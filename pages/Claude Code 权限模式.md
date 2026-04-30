refrence:: [[Claude Code]]

- ((69e02c5b-d57f-4289-9e0a-72861753305c))
- ((69df6234-3018-479b-b0f2-a4e357928fa7))
-
- # 支持的权限模式
	- | 模式 |Claude 无需询问即可执行的操作 | 最适合 |
	  |--|--|--|
	  | `default` |读取文件 | 入门、敏感工作 |
	  | `acceptEdits` |读取和编辑文件，[:br]受保护目录除外 | 迭代您正在审查的代码 |
	  | [`plan`](https://code.claude.com/docs/zh-CN/permission-modes#analyze-before-you-edit-with-plan-mode) | 读取文件 | 探索代码库、规划重构 |
	  | [`auto`](https://code.claude.com/docs/zh-CN/permission-modes#eliminate-prompts-with-auto-mode) | 所有操作，带后台安全检查 | 长时间运行的任务、减少提示疲劳 |
	  | [`bypassPermissions`](https://code.claude.com/docs/zh-CN/permission-modes#skip-all-checks-with-bypasspermissions-mode) | 除受保护目录外的所有操作 | 仅隔离容器和 VM |
	  | [`dontAsk`](https://code.claude.com/docs/zh-CN/permission-modes#allow-only-pre-approved-tools-with-dontask-mode) | 仅预先批准的工具 | 锁定环境 |
-
- # 配置说明
	- 方式一：按 Shift + Tab 循环切换权限模式
		- #+BEGIN_NOTE
		  default → acceptEdits → plan
		  #+END_NOTE
		- > **在会话期间**：按 `Shift+Tab` 循环切换 `default` → `acceptEdits` → `plan` → `auto`。当前模式显示在状态栏中。在启动时传递 `--enable-auto-mode` 之前，`auto` 不会出现在循环中。Auto 还需要 Team、Enterprise 或 API 计划和 Claude Sonnet 4.6 或 Opus 4.6，因此即使使用该标志，该选项也可能保持不可用。如果同时启用了 `bypassPermissions`，它会出现在 `plan` 和 `auto` 之间的循环中。
	- 方式二：**启动时**：将模式作为 CLI 标志传递
		- ```powershell
		  // 启用计划模式
		  claude --permission-mode plan
		  
		  // 启用允许编辑模式
		  claude --permission-mode acceptEdits
		  
		  // 启用不询问模式
		  claude --permission-mode bypassPermissions
		  
		  // 启用自动模式
		  claude --permission-mode auto
		  ```
-
- # 相关参考
	- [选择权限模式 - Claude Code Docs](https://code.claude.com/docs/zh-CN/permission-modes)
	  id:: 69e02c5b-d57f-4289-9e0a-72861753305c
	- [计划模式 – Claude 中文 - Claude AI 开发技术社区](https://claudecn.com/docs/claude-code/workflows/plan-mode/)
	  id:: 69df6234-3018-479b-b0f2-a4e357928fa7
-