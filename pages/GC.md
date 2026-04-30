tags:: .NET
category:: 文章
public:: true

-
- # GC的类型
	- 在 .NET 中，垃圾回收器（GC）的类型主要可以从**两种工作模式（Workstation / Server）**和**两种回收策略（Background / Non-Concurrent）**来划分。
	- ## 按工作模式划分
		- |**GC类型**|**关键特点**|
		  |--|--|
		  |Workstation GC|为客户端应用优化，侧重快速响应，减少UI冻结。|
		  |Server GC|为服务器应用优化，侧重**高吞吐量**，伸缩性更好。|
		- **Workstation GC（工作站模式）**：为桌面、WinForms等客户端应用设计，也是独立应用的默认模式。其核心目标是**快速响应**，通过频繁但短暂的回收来避免长时间的用户界面冻结。它在触发GC的用户线程上并发执行，能有效减少UI卡顿，适合单处理器或处理器核心较少的机器。
		- **Server GC（服务器模式）**：为ASP.NET Core等需要高吞吐量的服务端应用设计，也是这些应用的默认模式。其核心目标是**最大化吞吐量**，倾向于较少但更彻底的回收，会分配更多内存以获得更高性能。它会为每个逻辑处理器创建独立的GC堆和**高优先级**的专用线程来并行工作，回收速度更快，但也更消耗资源，适合多核服务器环境。
	- ## 按回收策略划分
		- |**GC类型**|**关键特点**|
		  |--|--|
		  |Background GC|执行第2代回收时，可并发收集第0、1代，**减少暂停时间**。|
		  |Non-Concurrent GC|回收时会**挂起所有托管线程**，直到过程结束。|
		- **Background GC（后台/并发GC）**：这是现代.NET (4.0+)的**默认模式**，用于取代旧的并发GC。它在进行最耗时的**第2代回收**时，会使用专门的线程在后台进行，此时应用程序线程**无需挂起**，可以继续运行。不过，对于第0代和第1代的回收，仍需短暂挂起所有托管线程。
		- **Non-Concurrent GC（非并发GC）**：在这种模式下，一旦触发GC，所有相关的托管线程都会被**挂起**，直到回收任务完全结束。这种方式可能导致程序暂停时间更长，但在某些场景下（如减少上下文切换）能获得更高性能。在.NET Framework 4及更早版本中，服务器模式默认就是非并发的。
		- #+BEGIN_TIP
		  小提示：“后台(Background)”与“前台(Foreground)”是对应的概念。后台GC通常指Gen 2的回收，而在此期间触发的Gen 0/1回收会被称为前台GC，执行时仍需短暂挂起线程。
		  #+END_TIP
		- 工作模式GC和回收策略GC之间的默认关系
			- | 版本 | Workstation GC | Server GC |
			  | ---- | ---- | ---- |
			  | .NET 2.0-3.5 | 旧式并发 GC | 串行 GC |
			  | **.NET 4.0** | ✅ **Background GC（默认）** | 串行 GC |
			  | **.NET 4.5+** | Background GC | ✅ **Background GC（默认）** |
			- #+BEGIN_TIP
			  现在的 .NET（.NET Core 3.0+、.NET 5+）两种 GC 模式默认都是 **Background GC**，不需要额外配置就能享受低暂停的好处。
			  #+END_TIP
	- ## 按代际回收划分
		- |**GC类型**|**典型暂停时间**|**大小（参考）**|**关键特点**|
		  |--|--|--|--|
		  |`Generation 0  `|< 1ms ~ 几毫秒|~256KB-4MB|新创建的小对象，[:br]回收最频繁。|
		  |`Generation 1  `|几毫秒 ~ 10ms|~几MB|从 Gen 0 幸存的对象，[:br]作为缓冲代。|
		  |`Generation 2  `   |几十毫秒 ~ 几百毫秒|~几十MB-几GB|长期存活的对象和大对象[:br]（Large Object Heap, LOH）|
		- 大对象堆（LOH）
			- 单独管理（通常 ≥ 85KB 的对象）。
			- 只在 Gen 2 回收时处理，默认不压缩（.NET 4.5.1+ 可配置压缩）。
-
- # GC的发展
	- | .NET 版本 | GC 特性 |
	  | ---- | ---- | ---- |
	  | 2.0-3.5 | 串行 GC + 旧并发 GC |
	  | 4.0+ | Background GC（进化版并发） |
	  | .NET Core 2.1+ | G1 GC 可选、GC 调优增强 |
	  | .NET 6+ | 分代合并、部分区域回收优化 |
	- 具体时间线：
		- **.NET Framework 4.0**（2010年）引入 Background GC
		- 之前是 **.NET 2.0-3.5** 的老式并发 GC（Background 是进化版）
		- .NET 4.5+ 的 Background GC 更成熟，支持 **Background Server GC**
-
- # 相关代码
	- ```C#
	  Console.WriteLine($"IsServerGC: {GCSettings.IsServerGC}");
	  Console.WriteLine($"LatencyMode: {GCSettings.LatencyMode}");
	  
	  // LatencyMode 枚举值
	  // Batch        - 禁用并发，暂停时间长（Server GC 旧默认）
	  // Interactive  - 启用并发（Workstation GC 旧默认）
	  // LowLatency   - 尽量避免 GC，慎用
	  // SustainedLowLatency - 尽量避免 Full GC
	  // NoGCRegion   - 禁止 GC 区域
	  
	  using System;
	  
	  // 1. 工作模式：是否为 Server GC
	  bool isServerGC = System.Runtime.GCSettings.IsServerGC;
	  Console.WriteLine($"GC 模式: {(isServerGC ? "Server" : "Workstation")}");
	  
	  // 2. 后台/并发 GC 是否启用 (.NET Core / .NET 5+)
	  string concurrentSetting = AppContext.GetData("System.GC.Concurrent") as string;
	  bool isBackgroundGC = concurrentSetting == "true"; // 注意区分大小写，通常为 "true"/"false"
	  Console.WriteLine($"后台 GC 启用: {isBackgroundGC}");
	  
	  // 3. （辅助参考）当前延迟模式
	  System.Runtime.GCLatencyMode latencyMode = System.Runtime.GCSettings.LatencyMode;
	  Console.WriteLine($"延迟模式: {latencyMode}");
	  // 典型的可预测对应关系：
	  // Workstation 默认：Interactive（后台GC开启）
	  // Server 默认：     Interactive（后台GC开启）
	  // 若设为 SustainedLowLatency 或 Batch 时，后台GC可能被临时调整
	  ```
	-
	- ## 配置
		- 如果你希望手动配置，可以通过项目文件 (`.csproj`) 或运行时配置文件 (`runtimeconfig.json`) 进行。在 `.csproj` 文件中，一个同时启用Server GC和后台并发GC的推荐高性能配置如下：
			- ```xml
			  <PropertyGroup>
			    <!-- 启用Server GC: 可选值 true (server) / false (workstation) -->
			    <ServerGarbageCollection>true</ServerGarbageCollection>
			    <!-- 启用后台并发GC: 可选值 true (background) / false (non-concurrent) -->
			    <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
			  </PropertyGroup>
			  ```
		- App.config中配置
			- ```xml
			  <configuration>
			    <runtime>
			      <!-- 启用服务器 GC -->
			      <gcServer enabled="true"/>
			      <!-- 启用并发/后台 GC（工作站模式默认开启） -->
			      <gcConcurrent enabled="true"/>
			      <!-- 压缩 LOH（.NET 4.5.1+） -->
			      <gcAllowVeryLargeObjects enabled="true"/>
			    </runtime>
			  </configuration>
			  ```
			- 相关参考 `configuration/runtime`
				- ((69f2a6ab-c76d-4fdc-9044-ccae52470b0a))
-
- # 相关工具
	- 通过 [[性能计数器 (dotnet-counters)]] [[.NET CLI]] 工具查看
	  {{embed ((69f2a46a-80b0-49a3-bd5a-454d8a9972ad))}}
		- #+BEGIN_IMPORTANT
		  ==限制：== dotnet-counters 只支持 .NET Core 3.0+ / .NET 5+
		  #+END_IMPORTANT
-