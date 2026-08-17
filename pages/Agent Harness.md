tags:: #AI, #Agent

- # 介绍
	- 这是目前AI圈最火的概念之一，可以通俗地理解为 **“AI的缰绳”** 。它指**在大模型（LLM）外围构建的一整套工程化的辅助、约束与治理系统**。
	- 一个广为流传的公式可以很好地概括其核心：**Agent = Model + Harness**[](https://www.geekpark.net/news/362530)[](https://m.zhidx.com/p/562998.html#comments)。它解决了大模型虽然能力强大但“不受控”的问题[](https://www.geekpark.net/news/362530)，通过为模型套上“马具”[](https://news.qq.com/rain/a/20260726A08UIN00)，使其能**稳定、安全、可靠地**完成复杂的现实任务[](https://m.bkeconomy.com/detail/1775178643129477.html)。
	- 一个完整的 **Agent Harness** 通常包含以下几个关键层级[](http://stockfinance.sina.cn/stock/go.php/paper/reportid/833578260294/index.phtml?vt=4&autocallup=no&isfromsina=no)：
		- **🧭 调度与编排 (Orchestration)**：规划任务步骤，决定信息如何在不同的子Agent间流动。
		- **🛠️ 工具调用 (Tool Calling)**：赋予AI调用外部API、操作软件、读写文件等实际动手的能力。
		- **🧠 记忆管理 (Memory Management)**：让AI能记住历史对话和关键信息，实现跨任务的上下文关联[](http://stockfinance.sina.cn/stock/go.php/paper/reportid/833578260294/index.phtml?vt=4&autocallup=no&isfromsina=no)。
		- **🔒 安全与治理 (Safety & Governance)**：设定权限、审计日志、沙箱隔离，确保AI的操作安全合规[](http://stockfinance.sina.cn/stock/go.php/paper/reportid/833578260294/index.phtml?vt=4&autocallup=no&isfromsina=no)。
		- **🔍 可观测性 (Observability)**：监控AI的每一步操作和决策过程，便于调试和优化[](http://stockfinance.sina.cn/stock/go.php/paper/reportid/833578260294/index.phtml?vt=4&autocallup=no&isfromsina=no)。
		- **✅ 验证与评估 (Validation & Evaluation)**：建立反馈闭环，检查AI的工作结果是否正确，并在出错时进行纠正。
- # 相关参考
	- [新 ClaudeCode 和 Codex 变得越来越强的 5 个 Harness 设计](https://mp.weixin.qq.com/s/IjjkJorQU_HZDRdEuVoNJQ)