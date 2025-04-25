# Terminal Multiplexers
A **terminal multiplexer** is a software application that can be used to multiplex several separate pseudoterminal-based login sessions inside a single terminal display, terminal emulator window, PC/workstation system console, or remote login session, or to detach and reattach sessions from a terminal. It is useful for dealing with multiple programs from a command line interface, and for separating programs from the session of the Unix shell that started the program, particularly so a remote process continues running even when the user is disconnected.[^wiki]

[^wiki]: [Terminal multiplexer - Wikipedia](https://en.wikipedia.org/wiki/Terminal_multiplexer)

## Implementations
[screen vs. tmux : r/linux](https://www.reddit.com/r/linux/comments/1gjdni9/screen_vs_tmux/)
> tried both, tmux for the last 4 months, screen for 4 years. I take tmux, does everything that screen does but it seems to have much more support.

[Which multiplexer do yall use? Tmux, Zellij, Wezterm? : r/neovim](https://www.reddit.com/r/neovim/comments/1bjztoo/which_multiplexer_do_yall_use_tmux_zellij_wezterm/)

[shell - How to run a command in background using ssh and detach the session - Stack Overflow](https://stackoverflow.com/questions/1628204/how-to-run-a-command-in-background-using-ssh-and-detach-the-session)

### Screen
[Wikipedia](https://en.wikipedia.org/wiki/GNU_Screen)

### [tmux](https://github.com/tmux/tmux)
[Getting Started](https://github.com/tmux/tmux/wiki/Getting-Started)

- Installation
  - [Debian -- Package Search Results -- tmux](https://packages.debian.org/search?lang=en&keywords=tmux)

Bad help.

Quick references:
- [tmux shortcuts & cheatsheet](https://gist.github.com/MohamedAlaa/2961058)
- [Tmux Cheat Sheet & Quick Reference](https://tmuxcheatsheet.com/)

Restart:
```sh
tmux kill-session -t app
tmux new-session -s app -d  app
```

### [Zellij](https://github.com/zellij-org/zellij)
- [Third Party Install](https://github.com/zellij-org/zellij/blob/main/docs/THIRD_PARTY_INSTALL.md)
  
  Only Arch, Fedora, Void and macOS.
- No China mirror
- No Windows support

[Zellij vs Tmux | Typecraft Learn](https://typecraft.dev/tutorial/zellij-vs-tmux)

### [WezTerm](https://github.com/wezterm/wezterm)
> A GPU-accelerated cross-platform terminal emulator and multiplexer written by @wez and implemented in Rust
