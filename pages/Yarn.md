tags:: Npm

- # 介绍
	- `yarn` 是一个由 Facebook（现 Meta）在 2016 年推出的 **JavaScript 包管理器**，与 `npm` 功能类似，主要用于管理项目的依赖包。它最初是为了解决早期 npm 的一些性能和安全性问题而诞生的，如今依然拥有不少忠实用户。
	- ## 核心特点
		- **速度快**：早期版本通过**并行下载**和**本地缓存**，比当时的 npm 快很多（现在 npm 也大幅优化了，但 yarn 依然很流畅）。
		- **确定性安装**：通过 `yarn.lock` 文件确保每次安装得到的依赖树**完全相同**（npm 后来也加入了 `package-lock.json`，但 yarn 的算法更早成熟）。
		- **离线模式**：安装过一次的包会缓存在本地，下次即使没网也能安装。
		- **工作区（Workspaces）**：原生支持**单仓库多包**（monorepo），管理大型项目非常方便。
		- **简洁的命令行**：比如 `yarn add` 代替 `npm install --save`，`yarn upgrade` 等。
	- ## 常用命令对比
	  
	  | 功能 | npm | yarn |
	  | ---- | ---- | ---- |
	  | 安装全部依赖 | `npm install` | `yarn` 或 `yarn install` |
	  | 添加生产依赖 | `npm install <pkg>` | `yarn add <pkg>` |
	  | 添加开发依赖 | `npm install -D <pkg>` | `yarn add -D <pkg>` |
	  | 全局安装 | `npm install -g <pkg>` | `yarn global add <pkg>` |
	  | 移除依赖 | `npm uninstall <pkg>` | `yarn remove <pkg>` |
	  | 更新依赖 | `npm update` | `yarn upgrade` |
	  | 运行脚本 | `npm run <script>` | `yarn <script>` |
	- ## 版本说明
		- **Yarn Classic (v1.x)**：最广泛使用的版本，与 npm 生态完全兼容，命令稳定。
		- **Yarn Berry (v2/v3/v4)**：从 v2 开始引入巨大变化（如 Plug'n'Play 零 node_modules 模式），但兼容性不如 v1，因此很多团队仍停留在 v1。
	- ## 该用 yarn 还是 npm？
		- **新项目**：两者都可以，现代 npm 已经非常成熟。如果你喜欢简洁的命令行或需要原生工作区，可选 yarn v1。
		- **已有项目**：跟随项目现有的锁文件（`yarn.lock` 或 `package-lock.json`），不要混用包管理器。
		- **团队协作**：统一使用同一种包管理器，避免锁文件冲突。
- # 安装与使用
	- 如果你想快速尝试 yarn，可以先全局安装：
	  ```bash
	  npm install -g yarn   # 用 npm 安装 yarn
	  ```
	-