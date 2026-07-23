tags:: #终端工具, #跨平台, #CLI

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** #rmux
	- **使用协议：** [[MIT license]]
	- **开源地址：** https://github.com/Helvesec/rmux
	- **开发语言：** Rust 96.0%+Shell 2.1%+PowerShell 1.1%+Other 0.8%
- # 项目介绍
	- **rmux** 是一个用 Rust 编写的**通用终端复用器引擎**[](https://github.com/Helvesec/rmux)。它的核心定位是作为一个**可编程的“终端管理器”**，让开发者能够通过代码（而非仅仅手动操作）来驱动任何命令行（CLI）或终端界面（TUI）应用[](https://github.com/Helvesec/rmux)。
	- ##  核心特性
		- **跨平台原生支持**：支持 **Linux、macOS 和 Windows**，且 Windows 上**无需 WSL**[](https://github.com/Helvesec/rmux)。
		- **兼容 tmux 命令**：实现了 **90 多种 `tmux` 命令**，并配有兼容性测试，方便 `tmux` 用户平滑迁移[](https://github.com/Helvesec/rmux)。
		- **提供多语言 SDK**：不仅是一个 CLI 工具，更是一个**可编程引擎**。它提供了 Rust、Python 和 TypeScript 的 SDK，方便开发者进行深度集成和自动化控制[](https://github.com/Helvesec/rmux)。
		- **内置 Web 分享**：支持将终端会话通过浏览器分享，并采用**混合后量子端到端加密**保障安全[](https://github.com/Helvesec/rmux)。
		- **AI 助手友好**：提供了 `rmux claude` 命令，可一键启动 Claude Code 的 **Teammate Mode**[](https://github.com/Helvesec/rmux)。同时，还提供了一个 Claude Code Skill，让 Claude 能记住 rmux 的使用模式[](https://github.com/Helvesec/rmux)。
		- **高性能与可嵌入**：采用 Rust 编写，性能优化[](https://github.com/Helvesec/rmux)。它还提供了一个 **Ratatui widget**，可以在 Rust 终端应用中直接渲染 rmux 的面板[](https://github.com/Helvesec/rmux)。
- # 相关参考
	- [专为 Agent 而生的终端神器，开源了！](https://mp.weixin.qq.com/s/xbdMy9Ofv4W3wHk-0BuWYg) #tmux