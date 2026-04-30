tags:: .NET CLI
category:: 开发工具
public:: true

- #+BEGIN_IMPORTANT
  可以从运行 .NET 5 或更高版本的应用程序读取计数器。
  #+END_IMPORTANT
- # 安装与使用
	- 查看GC 模式
	  id:: 69f2a46a-80b0-49a3-bd5a-454d8a9972ad
		- ```bash
		  # 安装（如未安装）
		  dotnet tool install --global dotnet-counters
		  
		  # 监视你的进程
		  dotnet-counters monitor -p <进程ID> --refresh-interval 1
		  ```
		- 在输出的 `System.Runtime` 段中，你会直接看到一条 `gc-mode` 指标：
			- 值 `0` 代表 **Workstation**
			- 值 `1` 代表 **Server**
-
- # 相关参考
	- [dotnet-counters 诊断工具 - .NET CLI - .NET | Microsoft Learn](https://learn.microsoft.com/zh-cn/dotnet/core/diagnostics/dotnet-counters)