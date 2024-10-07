# Textual User Interfaces
## Terminals
[Wikipedia](https://en.wikipedia.org/wiki/Computer_terminal)

Teletypewriter, TTY

### Pseudoterminals
[Wikipedia](https://en.wikipedia.org/wiki/Pseudoterminal)

pseudoterminal, pseudotty, PTY, virutal terminal

严格来说，现在几乎所有终端都是 pseudoterminals，不是物理的。pesudoterminal 更常见的用法是指不面向用户的终端。

[Windows Command-Line: Introducing the Windows Pseudo Console (ConPTY) - Windows Command Line](https://devblogs.microsoft.com/commandline/windows-command-line-introducing-the-windows-pseudo-console-conpty/)
- [Windows finally gets a real PTY - What the Daily WTF?](https://what.thedailywtf.com/topic/25590/windows-finally-gets-a-real-pty)

[Terminal under the hood - TTY & PTY - Ahmed Yakout](https://yakout.io/blog/terminal-under-the-hood/)

API:
- `isatty()`

  `isatty()` 的实际作用并不是判断物理终端，而是判断终端是否面向用户。

  - Linux: [`isatty()`](https://www.man7.org/linux/man-pages/man3/isatty.3.html)
  - Windows
    - [`GetConsoleMode()`](https://learn.microsoft.com/en-us/windows/console/getconsolemode)
    - `GetFileType()` `FILE_TYPE_CHAR`
      - MSVC: [`_isatty()`](https://learn.microsoft.com/en-us/cpp/c-runtime-library/reference/isatty) (`ucrtbase.o__isatty()`)

        Doesn't call `GetConsoleMode()`/`GetFileType()` directly, but inited in `initialize_stdio_handles_nolock()`.
        ```cpp
        extern "C" int __cdecl _isatty(int const fh)
        {
            _CHECK_FH_RETURN(fh, EBADF, 0);
            _VALIDATE_RETURN((fh >= 0 && (unsigned)fh < (unsigned)_nhandle), EBADF, 0);

            return static_cast<int>(_osfile(fh) & FDEV);
        }
        ```
        `FDEV` can't be set by `_setmode()`

        ```cpp
        static void initialize_stdio_handles_nolock() throw()
        {
            for (int fh = 0; fh != STDIO_HANDLES_COUNT; ++fh)
            {
                __crt_lowio_handle_data* const pio = _pioinfo(fh);

                // If this handle was inherited from the parent process and initialized
                // already, make sure it has the FTEXT flag and continue:
                if (pio->osfhnd != reinterpret_cast<intptr_t>(INVALID_HANDLE_VALUE) &&
                    pio->osfhnd != _NO_CONSOLE_FILENO)
                {
                    pio->osfile |= FTEXT;
                    continue;
                }

                // Regardless what happens next, the file will be treated as if it is
                // open in text mode:
                pio->osfile = FOPEN | FTEXT;

                // This handle has not yet been initialized, so  let's see if we can get
                // the handle from the OS:
                /// {STD_INPUT_HANDLE, STD_OUTPUT_HANDLE, STD_ERROR_HANDLE}[fh]
                intptr_t const os_handle = reinterpret_cast<intptr_t>(GetStdHandle(get_std_handle_id(fh)));

                bool const is_valid_handle = 
                    os_handle != reinterpret_cast<intptr_t>(INVALID_HANDLE_VALUE) &&
                    os_handle != reinterpret_cast<intptr_t>(nullptr);

                DWORD const handle_type = is_valid_handle
                    ? GetFileType(reinterpret_cast<HANDLE>(os_handle))
                    : FILE_TYPE_UNKNOWN;


                if (handle_type != FILE_TYPE_UNKNOWN)
                {
                    // The file type is known, so we obtained a valid handle from the
                    // OS.  Finish initializing the lowio file object for this handle,
                    // including the flag specifying whether this is a character device
                    // or a pipe:
                    pio->osfhnd = os_handle;

                    if ((handle_type & 0xff) == FILE_TYPE_CHAR)
                        pio->osfile |= FDEV;

                    else if ((handle_type & 0xff) == FILE_TYPE_PIPE)
                        pio->osfile |= FPIPE;
                }
                else
                {
                    // We were unable to get the handles from the OS.  For stdin, stdout,
                    // and stderr, if there is no valid OS handle, treat the CRT handle
                    // as being open in text mode on a device with _NO_CONSOLE_FILENO
                    // underlying it.  We use this value instead of INVALID_HANDLE_VALUE
                    // to distinguish between a failure in opening a file and a program
                    // run without a console:
                    pio->osfile |= FDEV;
                    pio->osfhnd = _NO_CONSOLE_FILENO;

                    // Also update the corresponding stdio stream, unless stdio was
                    // already terminated:
                    if (__piob)
                        __piob[fh]->_file = _NO_CONSOLE_FILENO;
                }
            }
        }
        ```

  - Rust
    - [`std::io::IsIterminal`](https://doc.rust-lang.org/std/io/trait.IsTerminal.html)
      ```rust
      pub fn is_terminal(h: &impl AsHandle) -> bool {
          handle_is_console(h.as_handle())
      }

      fn handle_is_console(handle: BorrowedHandle<'_>) -> bool {
          // A null handle means the process has no console.
          if handle.as_raw_handle().is_null() {
              return false;
          }

          let mut out = 0;
          if unsafe { c::GetConsoleMode(handle.as_raw_handle(), &mut out) != 0 } {
              // False positives aren't possible. If we got a console then we definitely have a console.
              return true;
          }

          // Otherwise, we fall back to an msys hack to see if we can detect the presence of a pty.
          msys_tty_on(handle)
      }

      fn msys_tty_on(handle: BorrowedHandle<'_>) -> bool {
          // Early return if the handle is not a pipe.
          if unsafe { c::GetFileType(handle.as_raw_handle()) != c::FILE_TYPE_PIPE } {
              return false;
          }

          /// Mirrors [`FILE_NAME_INFO`], giving it a fixed length that we can stack
          /// allocate
          ///
          /// [`FILE_NAME_INFO`]: https://learn.microsoft.com/en-us/windows/win32/api/winbase/ns-winbase-file_name_info
          #[repr(C)]
          #[allow(non_snake_case)]
          struct FILE_NAME_INFO {
              FileNameLength: u32,
              FileName: [u16; c::MAX_PATH as usize],
          }
          let mut name_info = FILE_NAME_INFO { FileNameLength: 0, FileName: [0; c::MAX_PATH as usize] };
          // Safety: buffer length is fixed.
          let res = unsafe {
              c::GetFileInformationByHandleEx(
                  handle.as_raw_handle(),
                  c::FileNameInfo,
                  (&raw mut name_info) as *mut c_void,
                  size_of::<FILE_NAME_INFO>() as u32,
              )
          };
          if res == 0 {
              return false;
          }

          // Use `get` because `FileNameLength` can be out of range.
          let s = match name_info.FileName.get(..name_info.FileNameLength as usize / 2) {
              None => return false,
              Some(s) => s,
          };
          let name = String::from_utf16_lossy(s);
          // Get the file name only.
          let name = name.rsplit('\\').next().unwrap_or(&name);
          // This checks whether 'pty' exists in the file name, which indicates that
          // a pseudo-terminal is attached. To mitigate against false positives
          // (e.g., an actual file name that contains 'pty'), we also require that
          // the file name begins with either the strings 'msys-' or 'cygwin-'.)
          let is_msys = name.starts_with("msys-") || name.starts_with("cygwin-");
          let is_pty = name.contains("-pty");
          is_msys && is_pty
      }
      ```
    - [atty: are you or are you not a tty?](https://github.com/softprops/atty/tree/master)

  这一 API 导致了程序模拟面向用户的终端变得困难，产生了对 [fake terminals](#fake-terminals) 的需要。

- 虽然为程序和用户输入输出提供单独的接口更加清晰，比如 `pesudo_stdin/out/err`，但这会增加程序的开发负担，不需要区分的程序也不得不进行区分。

### Fake terminals
First terminal, then pesudoterminal, then fake terminal, when pesudofaketerminal?

[A terminal case of Linux](https://fasterthanli.me/articles/a-terminal-case-of-linux)

Tools:
- Linux
  - [faketty: Wrapper to exec a command in a pty, even if redirecting the output](https://github.com/dtolnay/faketty)

  - [teetty: A bit like tee, a bit like script, but all with a fake tty. Lets you remote control and watch a process](https://github.com/mitsuhiko/teetty)
    - [tty\_spawn](https://docs.rs/tty-spawn/latest/tty_spawn/)
    - [Windows Support - Issue #5](https://github.com/mitsuhiko/teetty/issues/5)

  - [`script`](https://man7.org/linux/man-pages/man1/script.1.html)

    `script` only uses a single pty, which makes it impossible to demultiplex stdout and stderr to different places.

  - Hook `isatty`
    ```sh
    echo 'int isatty(int fd) { return 1; }' | cc -shared -o libfaketty.so -xc -
    LD_PRELOAD="$PWD"/libfaketty.so
    ```

  [shell - How to trick a command into thinking its output is going to a terminal - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/249723/how-to-trick-a-command-into-thinking-its-output-is-going-to-a-terminal)

  [How to fool a subprocess into thinking its stdout/stderr was a TTY while still reading output of its stdout/stderr? - help - The Rust Programming Language Forum](https://users.rust-lang.org/t/how-to-fool-a-subprocess-into-thinking-its-stdout-stderr-was-a-tty-while-still-reading-output-of-its-stdout-stderr/79810)

  [(Q) Executing command without tty (like a shell would) : r/rust](https://www.reddit.com/r/rust/comments/q7vzon/q_executing_command_without_tty_like_a_shell_would/)

- Windows
  - Hook `GetConsoleMode()` (Rust, Ruby, ...)
  - Hook `_isatty()` (dynamic CRT)
  - Hook `GetFileType()` (static CRT)
    ```cpp
    DWORD WINAPI GetFileType(
        _In_ HANDLE hFile
    ) {
        const auto result = hooks::GetFileType(hFile);
        if (hFile == GetStdHandle(STD_OUTPUT_HANDLE)) {
            return result & ~0xff | FILE_TYPE_CHAR;
        }
        return result;
    }
    ```

## Backspace
[python - Why doesn't `sys.stdout.write('\b')` backspace against newlines? - Stack Overflow](https://stackoverflow.com/questions/3593339/why-doesnt-sys-stdout-write-b-backspace-against-newlines)
> This is about the behavior of console windows: backspaces only work within a line, they won't backup over newlines.

> This is absolutely nothing to do with Python. It's your console driver that handles any visual effects. Most of them will emulate an ASR33 teletype ... backspace means move the print head one space back towards the start-of-line position, if possible.

How do pipe read libraries handle backspace? Nothing.

[linux - Bash - process backspace control character when redirecting output to file - Stack Overflow](https://stackoverflow.com/questions/34282174/bash-process-backspace-control-character-when-redirecting-output-to-file)

Implementations:
- Python: `python -c "print('a\bc')"`
- C++: [backspace.cpp](backspace.cpp)

## Windows
[Console documentation - Windows Console | Microsoft Learn](https://learn.microsoft.com/en-us/windows/console/)

Rust:
- [win32console: Provides a wrapper to interact with the windows console from rust.](https://github.com/Neo-Ciber94/win32console) (discontinued)