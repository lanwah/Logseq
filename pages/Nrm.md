public:: true
tags:: Node.js, Npm
category:: 开发工具

- # 介绍
	- **nrm (NPM Registry Manager) 是一个命令行工具，用于帮助开发者快速、方便地查看和切换 npm 的镜像源（registry）。**
	- 简单来说，当你发现用 `npm install` 命令安装依赖包速度很慢，或者因为网络问题导致失败时，可以使用 nrm 快速切换到速度更快的国内镜像源，比如淘宝源，从而加速下载[](https://www.itzhai.com/tags/nrm/)。
- # 如何安装
	- 在安装 nrm 之前，请确保你的电脑上已经安装了 **Node.js** 和 **npm**[](https://www.webzsky.com/archives/1524)。
	- **执行安装命令**：输入以下命令进行全局安装[](https://www.npmjs.com/package/nrm)。
		- `npm install -g nrm`
	- **验证安装成功**：安装完成后，运行 `nrm --version` 命令。如果成功输出了版本号（例如 `1.2.6`），就说明 nrm 已经安装好了[](https://www.webzsky.com/archives/1524)。
- # 相关命令
	- ## 常用命令介绍
		- ```bash
		  // 列出所有源，查看所有可用的镜像源，当前使用的源前面会有 * 标记。
		  nrm ls
		  
		  // 切换源，一键切换到指定的镜像源，例如 nrm use taobao
		  nrm use <源名称>
		  
		  // 测试源速度，测试所有源的响应速度，帮助你选择最快的镜像。
		  nrm test
		  
		  // 添加自定义源，你可以添加自己公司内部的私有 npm 仓库地址。
		  nrm add <源名称> <源地址>
		  
		  // 删除源，用于删除不再需要的自定义镜像源。
		  nrm del <源名称>
		  ```
-