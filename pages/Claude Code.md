tags:: AI, AI Agent，软件工具
category:: 软件工具

- 什么是 Claude Code？
	- > Claude Code 是 Anthropic 推出的智能编码助手，它不仅能生成代码，更能理解整个项目、自主规划任务、调用工具完成复杂的开发工作。
-
- # 官方网站
	- [Claude 中文 - Claude AI 开发技术社区](https://claudecn.com/)
		- [Claude 中文文档 – Claude 中文 - Claude AI 开发技术社区](https://claudecn.com/docs/)
			- [学习路径 – Claude 中文 - Claude AI 开发技术社区](https://claudecn.com/docs/learning-paths/)
			- [快速开始 – Claude 中文 - Claude AI 开发技术社区](https://claudecn.com/docs/claude-code/quickstart/)
	- [Claude Code 概述 - Claude Code Docs](https://code.claude.com/docs/zh-CN/overview)
		- [在 VS Code 中使用 Claude Code - Claude Code Docs](https://code.claude.com/docs/zh-CN/vs-code)
-
-
- # IDE集成
	- [Claude Code 正式发布 VS Code 扩展！](https://mp.weixin.qq.com/s/Ts80YnZLvvZTW2oM30vBTg)
-
- # 安装和使用
	- [Claude Code安装和使用教程 - 星墨 - 博客园](https://www.cnblogs.com/yada/p/19723381)
	- [Claude Code 快速切换模型：一键丝滑切换国产大模型 - 知乎](https://zhuanlan.zhihu.com/p/1994519994684428636)
	- [Claude Code 快速切换模型：一键丝滑切换国产大模型 - 知乎](https://zhuanlan.zhihu.com/p/1994519994684428636)
	- [榨干 Claude Code 的 16 个实用小技巧（高端玩法，建议收藏！） - Java技术栈 - 博客园](https://www.cnblogs.com/javastack/p/18978280)
	- [Claude Opus 4.6最强编程王上线，附国内5种使用方法 - 知乎](https://zhuanlan.zhihu.com/p/2003109863224541216)
	- [Claude Code 教程 | 菜鸟教程](https://www.runoob.com/claude-code/claude-code-tutorial.html)
	- 安装命令
		- ```powershell
		  // 安装特定版本
		  npm install -g @anthropic-ai/claude-code@2.1.123
		  
		  // 查看版本号
		  claude -v
		  
		  
		  ```
		- 参考
			- ((69fd4489-9603-4db3-98b3-b40669f3d928))
-
- # 命令和快捷键
	- ## PowerShell 命令
		- **注意命令行使用 ==管理员== 身份运行。**
		  id:: 69d8d163-40f7-419c-b655-246df3466349
		  | 命令 | 含义 |
		  | ---- | ---- |
		  | `claude --version` | 输出版本号 |
		  | `npm view @anthropic-ai/claude-code version` | 获取最新的版本号 |
		  | `claude update` | 检查更新，并升级到最新 |
		-
	- ## Claude Code 命令
		- 常用快捷键
		  | 命令 | 含义 |
		  |--|--|
		  | `Shift + Tab` | 循环切换权限模式 |
		  |`Ctrl + C`|中断生成，光标回到输入行|
		  |`Esc + Esc`|打开Rewind菜单，可选择撤回|
		  |`Ctrl + D`|退出程序，返回到系统终端|
		  |`/exit`|通过命令退出，效果同 `Ctrl + D`|
		  |`/clear`|清空当前对话历史，保留 Auto Memory 设置。|
		-
		- ## 操作指南
			- [[Claude Code 权限模式]]
			  id:: 69df6188-9a00-4c1f-84ae-692de2d85620
			- [[Claude Code 命令]]
			  id:: 69ecbb5f-8121-4216-b213-b282822a8b49
			- [[Claude Code 记忆]]
			  id:: 69ecc009-18a8-4d71-b32c-5af845b79a08
		-
-
- # Claude Code 学习
	- Git：[lhfer/claude-howto-zh-cn](https://github.com/lhfer/claude-howto-zh-cn)
		- > Claude Code 中文全面上手指南。基于 luongnv89/claude-howto 本土化重写，面向中国小白用户，保留命令与配置兼容性，并附学习路径与本地化校验护栏。
	- id:: 69eb0e89-7c78-4cf5-8011-b08f0cc21e74
- # Plugins
	- [Plugins for Claude Code and Cowork | Anthropic](https://claude.com/plugins#plugins)
	- [anthropics/claude-plugins-official: Official, Anthropic-managed directory of high quality Claude Code Plugins.](https://github.com/anthropics/claude-plugins-official)
	- [obra/superpowers: An agentic skills framework & software development methodology that works.](https://github.com/obra/superpowers)
	- ## Claude HUD
		- [jarrodwatts/claude-hud: A Claude Code plugin that shows what's happening - context usage, active tools, running agents, and todo progress](https://github.com/jarrodwatts/claude-hud)
		- [Claude HUD：给你的 Claude Code 装一块「仪表盘」为什么需要 Claude HUD？ 如果你已经在用 - 掘金](https://juejin.cn/post/7618239540528758838)
		- [给claudecode装上状态栏，效率起飞！claude-hud插件完全解析-CSDN博客](https://blog.csdn.net/qq_60735796/article/details/158208616)
- # 模型
	- Claude Code settings.json 配置文件中配置的模型信息：
		- ANTHROPIC_MODEL
		  > 它用于设置Claude Code在大部分常规任务中使用的默认模型。这项配置会覆盖Claude内部许多默认使用Sonnet模型的场景。
		- ANTHROPIC_DEFAULT_HAIKU_MODEL
		  > 简单任务 (例如, Bash, Edit): 默认使用 Haiku 模型。它响应快、成本低，适合处理基础操作。
		- ANTHROPIC_DEFAULT_SONNET_MODEL
		  > 常规任务 (例如, Read, Grep): 默认使用 Sonnet 模型。它在性能和速度之间取得了很好的平衡，是处理大多数任务的“主力”模型。
		- ANTHROPIC_DEFAULT_OPUS_MODEL
		  > 复杂任务 (例如, Write, MultiEdit): 当任务涉及大型重构、复杂逻辑推理、多文件编辑、架构设计或生成详细方案时，Claude Code 会自动调用 Opus 模型，以保证代码质量和一次性成功率。
		  Opus是Claude系列中最强大、最智能的模型，用于解决极其复杂的问题。
		- Claude Code 会根据任务的复杂程度，智能地选择模型，大致遵循以下规则：
			- 简单任务 (例如, Bash, Edit): 默认使用 Haiku 模型。它响应快、成本低，适合处理基础操作。
			- 常规任务 (例如, Read, Grep): 默认使用 Sonnet 模型。它在性能和速度之间取得了很好的平衡，是处理大多数任务的“主力”模型。
			- 复杂任务 (例如, Write, MultiEdit): 当任务涉及大型重构、复杂逻辑推理、多文件编辑、架构设计或生成详细方案时，Claude Code 会自动调用 Opus 模型，以保证代码质量和一次性成功率。
			- 因此，你并不需要为每一次对话都手动指定使用 Opus 模型。
	- ## 接入DeepSeek
		- 参考 [[DeepSeek]] 中： ((6a0d0665-b366-44b2-930c-02b6c909e266)) 章节。
- # Skills
	- ## 安装和使用
		- [【claude】Claude Skills 实战指南：从安装到自定义 - 甲枫 - 博客园](https://www.cnblogs.com/jiafeng1323/p/19561565)
	- ## Skills市场/开源项目
		- [Job Skills by Occupation | SOC Career & Technical Skills](https://skillsmp.com/zh/occupations)
		- [anthropics/skills: Public repository for Agent Skills](https://github.com/anthropics/skills)
		- [dotnet/skills: Repository for skills to assist AI coding agents with .NET and C#](https://github.com/dotnet/skills)
			- [.NET Agent Skills: How AI Coding Agents Get Domain Expertise - Uno Platform](https://platform.uno/articles/dotnet-agent-skills-ai-coding-agents/#elementor-toc__heading-anchor-0)
		- [Aaronontheweb/dotnet-skills: Claude Code skills and sub-agents for .NET Developers](https://github.com/Aaronontheweb/dotnet-skills/tree/master)
			- [dotnet-skills by Aaronontheweb - SourcePulse](https://www.sourcepulse.org/projects/24075074)
	- ## 自定义技能
		- [[code-downloader]]
- # 学习推荐网站
	- ((6a1f7871-72ee-4555-8881-d33a172adb19))
- # 动态/新闻
	- ((6a2a087a-b16d-4d4a-8110-172902229e4e))
-
- # 相关参考
	- [Claude Code 安装 - 快速开始 | Claude Code 中文站](https://claude-zh.cn/guide/getting-started)
	  id:: 69fd4489-9603-4db3-98b3-b40669f3d928
	- [Claude Code 最强配置清单：七个高效开源工具，让 AI 编程从“能用”变成“好用”​！！！](https://mp.weixin.qq.com/s/WRE1pvGvlSVYT3VIkYYc3g) #pending
	- [为 C#/.NET 打造的13条 CLAUDE.md：让 AI 不再写“新手代码”](https://mp.weixin.qq.com/s/Ko_UjuI1ev3mPWM51nwv_Q) #pending
	- 动态/新闻
		- [Claude Fable 5正式发布 - 王者归航。](https://mp.weixin.qq.com/s/MY6dhYVvRDeoZh-KQLet3Q)
		  id:: 6a2a087a-b16d-4d4a-8110-172902229e4e
-