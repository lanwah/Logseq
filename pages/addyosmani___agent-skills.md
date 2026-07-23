tags:: #Skill

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** #addyosmani/agent-skills
	- **使用协议：** #MIT license
	- **开源地址：** https://github.com/addyosmani/agent-skills
	- **开发语言：** JavaScript 63.8%+Shell 35.0%+Other 1.2%
- # 项目介绍
	- **agent-skills** 是 Google Chrome 工程负责人 Addy Osmani 发起的一个开源项目[](https://developer.aliyun.com/article/1745190)[](https://github.com/addyosmani/agent-skills)，旨在为 AI 编程助手提供一套**生产级的工程技能（Skills）**[](https://github.com/addyosmani/agent-skills)[](https://github.com/addyosmani/agent-skills/blob/main/README.md)。
	- 简单来说，这个项目把资深软件工程师开发时的**工作流、质量门禁和最佳实践**，打包成了AI可以理解和执行的标准化流程[](https://github.com/addyosmani/agent-skills)。它的目标是把AI从“只会写代码”的助手，变成能**像资深工程师一样思考和交付**的可靠伙伴[](https://developer.aliyun.com/article/1745190)。
- # 核心功能：8个命令与24个技能
	- 项目提供了 **8 个斜杠命令（Slash Commands）**，覆盖了从创意到上线的完整生命周期[](https://github.com/addyosmani/agent-skills)[](https://github.com/addyosmani/agent-skills/blob/main/README.md)：
	  | 阶段 | 命令 | 核心原则 |
	  | ---- | ---- | ---- |
	  | **定义 (Define)** | `/spec` | 先写规范，再写代码[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **计划 (Plan)** | `/plan` | 拆解为小型、原子化的任务[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **构建 (Build)** | `/build` | 增量式构建，一次只做一部分[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **验证 (Verify)** | `/test` | 测试是代码工作的证明[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **审查 (Review)** | `/review` | 合并前进行代码审查[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **性能 (Web Perf)** | `/webperf` | 优化前先进行性能测量[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **简化 (Simplify)** | `/code-simplify` | 清晰胜于奇技淫巧[](https://github.com/addyosmani/agent-skills/blob/main/README.md) |
	  | **交付 (Ship)** | `/ship` | 更快的交付更安全 |
	- 在这些命令背后，是 **24个具体的技能（Skills）**[](https://developer.aliyun.com/article/1745190)。以下列举部分核心技能[](https://github.com/addyosmani/agent-skills)：
		- **需求与设计**：`interview-me`（通过提问厘清模糊需求）[](https://github.com/addyosmani/agent-skills)、`idea-refine`（将模糊想法转化为具体方案）[](https://github.com/addyosmani/agent-skills)、`spec-driven-development`（编写PRD）[](https://github.com/addyosmani/agent-skills)。
		- **构建与编码**：`test-driven-development`（强制执行红-绿-重构的TDD流程）[](https://github.com/addyosmani/agent-skills)、`incremental-implementation`（进行小批量、可回滚的增量实现）[](https://github.com/addyosmani/agent-skills)、`frontend-ui-engineering`（涵盖组件、设计系统、可访问性的前端工程化）[](https://github.com/addyosmani/agent-skills)。
		- **审查与质量**：`code-review-and-quality`（从五个维度进行代码审查）[](https://github.com/addyosmani/agent-skills/blob/main/README.md)、`doubt-driven-development`（对高风险决策进行对抗性审查）[](https://github.com/addyosmani/agent-skills)。
		- **专项角色 (Agents)**：项目还内置了**代码审查员、测试工程师、安全审计员**等特定角色（Personas），可被调用来执行专项任务[](https://github.com/addyosmani/agent-skills)。
- # 相关参考
	- [GitHub 58.9K星，Google大佬写了个CLAUDE.md，程序员慌了](https://mp.weixin.qq.com/s/NJNKi9qEue2c81AuWj890A)