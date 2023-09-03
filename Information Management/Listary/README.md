# [Listary](https://www.listary.com/)
[Wikipedia](https://en.wikipedia.org/wiki/Listary)

[Listary Docs](https://help.listary.com/)

[Listary Discussions](https://discussion.listary.com/)

## To-dos
- 搜索
  - 精确搜索
    - [x] 匹配评分 ([v6.3.0.45](https://discussion.listary.com/t/6-3-0-45-beta-is-live-new-file-search-window-updated-file-search-engine-new-user-documentation/8553), [中文](https://discussion.listary.com/t/6-3-0-45-beta/8554))

     [有搜索不到文件夹的情况，搜索结果排序不合理 - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/topic/8551)
    - 最高性能算法
  - 拼音搜索
    - [x] 简拼
    - [x] 全拼 ([v6.0.11.34](https://discussion.listary.com/t/listary-6-0-11-35/7946))
      - [x] 全拼补充

      [拼音的全拼什么时候上](https://discussion.listary.com/t/topic/7874)

      [建议在搜索时可以通过字母和拼音的简写或全拼来进行搜索](https://discussion.listary.com/t/topic/6975)
    - 双拼
    - 扩展平面汉字
    - 音频、词频
      
      [6.0.11.35全拼bug反馈（全拼关键字搜索到非目标文件）（有图）](https://discussion.listary.com/t/6-0-11-35-bug/7970)
  - 简繁搜索
  - 日语罗马音搜索
  - 模糊搜索
    - 编辑距离
    - 全面模糊搜索
      - 精确搜索结果为空时
  - 正则表达式
    
    [支持正则搜索吗](https://discussion.listary.com/t/topic/7991)
- 索引
  - [x] Rust 引擎
    - [Listary 新搜索算法 & 引擎 Demo (Windows/macOS)](https://discussion.listary.com/t/listary-demo-windows-macos/7563)
    - [x] 数据库：RocksDB
    - [x] FileDB
    - [x] Indexers
      - [x] NTFS
      - [x] Notify
        - [x] Poll
      - [ ] Load old index before rebuild
    - [x] Searchers
    - [x] IPC: gRPC
    - [x] Error repoting: Sentry
  - 静态
    - 本地文件
    - desktop.ini
      
      [Windows11无法搜索系统功能的中文名](https://discussion.listary.com/t/windows11/7843)
    - Directory Opus

      [Feature Request: Use Directory Opus’ Favorites and Folder Aliases](https://discussion.listary.com/t/feature-request-use-directory-opus-favorites-and-folder-aliases/2475)
    - Windows Search
      - OneNote

        [什么时候支持Oneonte笔记搜索](https://discussion.listary.com/t/oneonte/8103)
    - ETW
    - 程序文件排除
      - QQ
    - Windows Shell
    - Property System
      - Total Commander
    - WSL 2
    - GitHub repos
    - 剪切板
    - Telegram
    - Discord
    - Markdown 链接
    
  - 动态（命令）
    - 插件

      [逛Github，发现已经有人基于Listary 6 beta开发了个词典插件](https://discussion.listary.com/t/github-listary-6-beta/5753)
    - Browsers
      - Tabs
      - Bookmarks

        [Bookmarks (Vivaldi, Firefox, ...) - support - Listary Discussions](https://discussion.listary.com/t/bookmarks-vivaldi-firefox/8548)
    - UIA
    - WolframAlpha
    - AutoHotkey 命令
    - Python 命令
    - IPython
      - Python
      - Sage
    - Timer tracker
    - DOpus FAYT
- UI
  - [x] File search window ([v6.3.0.45](https://discussion.listary.com/t/6-3-0-45-beta-is-live-new-file-search-window-updated-file-search-engine-new-user-documentation/8553), [中文](https://discussion.listary.com/t/6-3-0-45-beta/8554))

    [很不好用啊，模糊搜索时绝大多数文件都搜索不出来 - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/topic/8536)
  - 激活
    - [x] Alt+Space 激活
    - [x] 从开始菜单激活全局搜索 ([v6.1.0.37](https://discussion.listary.com/t/6-1-0-37-beta-released/8149), [中文](https://discussion.listary.com/t/6-1-0-37-beta/8150))

      [在文件中双击Ctrl能否默认为全局搜索](https://discussion.listary.com/t/ctrl/7883)
    - 全局搜索在高 DPI 下的激活位置会偏移
    - [x] 鼠标中键激活闪退问题 ([v6.2.0.41](https://discussion.listary.com/t/6-2-0-41-beta-released-dark-theme-is-now-available/8325), [中文](https://discussion.listary.com/t/6-2-0-41-beta/8324))
    
      [Listary最新的测试版在Win11还是有问题](https://discussion.listary.com/t/listary-win11/7788)

      [中键呼出菜单闪退 左键双击无效](https://discussion.listary.com/t/topic/7913)

      ~~[单击中键弹出的Menu会闪退](https://discussion.listary.com/t/menu/4751)~~

      [鼠标中间键无法弹出快捷菜单](https://discussion.listary.com/t/topic/4279)
    - 左键双击

      [中键呼出菜单闪退 左键双击无效](https://discussion.listary.com/t/topic/7913)

      [双击鼠标左键有不能呼出菜单的情况](https://discussion.listary.com/t/topic/8148)

    - [x] 对话框搜索框残留问题 ([v6.2.0.41](https://discussion.listary.com/t/6-2-0-41-beta-released-dark-theme-is-now-available/8325), [中文](https://discussion.listary.com/t/6-2-0-41-beta/8324))

      [Bug 反馈 6.0.11.35 跳转窗口无法自动消失](https://discussion.listary.com/t/bug-6-0-11-35/7963)

      [\[BUG\] 另存为对话框](https://discussion.listary.com/t/bug/8164)

      [\[Bug\] 打开文件选择窗口时Listary输入框错位](https://discussion.listary.com/t/bug-listary/8190)

      [Bug 保存之后，弹出框下的搜索框不会一起消失](https://discussion.listary.com/t/bug/8153)

      [Bug反馈 6.1.0.38 跳转窗口无法自动消失的bug再次出现](https://discussion.listary.com/t/bug-6-1-0-38-bug/8176)

      [Bar hanging on screen after closing save as in explorer](https://discussion.listary.com/t/bar-hanging-on-screen-after-closing-save-as-in-explorer/8158)

      [Listary remaining open after File Save/Open dialog used](https://discussion.listary.com/t/listary-remaining-open-after-file-save-open-dialog-used/3019)

    - 管理员自启问题

      [Running app through Listary different from Start menu](https://discussion.listary.com/t/running-app-through-listary-different-from-start-menu/8215)

      [\[BUG\]更新后Windows Terminal总是以管理员权限启动](https://discussion.listary.com/t/bug-windows-terminal/8039)

      [Opening Listary from applications running as administrator](https://discussion.listary.com/t/opening-listary-from-applications-running-as-administrator/5759)

    - 桌面激活要求管理员权限

  - 快速选择
    - [x] 搜索结果热键失效 bug ([v6.1.0.37](https://discussion.listary.com/t/6-1-0-37-beta-released/8149), [中文](https://discussion.listary.com/t/6-1-0-37-beta/8150))

      [Listary 6的界面问题](https://discussion.listary.com/t/listary-6/4680)
        
      [\[BUG\] 搜索结果的图标有时候不会显示](https://discussion.listary.com/t/bug/8162/3)

    - Alt+数字键
  - Preview handlers
    - QuickLook

      [QuickLook (Windows) and file open&save dialogs](https://discussion.listary.com/t/quicklook-windows-and-file-open-save-dialogs/5387)
    - Total Commander
  - 搜索框图标操作
  - 动作
      - （使用 VSC）打开文件所属 Git 目录
  - 主题
    - [x] Dark mode ([v6.2.0.41](https://discussion.listary.com/t/6-2-0-41-beta-released-dark-theme-is-now-available/8325), [中文](https://discussion.listary.com/t/6-2-0-41-beta/8324))

      [Listary什么时候支持更换夜间主题啊](https://discussion.listary.com/t/listary/8124)

      [关于增加深色模式并根据系统自动切换](https://discussion.listary.com/t/topic/7456)

      [When will the black theme be launched?](https://discussion.listary.com/t/when-will-the-black-theme-be-launched/8123/3)

      [Listary6的外观功能现在是用不了吗](https://discussion.listary.com/t/listary6/7799)

      [Themes?](https://discussion.listary.com/t/themes/7859)

      [Dark theme?](https://discussion.listary.com/t/dark-theme/7656)

      [Will theme coming soon?](https://discussion.listary.com/t/will-theme-coming-soon/8025)
  - WPF 占用独显问题

    [Listary 6 调用surface book 独立显卡的问题](https://discussion.listary.com/t/listary-6-surface-book/4948)

    [Listary 阻止显卡切换](https://discussion.listary.com/t/listary/7602)
  - [x] 长路径 ([v6.2.0.41](https://discussion.listary.com/t/6-2-0-41-beta-released-dark-theme-is-now-available/8325), [中文](https://discussion.listary.com/t/6-2-0-41-beta/8324))

    [长文件名的显示问题](https://discussion.listary.com/t/topic/4660)
- Listary as a service
  - 文件对话框集成
    - [x] WPS ([v6.3.0.45](https://discussion.listary.com/t/6-3-0-45-beta-is-live-new-file-search-window-updated-file-search-engine-new-user-documentation/8553), [中文](https://discussion.listary.com/t/6-3-0-45-beta/8554))
    - [x] WinRAR ([v6.1.0.37](https://discussion.listary.com/t/6-1-0-37-beta-released/8149), [中文](https://discussion.listary.com/t/6-1-0-37-beta/8150))

      [希望能支持winrar解压界面路径自动跳转](https://discussion.listary.com/t/winrar/7860)

       - [x] [Bug：winrar解压对话框 从DOpus自动切换某些路径会出现乱码](https://discussion.listary.com/t/bug-winrar-dopus/8179) ([v6.2.0.42](https://discussion.listary.com/t/please-update-to-listary-6-2-0-42-manually-if-youre-using-6-2-0-41-beta/8421), [中文](https://discussion.listary.com/t/listary-6-2-0-42-6-2-0-41-beta/8422))
  - 列表搜索
  - [ ] 文件管理器集成
    - [x] 插件 ([v6.1.0.37](https://discussion.listary.com/t/6-1-0-37-beta-released/8149), [中文](https://discussion.listary.com/t/6-1-0-37-beta/8150))

      [Feature request: Add "Type directly for search" for other file managers](https://discussion.listary.com/t/feature-request-add-type-directly-for-search-for-other-file-managers/8194)
    - VS Code
    - Windows Terminal
    - Obsidian
    - [ ] Directory Opus

      [Listary 6 在Dopus文资源管理器上有bug](https://discussion.listary.com/t/listary-6-dopus-bug/7397)

      [Listary 6 not highlighting files in Directory Opus](https://discussion.listary.com/t/listary-6-not-highlighting-files-in-directory-opus/7625)
    - Files
      
      [请添加Ctrl+G定位功能对Files的支持](https://discussion.listary.com/t/ctrl-g-files/7227)

      [Files App support](https://discussion.listary.com/t/files-app-support/7631)

      [Listary 5 : Making listary's quick switch work on 3rd party file explorer, Files](https://discussion.listary.com/t/listary-5-making-listarys-quick-switch-work-on-3rd-party-file-explorer-files/7041)

      [能否增加对 files App的支持？](https://discussion.listary.com/t/files-app/7496)

      [API for third-party applications to get Files tab‘s path · Issue #11765 · files-community/Files](https://github.com/files-community/Files/issues/11765)
    - RX文件管理器

      [第三方集成可以添加 rx文件管理器吗](https://discussion.listary.com/t/rx/7467)
    - Mouse Down Blow Up
  - Everything API 兼容层
    - 文件夹大小列
- 代码
  - ~~.NET 7~~
  - C# 语言标准
  - Issue tacker
  - [ ] 开源生态：[listary](https://github.com/listary)
  - 异常时捕获变量
  - [ ] 日志文件大小限制

    [Listary在appdata下的log文件能删掉吗 - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/listary-appdata-log/8485)

## Related applications
- Everything
- Iconer
- Flow Launcher
- Fluent Search
  - [Fluent Search | 支持工作流的高颜值 Windows 搜索启动器 - 发现频道 - 小众软件官方论坛](https://meta.appinn.net/t/topic/38094)
  - [你更愿意使用 Listary 还是 FluentSearch 呢？ - V2EX](https://www.v2ex.com/t/916709)
- uTools
- Quicker
- Hookmark

如何和而不同？
- 智能、易用
- Everything：精确

[总结了一下常见的“快速启动类软件” - 大家的板块 / 网络黄页 - 小众软件官方论坛](https://meta.appinn.net/t/topic/23645)

## History
- 2018-12-24 [Listary 6 Beta 🎉 - release - Listary Discussions](https://discussion.listary.com/t/listary-6-beta/4615)
- 2019-01-09 [Listary 6的界面问题 - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/listary-6/4680)
  - 自动补全？
- 2019-12-21 [【我回来了】目前 Listary 6 中最缺哪些功能？ - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/listary-6/5531)
- 2022-04-26 [致 Listary 用户的一封信💌 - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/listary/7237)
- 2022-07-04 [Listary 新搜索算法 & 引擎 Demo (Windows/macOS) - 中文讨论区 - Listary Discussions](https://discussion.listary.com/t/listary-demo-windows-macos/7563)