tags:: #Skill #浏览器自动化

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** [[browser-act/skills]]
	- **使用协议：** [[MIT license]]
	- **开源地址：** https://github.com/browser-act/skills
	- **开发语言：** Python 100%
- # 项目介绍
	- **browser-act/skills** 是一个为 AI 智能体（Agent）设计的开源浏览器自动化 CLI 工具[](https://github.com/browser-act/skills)。它让 AI 能像人一样操作真实浏览器，突破反爬壁垒，在多任务并行时做到身份隔离，并在遇到无法处理的情况时无缝转交给真人[](https://github.com/browser-act/skills)。
	- `browser-act/skills` 本质上是一套为 AI 智能体设计的**浏览器自动化“技能包”**。它通过模拟真实用户、突破反爬、支持并发和人工接管等机制，让 AI Agent 能像人一样在复杂的网络环境中自主操作浏览器[](https://github.com/browser-act/skills)。
	- ## 🎯 主要功能
		- | 功能模块 | 核心能力 |
		  | ---- | ---- | ---- |
		  | **突破封锁** | 通过**三层机制**逐步对抗反爬：`环境层`（指纹伪装、TLS 和代理轮转）[](https://github.com/browser-act/skills)→ `执行层`（自动解决验证码、提取受保护页面）[](https://github.com/browser-act/skills)→ `人工层`（生成链接让真人接管）[](https://github.com/browser-act/skills)。 |
		  | **三种浏览器模式** | **`chrome`**（复用本地 Chrome 登录态）；**`stealth`隐私模式**（每次会话使用全新指纹和代理，不留痕迹）；**`stealth`固定身份模式**（为多账号并行提供稳定指纹和 IP）[](https://github.com/browser-act/skills)。 |
		  | **零干扰并发** | 支持跨浏览器并行和同浏览器多会话，每个任务有独立的 Cookies、指纹和代理，互不干扰[](https://github.com/browser-act/skills)。 |
		  | **为 Agent 设计** | 输出**紧凑的索引文本**（比 JSON/HTML 更省 Token）[](https://github.com/browser-act/skills)；通过 **`state`** 命令获取可交互元素列表，然后用 **`click 3` / `input 2`** 这样的索引进行交互[](https://github.com/browser-act/skills)。 |
		  | **语义记忆** | 每个浏览器可携带一个 `desc` 描述，供 Agent 按含义匹配任务[](https://github.com/browser-act/skills)。 |
		  | **安全确认** | 创建/删除浏览器、导入 Profile、修改代理等敏感操作需用户**明确批准**，且每次都需要重新确认[](https://github.com/browser-act/skills)。 |
	- ## 🚀 如何使用
		- **1. 安装**
		  在你的 AI 编程助手（如 Claude Code、Cursor 等[](https://github.com/browser-act/skills)）中，告诉它：
		  > "Install browser-act. Skill source: [https://github.com/browser-act/skills/tree/main/browser-act](https://github.com/browser-act/skills/tree/main/browser-act)"
		- **2. 快速上手**
		  安装后，你的 Agent 可以通过 `browser-act` 命令执行操作[](https://github.com/browser-act/skills)：
		- ```bash
		  # 提取受保护页面内容（零配置）
		  browser-act stealth-extract https://example.com
		  
		  # 完整浏览器自动化
		  browser-act --session my-task browser open https://example.com
		  browser-act --session my-task state              # 查看可点击元素
		  browser-act --session my-task click 3            # 点击索引为3的元素
		  browser-act --session my-task input 2 "hi"       # 在索引为2的输入框输入文字
		  ```
	- ## 💰 收费模式
		- 项目大部分功能免费，只有两项需要付费：**托管代理**，以及**超出 5 个的隐身浏览器实例**[](https://github.com/browser-act/skills)。
		  | 功能 | 免费（无需登录） | 免费（需登录） | 付费 |
		  | ---- | ---- | ---- |
		  | 浏览器自动化、Chrome 直连 | ✅ | ✅ | ✅ |
		  | 隐身浏览器 (≤5个)、验证码破解、远程协助等 | ❌ | ✅ | ✅ |
		  | 隐身浏览器 (>5个)、动态/静态代理 | ❌ | ❌ | ✅ |
	- ## 🛠️ Skill Forge：你的专属爬虫工程师
		- 此外，项目还包含一个名为 **Skill Forge** 的工具[](https://github.com/browser-act/skills)。它能**自动探索目标网站，发现其 API 和数据模式，生成一个可直接部署的 Skill 包**，用于稳定、大规模地提取数据[](https://github.com/browser-act/skills)。目前已有一个包含 30 多个预置 Skill 的解决方案目录，覆盖 Amazon、Google Maps、YouTube、Reddit、微信、知乎等平台[](https://github.com/browser-act/skills)。
- # 官方网站
	- [BrowserAct | Build a reusable web scraper from one prompt](https://www.browseract.com/?co-from=kyri01)
- # 相关参考
	- [又一个神级 skill，这次对小白更友好了。](https://mp.weixin.qq.com/s/e5kowHhX6SFrZJm_UosXFA)