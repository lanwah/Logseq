public:: true
tags:: 开发工具, #Node.js, Nrm, Npx, Yarn
refrence:: Nrm
category:: 开发工具

- # 介绍
	- NPM 是 Node.js 的 **官方包管理器**，用于安装、管理、发布 JavaScript 包（库、框架、工具等）。
-
- # 命令
	- ## 常用命令
	  collapsed:: true
		- ```powershell
		  // 查看当前的版本
		  npm -v
		  
		  // 查看最新的最稳定的版本
		  npm view npm version
		  
		  // 查看所有版本，如果列表太长，可以按 Ctrl + C 中断输出。
		  npm view npm versions
		  
		  // 查看具体版本的信息
		  npm info npm@10.9.8
		  
		  // 安装升级特定的版本
		  npm install -g npm@<具体版本号>
		  // 升级到最新版本
		  npm install -g npm@latest
		  
		  // 查看某个包是否已安装
		  npm list <包名>
		  // 例如
		  npm list react-router-dom
		  // 查看所有依赖的树状结构
		  npm list --depth=0
		  
		  // 安装目前最新的稳定版本
		  npm install <包名>
		  // 例如
		  npm install react-router-dom
		  # 安装最新的 v6 版本
		  npm install react-router-dom@6
		  // 查看所有可用版本
		  npm view react-router-dom versions
		  ```
	- ## Npm 配置
		- 语法格式
			- `npm config get/set/delte/list/edit/fix ....`
			- SSL 密钥验证
				- ```powershell
				  // 获取 strict-ssl 配置，默认是 true
				  npm config get strict-ssl
				  
				  // 设置更新 strict-ssl 配置
				  npm config set strict-ssl false
				  ```
				- > [strict-ssl](https://links.jianshu.com/go?to=https%3A%2F%2Fdocs.npmjs.com%2Fcli%2Fv9%2Fusing-npm%2Fconfig%23strict-ssl) - 通过 https 向注册表发出请求时是否进行 SSL 密钥验证，若校验失败，npm 将无法连接到服务器并报错。默认为 `true`。
				  参考： ((69fe9a16-6e50-4edd-8efb-939cae1946c1))
	- # Npm 发布包
		- ## Npm包发布的操作与步骤
		  id:: 6a107882-685b-4e87-b06d-289ba2b527e4
			- ```bash
			  // 1、查看当前发布的包源
			  nrm ls
			  
			  // 确定包源无误后继续下面的操作
			  
			  // 2、确认是否登录，如果没登录，则先进行登录
			  npm whoami
			  
			  // 登录操作，依次输入用户名，密码邮箱
			  npm login
			  // 登出
			  npm logout
			  
			  // 查看当前的最新版本
			  npm view <your_package_name> version
			  
			  // 3、自动更新版本号并打tag，git支持
			  // 补丁（patch）：修复问题，不改变 API # 1.0.0 -> 1.0.1
			  npm version patch
			  // 次要（minor）：新增功能，向下兼容 # 1.0.0 -> 1.1.0
			  npm version minor  
			  // 主要（major）：不兼容的 API 变更 # 1.0.0 -> 2.0.0
			  npm version major   
			  // 执行后会自动更新 package.json 中的 version，并提交一个 commit（如果项目是 Git 仓库），
			  // 同时创建一个 Git tag。
			  // 如果不想自动 commit 和 tag，可以加 --no-git-tag-version 参数
			  npm version patch --no-git-tag-version
			  
			  // 4、执行构建，生成新版本的产物
			  npm run build
			  
			  // 5、发布，上传版本
			  npm publish
			  
			  // 首次发布使用如下命令
			  npm publish --access public
			  
			  // 删除已发布的版本（慎用），发布后 72 小时内可以强制删除某个版本：
			  // 但不推荐，因为一旦有人依赖该版本就会构建失败。更好的做法是发布一个新的修复版本。
			  npm unpublish your-package-name@1.0.1 --force
			  ```
		- ## 本地测试包能否正常安装
		  collapsed:: true
			- 在发布前，可以在本地模拟安装测试（避免发布后才发现问题）
			- ```bash
			  # 生成一个压缩包 .tgz 文件
			  npm pack
			  
			  # 在另一个干净的目录中安装这个 .tgz 文件
			  cd /tmp
			  npm install /path/to/your-package-1.0.0.tgz
			  ```
			-
- # Npm包源
	- ## 包源切换相关命令
		- ```bash
		  // 查看当前的包源
		  npm config get registry
		  
		  // 切换到淘宝源
		  npm config set registry https://registry.npmmirror.com
		  
		  // 切回官方源
		  // npm config set registry https://registry.npmjs.org
		  ```
	- ## 包源管理
		- 请参考：[[Nrm]]
-
- # 相关参考
	- [unable to verify the first certificate 原因及解决方法 - 简书](https://www.jianshu.com/p/def279a1d2c3)
	  id:: 69fe9a16-6e50-4edd-8efb-939cae1946c1
	- [npm | Home](https://www.npmjs.com/)
	- [npm search](https://www.npmjs.com/search?q=react)
	- [前端技术选型时有用的网站 - 饭特稠 - 博客园](https://www.cnblogs.com/imgss/p/18183877)
		- [Bundlephobia | Size of npm dependencies](https://bundlephobia.com/)
		- [Smart Npm Package Comparison with AI Insights](https://npm-compare.com/)
-
-