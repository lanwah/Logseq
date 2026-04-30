refrence:: [[Claude Code]]

- # 命令类型
	- 命令的类型和存放路径
	  | 类型 | 路径 | 作用域 | 提示显示 |
	  | ---- | ---- | ---- | ---- |
	  | 项目命令 | `.claude/commands/` | 仅当前项目 | 显示"(project)" |
	  | 个人命令 | `~/.claude/commands/` | 所有项目 | 显示"(user)" |
	- #+BEGIN_IMPORTANT
	  文件名即命令名，例如 optimize.md 对应 /optimize
	  #+END_IMPORTANT
- # 命令关键字
	- Claude Code 自定义命令的 Frontmatter 关键字。
	- **Frontmatter 配置项**
	  | 关键字 | 必填 | 说明 | 示例 |
	  | ---- | ---- | ---- | ---- |
	  | `description` | 否 | 命令简短描述，显示在 `/help` 列表中 | `description: 审查代码安全漏洞` |
	  | `allowed-tools` | 否 | 指定命令可使用的工具 | `allowed-tools: Read, Grep, Bash(git:*)` |
	  | `model` | 否 | 指定执行命令的模型 | `model: sonnet`（可选 sonnet/opus/haiku） |
	  | `argument-hint` | 否 | 参数提示，用户补全时显示 | `argument-hint: [pr-number] [priority]` |
	  | `disable-model-invocation` | 否 | 是否禁用程序化调用（仅手动触发） | `disable-model-invocation: true` |
	- **动态变量**
	  | 变量 | 说明 | 示例 |
	  | ---- | ---- | ---- |
	  | `$ARGUMENTS` | 捕获所有传入参数 | `/fix-issue 123 high` → `$ARGUMENTS` = "123 high" |
	  | `$1`, `$2`, `$3`... | 捕获第1、2、3个位置参数 | `/review-pr 456 alice` → `$1`="456", `$2`="alice" |
	- **特殊语法**
	  | 语法 | 说明 | 示例 |
	  | ---- | ---- | ---- |
	  | `@文件路径` | 引用文件内容到命令上下文 | `Review @src/app.cs` |
	  | ``!command`` | 执行 Bash 命令获取动态上下文 | ``!git status`` |
- # 例子
	- Git 提交命令
	  
	  ```markdown
	  <!-- .claude/commands/commit.md -->
	  ---
	  description: 智能Git提交
	  allowed-tools: Bash(git add:*), Bash(git status:*), Bash(git commit:*)
	  ---
	  
	  ## 当前状态
	  !`git status`
	  
	  ## 未暂存改动
	  !`git diff`
	  
	  ## 最近提交
	  !`git log --oneline -5`
	  
	  基于改动创建 conventional commit 格式的提交。
	  ```
-