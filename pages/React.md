public:: true
tags:: 知识库

- # 环境配置
	- [[Node.js]] 安装与配置
		- ((5a7198cb-9b74-47cb-b071-7094bbd2c330))
		- ((69fdbb0a-5e5c-42a4-b0fd-749baacdf7d1))
			- ((69fdbb1a-726e-4c85-bf46-87b0f1201030))
- # 相关概念
	- |简称|说明|
	  |--|--|
	  |SSR|（Server-Side Rendering）服务端渲染|
	  |CSR|（Client-Side Rendering）客户端渲染|
	  |CRA|（Create React App）传统创建React项目的命令方式|
	  |HMR|热模块替换|
- # 命令与使用
	- ## 通过 Vite 创建项目
		- ```powershell
		  // 通过 Vite 创建项目,使用 --template react-ts 选择 TypeScript 模板
		  // Vite 支持多种模板，例如 react、react-ts、vue、svelte 等
		  // 创建一个新的 Vite 项目，并指定使用 React 模板。
		  npm create vite@latest my-react-app -- --template react
		  // 进入到 my-react-app 目录
		  cd my-react-app
		  // （可以简写为 npm i）会根据当前目录下的 package.json 文件，安装所有项目依赖。
		  npm install
		  // 启动开发服务器，按 Ctrl + C 可以停止服务器。
		  npm run dev
		  ```
	- ## 使用传统的 CRA 创建项目
		- ```powershell
		  // 创建项目
		  npx create-react-app my-app
		  // 进入到项目目录
		  cd my-app
		  // 启动项目
		  npm start
		  ```
		- #+BEGIN_IMPORTANT
		  但官方现已推荐 Vite 用于非 SSR 项目，因为 CRA 较慢且维护不活跃。
		  #+END_IMPORTANT
-