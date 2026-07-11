tags:: IDE, AI, VS Code, React, C# 
category:: AI编程工具

- # 介绍
-
- # 官方网站
	- ((6a066805-ea9d-4550-ab8d-dce2b0bf32ec))
	- **下载：**((6a066819-32a5-4f08-baf2-e0a11e6639ee))
	- **文档：** ((6a0a952a-4cb9-4da5-bb10-be0d96003b7a))
	- ## 官方文档索引
		- | 主题 | 链接 |
		  | ---- | ---- | ---- |
		  |文档总览|[https://cursor.com/docs](https://cursor.com/docs)|
		  |快速入门|[https://cursor.com/docs/get-started/quickstart](https://cursor.com/docs/get-started/quickstart)|
		  |Agent|[https://cursor.com/docs/agent/overview](https://cursor.com/docs/agent/overview)|
		  |Plan 模式|[https://cursor.com/docs/agent/plan-mode](https://cursor.com/docs/agent/plan-mode)|
		  |Ask 模式|[https://cursor.com/help/ai-features/ask-mode](https://cursor.com/help/ai-features/ask-mode)|
		  |Rules|[https://cursor.com/docs/rules](https://cursor.com/docs/rules)|
		  |Skills|[https://cursor.com/docs/skills](https://cursor.com/docs/skills)|
		  |MCP|[https://cursor.com/docs/mcp](https://cursor.com/docs/mcp)|
		  |Tab|[https://cursor.com/help/ai-features/tab](https://cursor.com/help/ai-features/tab)|
		  |索引|[https://cursor.com/help/customization/indexing](https://cursor.com/help/customization/indexing)|
		  |Prompting / @|[https://cursor.com/docs/agent/prompting](https://cursor.com/docs/agent/prompting)|
		  |Cloud Agent|[https://cursor.com/docs/cloud-agent](https://cursor.com/docs/cloud-agent)|
		  |CLI|[https://cursor.com/docs/cli/overview](https://cursor.com/docs/cli/overview)|
		  |完整 sitemap|[https://cursor.com/llms.txt](https://cursor.com/llms.txt)|
- # 快捷键
	- |快捷键|说明|
	  |--|--|
	  |Shift + Table|切换Agent模式|
	  |Ctrl + M, Ctrl + S|打开键盘快捷键|
	  |Ctrl + T|新建聊天窗口|
	  |Ctrl + F4|关闭聊天窗口|
- # 授权
	- ## 全局配置
		- 用户目录下：.cursor\cli-config.json
			- ```json
			  {
			    "permissions": {
			      "deny": [
			        "Bash(rm -rf *)",
			        "Bash(curl *)",
			        "Bash(sudo *)"
			      ],
			      "ask": [],
			      "allow": [
			        "Bash(winget search:*)",
			        "Bash(rtk ls *)",
			        "Bash(rtk find *)",
			        "Bash(rtk read *)",
			        "Bash(git clone *)",
			        "Bash(git log *)",
			        "Bash(git status)",
			        "Skill(code-downloader)"
			      ]
			    }
			  }
			  
			  ```
		- .cursor\permissions.json
			- ```json
			  {
			    "terminalAllowlist": [
			      "git status"
			    ]
			  }
			  ```
	- ## 项目配置
		- 项目目录下：.cursor\cli.json
			- ```json
			  {
			    "permissions": {
			      "deny": [
			        "Bash(rm -rf *)",
			        "Bash(curl *)",
			        "Bash(sudo *)"
			      ],
			      "ask": [],
			      "allow": [
			        "Bash(winget search:*)",
			        "Bash(rtk ls *)",
			        "Bash(rtk find *)",
			        "Bash(rtk read *)",
			        "Bash(git clone *)",
			        "Bash(git log *)",
			        "Bash(git status)",
			        "Skill(code-downloader)"
			      ]
			    }
			  }
			  
			  ```
- # Rules 与 AGENTS.md（项目规范）
	- 这是 Cursor 官方强调的「持久化指令」机制，详见 [Rules 文档](https://cursor.com/docs/rules.md)。
	- ## 四种规则类型
		- | 类型 | 位置 | 作用范围 |
		  | ---- | ---- | ---- |
		  |Project Rules|`.cursor/rules/*.mdc`|仓库内，可版本控制|
		  |AGENTS.md|项目根目录 / 子目录|纯 Markdown，始终生效|
		  |User Rules|Settings → Rules|本机所有项目|
		  |Team Rules|Dashboard|团队/企业统一规范|
	- ## 规则应用方式
		- | 模式 | 何时生效 |
		  | ---- | ---- | ---- |
		  |Always Apply|每次对话|
		  |Apply Intelligently|Agent 按 `description` 判断|
		  |Apply to Specific Files|`globs` 匹配时|
		  |Apply Manually|聊天中 `@rule-name`|
	- **官方最佳实践：**
		- 单条规则 **< 500 行**，建议 50–200 行，**一文件一主题**
		- **不要一开始就写满规则**——等 AI 反复犯同一类错再加
		- 用**具体示例**和 `@filename`，不要贴整本风格指南
		- **提交到 Git**，团队共享
		- 规则**不影响 Tab 和 Inline Edit**，只影响 Agent/Chat
		  **注意：** 旧版 .cursorrules 仍可用，但官方建议迁移到 .cursor/rules 或 AGENTS.md。
- # Skills（可复用工作流）
	- [Skills 文档](https://cursor.com/docs/skills.md) 适合把**重复流程**固化：
		- 位置：.cursor/skills/ 或 ~/.cursor/skills/
		- 结构：my-skill/SKILL.md + YAML frontmatter
		- 手动调用：聊天输入 /skill-name
		- 可用 `paths` 限定文件范围；`disable-model-invocation: true` 仅作 slash 命令
	- 适合：PR 审查清单、部署流程、代码下载、特定框架脚手架等。
- # MCP（连接外部系统）
	- [MCP 文档](https://cursor.com/docs/mcp.md) 让 Agent 访问 GitHub、数据库、Slack 等。
	  **建议：**
		- 配置放在 .cursor/mcp.json（项目）或 ~/.cursor/mcp.json（全局）
		- 密钥用 `${env:VAR}`，**不要硬编码**
		- 在 Settings 配置工具白名单 / 审批
		- 调试：Output 面板 → 「MCP Logs」
- # 代码库索引与搜索
	- [Indexing 说明](https://cursor.com/help/customization/indexing.md)：
		- 打开项目后**自动索引**，约 80% 完成即可用，约每 5 分钟同步
		- 大目录、生成物加入 .cursorignore（.gitignore 会自动尊重）
		- 需要时可 Command Palette → 「Reindex」
	- Agent 搜索策略：
		- **Grep** — 精确符号、正则
		- **Semantic** — 概念性搜索（「认证在哪处理？」）
		- 复杂探索可用 **Subagents**，避免撑爆主对话上下文
- # Cursor CLI
	- [CLI 概览](https://cursor.com/docs/cli/overview.md)：
	  ```shell
	  # Windows 安装
	  irm 'https://cursor.com/install?win32=true' | iex
	  
	  # 交互式
	  agent
	  agent "refactor the auth module to use JWT"
	  
	  # 模式
	  agent --mode=ask
	  agent --plan
	  
	  # 非交互（CI/脚本）
	  agent -p "review these changes for security issues" --output-format text
	  
	  # 会话
	  agent ls
	  agent resume
	  agent --continue
	  ```
	- CLI 会读取 .cursor/rules、AGENTS.md、mcp.json，与 IDE 行为一致。
-
- # 相关参考
	- [Cursor: The best way to code with AI](https://cursor.com/cn)
	  id:: 6a066805-ea9d-4550-ab8d-dce2b0bf32ec
	- [Download - Cursor](https://cursor.com/cn/download)
	  id:: 6a066819-32a5-4f08-baf2-e0a11e6639ee
	- [Cursor · 定价](https://cursor.com/cn/pricing)
		- [Cursor - dashboard](https://cursor.com/dashboard)
	- [Cursor 文档 — 智能体、规则、MCP、技能和 CLI](https://cursor.com/cn/docs)
	  id:: 6a0a952a-4cb9-4da5-bb10-be0d96003b7a
	- [Cursor Pro 国内怎么买？2026 完整攻略 | Pro/Pro+/Ultra 对比 | 含支付宝教程 | DGT Store](https://dgtsell.com/articles/cursor-pro-ultra-china-buy-guide-2026)
-