public:: true
tags:: AI, Token, [[Claude Code]] , GitHub Copilot, Cursor, Windsurf, Codex, OpenCode, OpenClaw
category:: 开发工具

- # 介绍
	- RTK 是一个高性能的命令行代理工具，它会在命令输出到达 LLM 上下文之前，智能地过滤和压缩这些内容。使用 Rust 编写的单一二进制文件，无需任何依赖，开销小于 10 毫秒，几乎感觉不到它的存在。
	- 最妙的是，RTK 的工作方式对 AI 助手完全透明。当你在 Claude Code 中执行 git status 时，RTK 会在后台自动将其改写为 rtk git status，压缩输出后再返回给 AI。Claude 完全感知不到这个过程，只会收到更简洁、更高效的输出结果。
- # 官方网站
	- ((69ff3761-06cc-403b-b40f-f313e9f1c42f))
	- ((69ff37a8-93af-40be-b070-51d54c26b285))
	- ((69ff377d-9b9d-4d02-8ee8-22cfde91d3e3))
-
- # 安装与配置
	- ## RTK安装
		- 访问 RTK Releases 页面。
		  logseq.order-list-type:: number
			- ((69ff37a8-93af-40be-b070-51d54c26b285))
		- 下载最新版本的 Windows 安装包：rtk-x86_64-pc-windows-msvc.zip
		  logseq.order-list-type:: number
		- 解压到合适的目录，例如：`C:\Program Files\rtk\`
		  logseq.order-list-type:: number
		- 将 RTK 目录添加到系统环境变量 PATH：
		  logseq.order-list-type:: number
			- 右键“此电脑” → “属性” → “高级系统设置”
			  logseq.order-list-type:: number
			- 点击“环境变量”
			  logseq.order-list-type:: number
			- 在“系统变量”中找到 Path，点击“编辑”
			  logseq.order-list-type:: number
			- 添加 RTK 所在目录路径
			  logseq.order-list-type:: number
			- 确定保存
			  logseq.order-list-type:: number
		- 打开新的命令提示符或 PowerShell，验证安装：
		  logseq.order-list-type:: number
			- `rtk --version`
	- ## Claude Code 中集成RTK
		- 在 [[Claude Code]] 中集成[[RTK]]只要执行如下命令：
			- `rtk init -g`
	-
- # 相关参考
	- [RTK：让 AI 编程工具省下 80% 的 Token 消耗](https://mp.weixin.qq.com/s/B9Vu_g6HIsmERWPWrh8i3Q)
	- [rtk-ai/rtk: CLI proxy that reduces LLM token consumption by 60-90% on common dev commands. Single Rust binary, zero dependencies](https://github.com/rtk-ai/rtk)
	  id:: 69ff3761-06cc-403b-b40f-f313e9f1c42f
	- [Releases · rtk-ai/rtk](https://github.com/rtk-ai/rtk/releases)
	  id:: 69ff37a8-93af-40be-b070-51d54c26b285
	- [rtk — Make your AI coding agent smarter | CLI proxy](https://www.rtk-ai.app/)
	  id:: 69ff377d-9b9d-4d02-8ee8-22cfde91d3e3
-