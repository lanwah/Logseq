tags:: #Skill #去AI味

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** #Hallmark
	- **使用协议：** [[MIT license]]
	- **开源地址：** https://github.com/Nutlope/hallmark
	- **开发语言：** CSS 58.5%+HTML 35.1%+JavaScript 6.4%
- # 项目介绍
	- Hallmark 是一个专为 Claude Code、Cursor 和 Codex 等 AI 编程助手设计的 Agent Skill（智能体技能），它的核心目标是让 AI 生成的界面看起来不像 AI 生成的。
	- 它由 Together AI 的工程师 Nutlope 创建，旨在把“拒绝 AI 味设计”从一句口号，变成一套可审计、可执行的设计协议。
		- ## 🎨 核心机制：拒绝模板化的“设计约束”
			- Hallmark 不是一个 UI 组件库，也不是一个建站框架。它更像一个内置在 AI 助手里的“设计总监”，通过一套严格的规则来约束 AI 的创作过程：
				- **宏观结构 (Macrostructure)：**它会为一个设计需求（brief）挑选一个独特的“页面骨架”，确保每个设计在结构层面就与众不同。
				- **21 种主题 (Twenty-one Themes)：**内置了 21 种视觉主题，如“Hum”、“Cobalt”、“Carnival”等，避免 AI 总是使用千篇一律的配色和样式。
				- **57 道“反 Slop”闸门 (57 Slop-Test Gates)：**这是核心的质量控制机制。在交付设计前，会进行 57 项检查，确保设计没有落入 AI 常见的“套路”。
				- **自我批判 (Pre-emit Self-critique)：**在最终输出前，Hallmark 会对自己生成的设计进行一轮批判性审查，进一步优化设计质量。
				- **定制主题 (Custom)：**如果内置主题都不符合需求，Hallmark 会进入“定制”模式，从头开始设计一套独一无二的配色、字体和布局。这同样会经过 57 道闸门的检验。
		- ## 🛠️ 四个核心命令 (Four Verbs)
			- Hallmark 通过以下四个核心动词（命令）来驱动其功能[](https://github.com/Nutlope/hallmark)：
			  | 命令 | 功能描述 |
			  | ---- | ---- | ---- |
			  | **`hallmark` (默认)** | 基于需求构建新的 UI。它会选择一个宏观结构，应用规则集，并在交付前运行“反 Slop”测试[](https://github.com/Nutlope/hallmark)。 |
			  | **`hallmark audit <目标>`** | 对现有的代码进行评分，对照“反模式”清单生成问题列表，但不会修改代码[](https://github.com/Nutlope/hallmark)。 |
			  | **`hallmark redesign <目标>`** | 丢弃原有的结构，保留文案、信息架构和品牌元素，用不同的“指纹”重建页面[](https://github.com/Nutlope/hallmark)。 |
			  | **`hallmark study <目标>`** | 提取一个优秀设计的“DNA”，包括其宏观结构、字体搭配和色彩锚点，并可生成一个 `design.md` 文件供其他 AI 工具使用[](https://github.com/Nutlope/hallmark)。 |
	-
- # 相关参考
	- [又一个神级 skill ，暴涨 2 万 Star。](https://mp.weixin.qq.com/s/KBhWFbho8aBlKv7VR7nzhg) #Hallmark