tags:: #Skill, #grill-me

-
- # 开源信息
	- **开源平台：** GitHub
	- **项目名称：** mattpocock/skills
	- **使用协议：** MIT license
	- **开源地址：** https://github.com/mattpocock/skills
	- **开发语言：** Shell 77.2%+JavaScript 22.8%
- # 项目介绍
	- **mattpocock/skills** 是 **Matt Pocock** 开源的个人 AI 编程 Agent 技能集，项目口号是 **"Skills for Real Engineers"**（为真正的工程师准备的技能）[](https://github.com/mattpocock/skills)[](https://github.com/mattpocock/skills/blob/main/README.md)。
	- Matt Pocock 是 **TypeScript 社区知名专家**、Total TypeScript 创始人，也是 AI 教育平台 [aihero.dev](https://aihero.dev/) 的创办者。这个仓库里放的是他**每天实际使用**的 AI 编码技能，目前已有超过 **4.4万 Star**，订阅其更新的开发者超过 **6 万人**[](https://github.com/mattpocock/skills/blob/main/README.md)。
- # 技能列表
	- 仓库将技能分为 **Engineering（工程）** 和 **Productivity（生产力）** 两大类，每类又分为用户主动调用的和模型自动调用的[](https://github.com/mattpocock/skills/blob/main/README.md)。
	- ## 🛠 Engineering Skills（工程技能）
	  
	  | 技能 | 类型 | 作用 |
	  | ---- | ---- | ---- |
	  | `ask-matt` | 用户调用 | 路由器——询问当前场景该用哪个技能[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `setup-matt-pocock-skills` | 用户调用 | 一次性配置（问题追踪器、标签、文档目录）[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `to-spec` | 用户调用 | 将对话转化为规范文档并发布到问题追踪器[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `to-tickets` | 用户调用 | 将计划/spec 拆解为可独立执行的任务清单[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `implement` | 用户调用 | 按 spec 或 tickets 构建代码，驱动 TDD，提交前跑 code review[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `wayfinder` | 用户调用 | 规划超大规模工作（超过单次 Agent 会话容量），用问题追踪器作为共享地图[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `triage` | 用户调用 | 用状态机管理 issue 的流转[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `improve-codebase-architecture` | 用户调用 | 扫描代码库，生成可视化 HTML 报告，指出可优化的架构点[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `grill-with-docs` | 用户调用 | 带文档构建的"拷问"式讨论，同步更新 CONTEXT.md 和 ADR[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `tdd` | 模型调用 | 测试驱动开发，红-绿-重构循环[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `diagnosing-bugs` | 模型调用 | 结构化调试：复现→最小化→假设→埋点→修复→回归测试[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `code-review` | 模型调用 | 双轴审查：规范符合度 + 代码标准（含 Fowler 代码坏味基线）[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `codebase-design` | 模型调用 | 设计"深模块"的规范与词汇——小接口背后的大行为[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `domain-modeling` | 模型调用 | 构建和打磨领域模型，挑战术语、压力测试边界场景[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `prototype` | 模型调用 | 构建一次性原型来回答设计问题[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `research` | 模型调用 | 基于高可信一手来源调研，产出带引用的 Markdown 文档[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `resolving-merge-conflicts` | 模型调用 | 逐块解决 git merge/rebase 冲突[](https://github.com/mattpocock/skills/blob/main/README.md) |
	- ## ⚡ Productivity Skills（生产力技能）
	  
	  | 技能 | 类型 | 作用 |
	  | ---- | ---- | ---- |
	  | `grill-me` | 用户调用 | 被 relentlessly 拷问计划或设计，直到决策树所有分支都被解决[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `handoff` | 用户调用 | 将当前对话压缩为交接文档，让另一个 Agent 可以继续工作[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `teach` | 用户调用 | 跨多会话教用户新技能或概念[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `writing-great-skills` | 用户调用 | 编写高质量 Skill 的参考指南[](https://github.com/mattpocock/skills/blob/main/README.md) |
	  | `grilling` | 模型调用 | 拷问循环——`grill-me` 和 `grill-with-docs` 背后的可复用逻辑 |
- # 相关参考
	- [又一个神级 Skill 夯爆了 。](https://mp.weixin.qq.com/s/--SWV1bxShL2DpCGks22TQ)
	- [2026年，Superpowers 可能不再是 Claude/Codex/Workbuddy 的最佳方案了（附实操建议）](https://mp.weixin.qq.com/s/go4FB051BFRagNl-IvXknA) #obra/superpowers
-