tags:: #图形

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** Zenith.NET
	- **使用协议：** [[MIT license]]
	- **开源地址：** https://github.com/qian-o/Zenith.NET
	- **开发语言：** C# 79.3%+CSS 8.6%+Slang 7.6%+JavaScript 4.5%
- # 项目介绍
	- **[Zenith.NET](https://zenith.net/)** 是一个为 .NET 生态打造的新一代**渲染硬件接口（RHI）**。它的核心目标是提供一套**统一、现代的 C# API**，让你能通过相同的代码逻辑，无缝调用 **DirectX 12、Metal 4 和 Vulkan 1.4** 这三个主流底层图形 API[](https://github.com/qian-o/Zenith.NET)[](https://raw.githubusercontent.com/qian-o/Zenith.NET/master/README.md)。
	- 简单来说，你可以把它看作是一个为 .NET 开发者设计的、跨平台的“图形与计算”通用翻译层。
	- ## ✨ 核心特性
		- **统一的现代 API**：提供了一套一致的 C# API，用于管理资源、渲染管线、命令录制、同步和显示等核心操作[](https://github.com/qian-o/Zenith.NET)[](https://raw.githubusercontent.com/qian-o/Zenith.NET/master/README.md)。
		- **全面的计算能力**：除了标准的图形光栅化，还支持**通用计算（Compute Shader）** 和**间接命令（Indirect Commands）**，适合 GPU 驱动的渲染管线[](https://github.com/qian-o/Zenith.NET)[](https://raw.githubusercontent.com/qian-o/Zenith.NET/master/README.md)。
		- **可选的高级特性**：支持**内联光线追踪（Inline Ray Tracing）** 和**网格着色（Mesh Shading）**，但官方建议在使用前通过 `Capabilities` 检查硬件是否支持[](https://github.com/qian-o/Zenith.NET)[](https://raw.githubusercontent.com/qian-o/Zenith.NET/master/README.md)。
		- **Bindless 资源与显式同步**：通过无绑定（Bindless）资源句柄暴露着色器资源，并使用队列（Queues）、屏障（Barriers）和纹理布局（Texture Layouts）来精确控制指令的执行顺序和资源访问依赖[](https://github.com/qian-o/Zenith.NET)[](https://raw.githubusercontent.com/qian-o/Zenith.NET/master/README.md)。
	- ## 💻 平台支持
		- [Zenith.NET](https://zenith.net/) 通过不同的后端，实现了对主流桌面和移动平台的广泛支持[](https://github.com/qian-o/Zenith.NET)[](https://raw.githubusercontent.com/qian-o/Zenith.NET/master/README.md)：
		  | 平台 | DirectX 12 | Metal 4 | Vulkan 1.4 |
		  | ---- | ---- | ---- |
		  | **Windows** | ✅ 支持 |  | ✅ 支持 |
		  | **Apple (macOS, iOS等)** |  | ✅ 支持 | ✅ 支持 |
		  | **Android** |  |  | ✅ 支持 |
		  | **Linux** |  |  | ✅ 支持 |
- # 相关参考
	- [Zenith.NET v0.0.7：Metal 后端落地，.NET GPU 抽象的跨平台旅程 - o王先生o - 博客园](https://www.cnblogs.com/xymfblogs/p/19805856)