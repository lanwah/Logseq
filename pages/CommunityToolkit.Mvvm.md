tags:: #.NET #MVVM #WPF #WinForms

- # 开源信息
	- **开源平台：** #GitHub
	- **项目名称：** #CommunityToolkit.Mvvm
	- **使用协议：** [[MIT license]]
	- **开源地址：** https://github.com/CommunityToolkit/dotnet
	- **开发语言：** C# 100%
- # 项目介绍
	- .NET Community Toolkit 是微软维护并发布的一套开源辅助库和 API 集合。它隶属于 .NET Foundation，最大的特点是不依赖任何特定的 UI 框架，这意味着无论是控制台应用、Web 服务还是桌面应用，任何 .NET 开发者都可以使用它。
	- 这个仓库中的许多库原本是 Windows Community Toolkit 的一部分，后来被抽取出来形成了这套通用工具包，在微软内部也被大量用于第一方应用（如新版 Microsoft Store）的开发中。
	- ## 核心组件
	  | 包名 | 说明 |
	  | ---- | ---- | ---- |
	  | **`CommunityToolkit.Common`** | 一组被其他 CommunityToolkit 库共享的辅助 API[](https://github.com/CommunityToolkit/dotnet) |
	  | **`CommunityToolkit.Diagnostics`** | 提供 `Guard` 和 `ThrowHelper` 等 API，用于更简洁、高效且不易出错的参数验证和错误检查[](https://github.com/CommunityToolkit/dotnet) |
	  | **`CommunityToolkit.HighPerformance`** | 面向高性能场景的辅助工具集合，包含池化缓冲区、`Memory2D`/`Span2D`、字符串池、位操作辅助等[](https://github.com/CommunityToolkit/dotnet) |
	  | **`CommunityToolkit.Mvvm` (MVVM Toolkit)** | 一个快速、模块化、平台无关的 MVVM 库，是知名库 `MvvmLight` 的官方继任者[](https://github.com/CommunityToolkit/dotnet)。在 Microsoft Store 等第一方应用中广泛使用 |
	- MVVM Toolkit 利用了 **Source Generators（源代码生成器）** 来大幅减少样板代码。
	- ## 主要特点
		- **UI 框架无关**：可以在任何 .NET 应用或库中使用，不绑定 WinForms、WPF、MAUI 等特定 UI 平台[](https://github.com/CommunityToolkit/dotnet)
		- **现代化高性能**：充分利用了最新的 .NET 性能特性，包含大量零分配、低开销的 API
		- **微软官方维护**：由微软团队维护，并在微软内部产品中得到了实战验证[](https://github.com/CommunityToolkit/dotnet)
		- **开源社区驱动**：接受社区贡献，持续根据反馈迭代改进
- # 官方文档
	- [入门指南 - Getting Started with the Windows Community Toolkit - Windows Community Toolkit | Microsoft Learn](https://learn.microsoft.com/zh-cn/windows/communitytoolkit/getting-started)
	- [完整文档 - .NET 社区工具包文档 - Community Toolkits for .NET | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/communitytoolkit/)
	- [API参考 - .NET API browser | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/api/?view=dotnet-comm-toolkit-8.4)
- # 相关参考
	- ((6a01d39f-3fb0-4e54-98ae-649071298829))