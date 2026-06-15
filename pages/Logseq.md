tags:: 日志，知识库，GitHub开源项目，软件工具
license:: AGPL-3.0
category:: 软件工具

-
- # 开源信息
	- **开源平台：** GitHub
	- **项目名称：** logseq
	- **使用协议：** AGPL-3.0 license
	- **开源地址：** ((69f307c0-1e61-4f88-86f2-33e331abf3dc))
- # 项目介绍
	- Logseq是一款基于Markdown的双向链接笔记应用，它不仅提供了简洁易用的界面和丰富的功能，还保持了轻量级的特点。与传统的笔记工具相比，Logseq引入了许多现代化的功能特性，如双向链接、块引用等。
- # 软件目录结构
	- Logseq 目录下的 `journals`、`pages` 和 `logseq` 这三个文件夹的作用。
	  id:: 69d5c12f-13c3-4cfc-97fb-c850b2248b75
	  | 目录 | 作用 | 存储内容举例 |
	  | ---- | ---- | ---- |
	  | **`journals   `** | 存放**日记 (Journal)** 类笔记，[:br]用于时间线记录[](https://blog.gitcode.com/9534517b2a33d1e3d1024197862badd9.html)。 | 如 `2026_04_08.md` 或 `2026-04-08.md`，[:br]每日自动生成[](https://zhuanlan.zhihu.com/p/370299376)。 |
	  | **`pages`** | 存放**普通页面 (Page)**，[:br]用于构建系统的知识网络[](https://blog.gitcode.com/9534517b2a33d1e3d1024197862badd9.html)。 | 如 `项目管理.md` 或 `Python学习笔记.md`，[:br]由你手动创建。 |
	  | **`logseq`** | 存放**应用配置**和**缓存数据**，[:br]是程序运行的"后台"[](https://blog.gitcode.com/9534517b2a33d1e3d1024197862badd9.html)。 | `config.edn` (配置文件)、[:br]`plugins` (插件文件夹)。 |
	- 插件目录：``C:\Users\Fishel\.logseq\plugins``
	  id:: 69e0c9a2-7e1f-4994-a5a6-6643eefe3de7
- id:: 69d73ac4-44a0-4a40-8ac6-f5e04bdcfcf0
- # 官方文档
	- [首页 - Logseq: A privacy-first, open-source knowledge base](https://logseq.com/)
	- [下载 - Logseq: A privacy-first, open-source knowledge base](https://logseq.com/downloads)
	- [GitHub - Logseq](https://github.com/logseq)
	  id:: 69f307c0-1e61-4f88-86f2-33e331abf3dc
	- [文档 - contents](https://docs.logseq.com/#/page/contents)
	- [入门 - tutorial](https://docs.logseq.com/#/page/tutorial)
-
- # 使用技巧
	- ## 快捷键
		- | 快捷键| 功能| 说明|
		  |--|--|--|
		  |Ctrl + B|加粗||
		  |Ctrl + I|斜体||
		  |Ctrl + Shift + H|高亮||
		  |Ctrl + Shift + S|删除线||
		  |Ctrl + L|插入连接||
		  |Ctrl + Enter|切换 Later/Now/Done 任务状态||
		  |Ctrl + K|快速查找||
		  |Ctrl + Shift + T|打开表格编辑器|安装了MTE插件|
		  |Alt + Shift + ↑|向上移动块||
		  |Alt + Shift + ↓|向下移动块||
		  |Tab|向右缩进（成为子块）||
		  |Shift + Tab|向左缩进（成为父块）||
		  |Ctrl + C|复制||
		  |Ctrl + Shift + C|复制选中的文本||
		  |Ctrl + V|粘贴||
		  |Ctrl + Shift + V|粘贴为纯文本||
		  |tt|切换主题||
		- 字母快捷键
			- #+BEGIN_TIP
			  字母快捷键的输入必须在==非输入模式下==（无光标的时候）输入。
			  比如【切换暗/亮主题】在无焦点时按下 ==tt== 即可。
			  #+END_TIP
		- ### 相关参考
			- [Logseq快捷键大全：提升3倍操作效率的隐藏技巧-CSDN博客](https://blog.csdn.net/gitblog_00706/article/details/152058298)
			- [提升Logseq效率的终极指南：快捷键vs鼠标操作速度对比分析-CSDN博客](https://blog.csdn.net/gitblog_00267/article/details/152061876)
	- ## 样式
		- [💅 Logseq自助修改 —— CSS指导手册 - 知乎](https://zhuanlan.zhihu.com/p/548640615)
		- [如何在 Logseq 中自定义字体设置 | 小赵的技术手记](https://zhaochunqi.com/posts/how-to-change-font-in-logseq/)
	- ## 用法
		- Tag（标签）
			- 使用格式说明
			  
			  ```markdown
			  标签以#开头，空格结尾。
			  ```
			- 例子
			  ```markdown
			  #这是一个无空格的标签的写法
			  #[[这是一个带空格的标签写法 注意中间可以有空格]]
			  ```
			- 参考
				- ((69d77c3e-81c0-432f-b51f-9a734be7e4d0))
		- 单行代码
		  collapsed:: true
			- 使用格式说明
			  ```markdown
			  `单行代码内容`
			  ```
			- 例子
			  `单行代码内容`
		- [[Logseq模板]]
		  id:: 69ddc081-58e5-4e53-b2db-b173bc4e3218
		- [[Logseq属性]]
		  id:: 69ddcbd6-6390-40b5-a6d6-f8a034c2fcf5
		- [[Queries查询]]
		  id:: 69df0e78-f0e8-429d-b895-0f6797d3de8f
		- [[Advanced Queries]]
		  id:: 69df11e4-aa9d-414a-802b-15cfeab7396e
		- [[Logseq收藏页面]]
		  id:: 69df4737-f5cc-4463-871b-82fa4ec3b09b
		- [[Logseq任务优先级]]
		  id:: 69df5b06-8147-426e-b53b-47784553cbef
	-
- # 插件推荐
	- 常用插件推荐
	  |插件名称|功能|
	  |--|--|
	  |Markdown Table Editor|Markdown表格插件|
	  |Tags|标签插件|
	  |Bullet Threading|标题连线插件|
-
- # 使用参考
	- [Logseq本地部署完整指南：轻松搭建个人知识库系统 | WMW](https://watermelonwater.tech/insights/%E6%9C%AC%E5%9C%B0%E9%83%A8%E7%BD%B2logseq%E6%9E%84%E5%BB%BA%E4%B8%AA%E4%BA%BA%E7%9F%A5%E8%AF%86%E5%BA%93/)
	- [Logseq：使用一年的感受 - 董川民](https://www.dongchuanmin.com/operate/6141.html)
	- [Logseq 用法备忘-CSDN博客](https://blog.csdn.net/zhzht19861011/article/details/146177595)
	  id:: 69d77c3e-81c0-432f-b51f-9a734be7e4d0
	- [2.3 Logseq查询指南：3个核心技巧，让你的「知识库」检索效率翻倍 - 今日头条](https://www.toutiao.com/article/7475897635422667299/?wid=1776127353518)
	  id:: 69dd8e81-b49e-474c-bace-1e883e561d62
	- [我的 Logseq 使用习惯 | Limboy](https://limboy.me/posts/logseq/)
	  id:: 69e0bcc4-c643-4b17-8eb7-59c6e1ad97eb
	- [10.页属性、块属性、query 的玩法 - 知乎](https://zhuanlan.zhihu.com/p/673835262)
	  id:: 69e0bcee-b18f-4bc2-addb-eecdb454f804
	- [Logseq简介：构建个人知识库的高效工具 - Awesome Top 中文社区](https://awesometop.cn/posts/6412e6fcdd5e4f1bac1399a4442db48f)
-