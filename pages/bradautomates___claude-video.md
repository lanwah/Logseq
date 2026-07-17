tags:: #Skill #视频

- # 开源信息
	- **开源平台：** GitHub
	- **项目名称：** bradautomates/claude-video
	- **使用协议：** MIT license
	- **开源地址：** https://github.com/bradautomates/claude-video
	- **开发语言：** Python 94.9%+Shell 5.1%
- # 项目介绍
	- **bradautomates/claude-video** 是一个开源的 **Agent Skill**，它通过一个 `/watch` 命令，让 Claude 获得了“观看”视频的能力[](https://github.com/bradautomates/claude-video)。该项目由 Brad Bonanno 开发[](https://github.com/bradautomates/claude-video)，采用 MIT 开源协议[](https://github.com/bradautomates/claude-video)。一经推出便迅速走红，成为 GitHub Trending 上单周涨星最快的项目之一（单周新增 7800+ 星），目前已有 **8.5k Star**[](https://github.com/bradautomates/claude-video)。
	- 该项目在 Plugin Marketplace 中注册的**核心技能只有一个**，即：
		- **`watch`**（调用命令为 `/watch`）
		  不过，这个 `/watch` 技能内部提供了 **4 种不同的运行模式（Detail Modes）**，你可以把它们理解为该技能的“子模式”或“策略”。以下是完整列表：
		- 核心技能： `watch` （视频观看与分析）
		  | 模式名称 | 提取策略 | 帧数上限 | 适用场景 |
		  | ---- | ---- | ---- |
		  | **`transcript`** | **纯字幕模式**（不抽取任何帧） | 0 帧 | 只需快速浏览文本内容、不关心画面细节时（**最快、几乎零图像Token成本**） |
		  | **`efficient`** | **关键帧提取**（基于场景变化，稀疏采样） | 50 帧 | 快速了解视频全貌、概览核心视觉内容（**性价比最高，速度极快**） |
		  | **`balanced`** | **场景切换检测**（识别镜头变化，更密集采样） | 100 帧 | 常规分析，需要兼顾画面细节和成本（**官方推荐模式**） |
		  | **`token-burner`** | **全量场景切换**（无上限，尽可能捕捉所有变化） | 无上限（取决于视频长度） | 需要深度分析每一处细节、排查微小 Bug 或逐帧审查（**图像Token消耗最大**） |
	- ### 补充说明
		- **使用时如何选择：** 在触发 `/watch` 命令时，你不需要手动输入模式代码。Claude 会根据你提出的问题自动选择最合适的模式（例如，问“总结大意”会用 `transcript`；问“哪里出错了”会用 `balanced` 或 `token-burner`）。你也可以在提问时主动指定，例如：“用高效模式分析这个视频”。
		  id:: 6a56dd4e-b088-4f34-97af-8d9c40680fef
		- **调用方式**：在 Claude Code 中安装插件后，直接在对话中输入 `/watch` 并附上视频链接或本地路径即可。
- # 相关参考
	- [这个 Skill 让 Claude Code 看懂视频，还挺实用的。](https://mp.weixin.qq.com/s/44vend3pxxq8lx_62s08uw)
-
-