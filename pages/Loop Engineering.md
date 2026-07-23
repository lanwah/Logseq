tags:: #AI

- # 介绍
	- **Loop Engineering（循环工程）** 是2026年AI工程领域兴起的一个新范式。它的核心思想是：**从“手动提示AI”转变为“设计一个能让AI自动循环工作的系统”**。
	- 你可以把它理解为AI Agent（智能体）时代的“流水线”[](https://cloud.tencent.com.cn/developer/article/2686804?policyId=1003)。传统方式是你手动给AI派活、检查、再派活，你自己是工作循环的一部分[](https://cloud.tencent.com.cn/developer/article/2693819?from=15425&frompage=seopage)；而Loop Engineering则是你设计好一套流程和规则，让AI Agent自己发现任务、执行、验证、修正，直到达成目标[](https://cloud.tencent.com.cn/developer/article/2693819?from=15425&frompage=seopage)，你则从具体操作者变成了系统设计者[](https://hub.baai.ac.cn/view/56014)。
	- ## 核心组件
	  一个完整的Loop工程通常包含以下关键部分[](https://hub-assets-cache.baai.ac.cn/view/55505)：
		- **自动化触发器 (Automations)**：按计划（如定时）或事件自动启动工作循环[](https://zhidx.com/p/565982.html#comments)。
		- **工作树 (Worktrees)**：为并行的多个Agent提供独立的工作空间，防止互相干扰[](https://zhidx.com/p/565982.html#comments)。
		- **技能包 (Skills)**：将项目规范、代码风格、历史经验等打包，供Agent参考，避免重复学习[](https://zhidx.com/p/565982.html#comments)。
		- **插件与连接器 (Plugins & Connectors)**：让Agent能调用外部工具（如数据库、API）[](https://zhidx.com/p/565982.html#comments)。
		- **子Agent (Sub-agents)**：由多个 specialized Agent 分工协作完成复杂任务[](https://cloud.tencent.com.cn/developer/article/2696935?policyId=1004)。
		- **记忆层 (Memory)**：跨会话的记忆，让Agent能积累经验[](https://zhidx.com/p/565982.html#comments)。
- # 相关参考
	- [提示词工程已死，Loop Engineering来了！](https://mp.weixin.qq.com/s?__biz=MzIyNjM2MzQyNg==&mid=2247723482&idx=1&sn=52522523fc778c878f71c1d9061535e3&scene=21&poc_token=HDGHXGqjbm67xPbdhRMo0ImD2N3RCyIFr6gbotyN)
	- [重磅！Loop Engineering 实操手册公开](https://mp.weixin.qq.com/s/kICrdEkPCYAiyOiwI-Gt1Q)