refrence:: [[Claude Code]]

- # 记忆系统
	- #+BEGIN_NOTE
	  Claude Code 有两套记忆系统。
	  #+END_NOTE
	- ## CLAUDE.md（人工维护）
		- | 类型 | 路径 | 作用域 |
		  | ---- | ---- | ---- |
		  | Project | `./CLAUDE.md` | 团队共享，可提交 git |
		  | Personal | `~/.claude/CLAUDE.md` | 你自己，跨所有项目 |
		  | Local | `./CLAUDE.local.md` | 你自己，当前项目（不提交 git） |
		- ## Auto Memory（Claude 自动记录）
			- 路径：`~/.claude/projects/<项目>/memory/MEMORY.md`
			- Claude 在工作时自己写笔记：调试经验、构建命令、发现的偏好
			- 每个项目独立，不会混淆
		- ## 核心区别
			- || CLAUDE.md | Auto Memory |
			  | ---- | ---- | ---- |
			  | 谁写 | 你 | Claude |
			  | 内容 | 指令和规范 | 学到的模式和反馈 |
			  | 触发写入 | 人工编辑 | 你说"记住..."、你纠正它、Claude 觉得值得记 |
		- ## 写入时机
			- | 记忆类型 | 何时写入 |
			  | ---- | ---- |
			  | CLAUDE.md | 你手动编辑，或 `/init` 生成 |
			  | Auto Memory | 你说"记住..." / 你纠正 Claude / Claude 判断有价值 |
		- ## 加载规则
			- **CLAUDE.md**：每次会话完整加载
			- **Auto Memory**：前 200 行或 25KB 加载（取较小值），超出内容按需读取
			- #+BEGIN_TIP
			  简单理解：CLAUDE.md 是团队手册，Auto Memory 是 Claude 的个人笔记本。
			  #+END_TIP