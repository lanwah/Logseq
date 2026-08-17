tags:: #AI #隔离环境

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** [[cloudflare/computer]]
	- **使用协议：** [[MIT license]]
	- **开源地址：** https://github.com/cloudflare/computer
	- **开发语言：** TypeScript 94.6%+JavaScript 3.5%+Shell 1.9%
- # 项目介绍
	- **@cloudflare/computer** 是 Cloudflare 于 2026 年 8 月 3 日发布的开源 AI 智能体运行时[](https://www.ithome.com/0/985/457.htm)。它的核心理念是：**给每个 AI 智能体一台属于自己的“虚拟计算机”**。
	- `@cloudflare/computer` 是 Cloudflare 在 AI 智能体基础设施领域的一次重要尝试。它试图回答一个核心问题：**如何让数以亿计的 AI 智能体都能拥有一台属于自己的“计算机”，同时又不被算力成本压垮？** 答案是：通过 Isolate 和 Container 的混合调度，让轻量任务跑在隔离环境中、重任务才调用容器，从而在效率、能力和成本之间找到平衡。
	- 目前它仍处于早期预览阶段，适合实验、探索和原型开发[](https://github.com/cloudflare/computer)。如果你正在构建需要沙箱化代码执行的 AI 智能体系统，这个项目值得关注和尝试。
	- ## 🎯 解决什么问题？
		- 传统做法是为每个 AI 智能体分配一个容器，但这面临一个根本性难题：**全球算力无法支撑数亿乃至数十亿个并发智能体各自拥有专属容器**。Cloudflare 的解决方案是利用其擅长的 **Isolate（隔离环境）** 作为更轻量的计算原语——隔离环境启动和销毁极快，可以无限横向扩展。
		- `@cloudflare/computer` 在这个基础上更进一步：它把 **Isolate 的轻量高效**和 **Container 的完整能力**整合成一个统一的抽象层，让智能体按需在两者之间无缝切换。
	- ## 🏗️ 架构与工作原理
		- 项目的核心是 **Workspace（工作区）**——一个存储在 Cloudflare Durable Object 中的虚拟文件系统[](https://github.com/cloudflare/computer)：
			- **权威状态**：所有文件状态持久化在 Durable Object 的 **SQLite** 数据库中[](https://github.com/cloudflare/computer)
			- **单一真相源**：无论使用哪种执行后端，都读写同一份文件，不会出现数据不一致[](https://www.tycp.xyz/2821.html)
			- **文件来源**：工作区可以从云存储、Git 仓库或自定义文件导入内容
	- ## ✨ 核心功能
		- | 功能 | 说明 |
		  | ---- | ---- | ---- |
		  | **虚拟文件系统** | 基于 SQLite 的持久化文件系统，支持 read、write、edit、ls 等操作[](https://www.ithome.com/0/985/457.htm)[](https://cloudflare-docs.cloudflare-docs.workers.dev/changelog/post/2026-08-03-cloudflare-computer/) |
		  | **统一执行入口** | 通过 `workspace.runtime.exec(source, { backend })` 统一调用[](https://github.com/cloudflare/computer) |
		  | **可插拔后端** | 支持三种执行后端，可按需切换[](https://github.com/cloudflare/computer) |
		  | **操作审计** | 所有操作均可设定权限门槛、审计和观测[](https://www.ithome.com/0/985/457.htm)[](https://cloudflare-docs.cloudflare-docs.workers.dev/changelog/post/2026-08-03-cloudflare-computer/) |
		  | **AI SDK 兼容** | 提供 AI SDK 兼容的工具集，模型可自动选择合适的后端 |
	- ## 🧩 三种执行后端
		- | 后端 | 运行方式 | 适用场景 |
		  | ---- | ---- | ---- |
		  | **Isolate Shell** | 在 Dynamic Worker 中运行 just-bash，无容器、零冷启动[](https://github.com/cloudflare/computer)[](https://www.tycp.xyz/2821.html) | 文件处理、数据处理、Git 管理[](https://www.ithome.com/0/985/457.htm) |
		  | **Isolate JavaScript** | 在 Dynamic Worker 中运行 ES Module，支持 `node:fs/promises` 等模块[](https://github.com/cloudflare/computer)[](https://www.tycp.xyz/2821.html) | 需要 JavaScript 生态的轻量任务 |
		  | **Container** | 在 Cloudflare Containers 中运行完整 Linux 环境，通过 FUSE 挂载文件[](https://github.com/cloudflare/computer)[](https://www.tycp.xyz/2821.html) | 需要 npm、原生二进制、编译型工具的任务[](https://www.ithome.com/0/985/457.htm) |
		- 系统会根据任务类型自动选择后端——轻量任务走 Isolate，重负载任务才调用容器[](https://www.ithome.com/0/985/457.htm)。
- # 相关参考
	- [又一个神级 Agent 工具，YYDS。](https://mp.weixin.qq.com/s/_GBmDoWkmq56bNZPiEKsjw)