public:: true
tags:: 开发工具, #Node.js 
category:: 开发工具

- # 介绍
	- NPM 是 Node.js 的 **官方包管理器**，用于安装、管理、发布 JavaScript 包（库、框架、工具等）。
-
- # 命令
	- ## 常用命令
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
-
- # 相关参考
	- [unable to verify the first certificate 原因及解决方法 - 简书](https://www.jianshu.com/p/def279a1d2c3)
	  id:: 69fe9a16-6e50-4edd-8efb-939cae1946c1