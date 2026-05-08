public:: true
tags:: React

- # 介绍
	- Node.js 是一个基于 **Chrome V8 JavaScript 引擎** 构建的**开源服务器端 JavaScript 运行时环境**，由 Ryan Dahl 于 2009 年创建。它采用**事件驱动、非阻塞 I/O 模型**，使其轻量高效，尤其适合数据密集型实时应用和高并发场景。
	- ## 核心特性与技术架构
		- ### 事件驱动与非阻塞 I/O
			- 通过 **libuv 库** 实现事件循环（Event Loop），单线程处理并发请求，避免多线程资源竞争问题。
			- 非阻塞 I/O 操作（如文件读写、网络请求）在后台执行，完成后通过回调通知主线程，显著提升吞吐量。
		- ### 模块化设计
			- 遵循 **CommonJS 规范**，通过 `require` 加载模块，`module.exports` 导出功能。
			- 核心模块（如 `http`、`fs`、`path`）内置，无需额外安装；第三方模块通过 **npm（Node Package Manager）** 管理。
		- ### 跨平台与高性能
			- 支持 Windows、Linux、macOS 等系统，底层依赖 V8 引擎的即时编译（JIT）优化 JavaScript 执行速度。
		- ## 总结
			- Node.js 革新了服务器端开发模式，使 JavaScript 成为全栈语言。其**高并发能力**、**丰富的模块生态**（npm）及**跨平台支持**，使其在实时应用、微服务、工具链开发中占据核心地位。学习建议从核心模块（`http`、`fs`）入手，逐步掌握异步编程与框架应用。
- # 官方网站
	- ((69fdb140-21ea-4039-887a-3cdb9f9152e7))
	- ((69fdb138-8087-4c2e-abb2-d65f74ffd03d))
- # 安装与配置
	- [[Node.js]] 安装与配置
	  id:: 69fdab2c-230f-49e7-b184-f56f4241ba1b
		- ==开发推荐== 使用 [[NVM]] 管理 Node.js 版本，安装与使用详见 [[NVM]]。
		  id:: 5a7198cb-9b74-47cb-b071-7094bbd2c330
	- 安装特定版本的 node.js
	  id:: 69fdbb0a-5e5c-42a4-b0fd-749baacdf7d1
		- 参考 ((69fdb17f-fe5c-45ed-907c-cb0327963d1e))
		  id:: 69fdbb1a-726e-4c85-bf46-87b0f1201030
- # 命令与使用
	- ```powershell
	  // 查看node的版本
	  node -v
	  
	  // 查看npm的版本
	  npm -v
	  
	  // 查看安装位置，cmd 中用 where node
	  gcm node
	  ```
- # 主要应用场景
	- ## Web 服务器与 API 开发
		- 使用 `http` 模块或框架（如 **Express.js**、Koa）快速构建 RESTful API 或 Web 服务。
		- 示例：创建 HTTP 服务器仅需数行代码：
			- ```jsx
			  const http = require('http');
			  http.createServer((req, res) => {
			    res.end('Hello World');
			  }).listen(3000);
			  ```
	- ## 实时应用开发
		- 适用于聊天应用、在线游戏等需**双向实时通信**的场景，结合 **WebSocket** 或 **Socket.IO** 库实现。
	- ## 工具链与自动化
		- 开发命令行工具（CLI）、构建工具（如 **Webpack**、**Gulp**）及测试框架（如 **Jest**、**Mocha**）。
	- ## 微服务与后端集成
		- 轻量级特性适合微服务架构，可连接数据库（MongoDB、MySQL）并整合消息队列（如 RabbitMQ）。
- # 生态系统与工具
	- ## [[NPM]]
		- 全球最大开源库仓库，提供超过 100 万个模块，支持依赖管理、脚本执行（`npm run`）。
	- ## 框架扩展
		- **Express**：轻量级 Web 框架，简化路由、中间件开发。
		- **NestJS**：企业级框架，支持 TypeScript 和依赖注入。
		- **Electron**：用 JavaScript 构建跨平台桌面应用（如 VS Code）。
- # 挑战与优化
	- ## 回调地狱（Callback Hell）
		- 解决方案：采用 **Promise**、**async/await** 优化异步代码结构。
	- ## 单线程瓶颈
		- 通过 **Cluster 模块** 或 **PM2 进程管理器** 启动多进程，利用多核 CPU。
	- ## 内存泄漏
		- 使用 **V8 内存快照分析工具**（如 `node-inspector`）定位未释放资源。
- # 发展历程
	- **2009 年**：Ryan Dahl 发布首个版本，聚焦高性能网络服务。
	- **2011 年**：获 Joyent 支持，推出 Windows 版本。
	- **2016 年**：npm 生态爆发，Yarn 诞生解决依赖管理问题。
	- **2020 年后**：Deno（Node 继任者）兴起，但 Node.js 仍是主流，持续更新 LTS 版本。
- # 相关参考
	- [Node.js — 在任何地方运行 JavaScript](https://nodejs.org/zh-cn)
	  id:: 69fdb140-21ea-4039-887a-3cdb9f9152e7
	- [Node.js — 下载 Node.js®](https://nodejs.org/zh-cn/download)
	  id:: 69fdb138-8087-4c2e-abb2-d65f74ffd03d
	- [Node.js安装及环境配置超详细教程【Windows系统】](https://blog.csdn.net/Nicolecocol/article/details/136788200)
	  id:: 69fdb17f-fe5c-45ed-907c-cb0327963d1e
-