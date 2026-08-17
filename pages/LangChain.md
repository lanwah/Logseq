tags:: #AI

- # 介绍
	- LangChain 是一个用于开发基于大型语言模型（LLM）的应用程序的开源框架。它诞生于2022年10月[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)，由哈佛大学的 Harrison Chase 发起，旨在解决将大模型能力应用到实际场景中的复杂性[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)。如今，它已成为全球最受欢迎的大模型开发框架之一[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)。
	- ## 🧱 核心思想：像“搭积木”一样构建AI应用
		- LangChain的核心思想是提供一套高度模块化、可复用的组件[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)，让开发者可以像“搭积木”一样，将这些组件“链接”在一起，从而快速构建复杂的AI应用[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)。它**自身并不开发大模型**，而是为各种LLM（如GPT、千问等）提供统一的接口[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)。
	- ## ⚙️ 主要组件：构建AI应用的“积木”
		- LangChain将AI应用的构建过程抽象为一系列可组合的组件。以下是其核心组件：
		  | 组件类别 | 核心作用 | 关键组件/概念 | 典型应用场景 |
		  | ---- | ---- | ---- |
		  | **模型 (Models)** | AI推理与生成[](https://docs.langchain.com/oss/python/langchain/component-architecture) | 聊天模型、LLM、嵌入模型[](https://docs.langchain.com/oss/python/langchain/component-architecture) | 文本生成、语义理解[](https://docs.langchain.com/oss/python/langchain/component-architecture) |
		  | **提示 (Prompts)** | 引导模型响应的结构化输入 | 提示模板 (Prompt Templates) | 优化模型输出，构建特定任务指令 |
		  | **链 (Chains)** | 将多个组件按顺序链接，形成一个工作流 | LCEL (LangChain 表达式语言)[](https://cloud.tencent.com.cn/developer/article/2683052) | 构建RAG、多步推理等复杂流程 |
		  | **检索器 (Retrievers)** | 从外部数据源查找相关信息 | 向量检索器、网页检索器[](https://docs.langchain.org.cn/oss/javascript/langchain/component-architecture) | RAG（检索增强生成）、知识库搜索 |
		  | **记忆 (Memory)** | 在多轮对话中保留上下文 | 对话历史、自定义状态[](https://docs.langchain.com/oss/python/langchain/component-architecture) | 构建有状态的聊天机器人[](https://docs.langchain.com/oss/python/langchain/component-architecture) |
		  | **智能体 (Agents)** | 自主决策、编排和推理[](https://docs.langchain.com/oss/python/langchain/component-architecture) | ReAct智能体、工具调用智能体[](https://docs.langchain.org.cn/oss/javascript/langchain/component-architecture) | 处理非确定性工作流、自动调用工具[](https://docs.langchain.com/oss/python/langchain/component-architecture) |
		  | **工具 (Tools)** | 赋予模型调用外部API、数据库等的能力[](https://docs.langchain.com/oss/python/langchain/component-architecture) | 网络搜索、数据计算[](https://docs.langchain.org.cn/oss/javascript/langchain/component-architecture) | 让模型能获取实时信息、执行操作 |
		  | **文档处理 (Document Processing)** | 加载、分割和转换各种格式的文档 | 文档加载器、文本分割器[](https://docs.langchain.com/oss/python/langchain/component-architecture) | 处理PDF、网页等非结构化数据[](https://docs.langchain.com/oss/python/langchain/component-architecture) |
		  | **向量存储 (Vector Stores)** | 存储和搜索文本的向量表示 | Chroma, FAISS, Pinecone[](https://docs.langchain.com/oss/python/langchain/component-architecture) | 为检索器提供语义搜索能力 |
		- ## 🔧 工作原理：组件如何协同工作
			- 这些组件通过两种主要方式协同工作[](https://cloud.tencent.com.cn/developer/article/2683052)：
				- **链式调用 (Chains)**：这是LangChain最基础的工作模式。开发者可以将一系列操作（如“检索文档” -> “构建提示” -> “调用模型” -> “解析输出”）定义为一个“链”。前一步的输出自动成为下一步的输入，从而将复杂任务分解为可管理的步骤。
				- **智能体 (Agents)**：这是一种更高级的编排方式[](https://docs.langchain.com/oss/python/langchain/component-architecture)。智能体本身由LLM驱动，能够根据用户的指令，**自主决定**需要调用哪些“工具”、以什么顺序调用，以及如何解读返回的结果[](https://cloud.tencent.com.cn/developer/article/2591045?from=15425&frompage=seopage)。
			-
- # 官方网站
	- [Deep Agents 概述 - LangChain 文档 - LangChain 教程](https://docs.langchain.org.cn/oss/python/deepagents/overview)