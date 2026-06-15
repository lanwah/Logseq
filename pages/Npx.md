tags:: Npm

- # 介绍
	- **npx**（Node Package Execute）是 **包执行器**，从 npm v5.2.0 开始自动附带，它的主要作用是：
		- **直接运行某个 npm 包中的可执行命令**，而无需全局或本地安装该包
		- 执行时会临时下载并运行，运行完毕后通常不保留（除非明确缓存）
		- 非常适合用于那些只需偶尔使用一次的工具，比如 `create-react-app`、`skills add`、`eslint --init` 等
	- **使用场景例子**
		- 使用 `npm install -g vercel`：全局安装 vercel 命令行工具，之后可以随时运行 `vercel`。
		- 使用 `npx vercel`：不全局安装，直接临时下载并运行最新版的 vercel 命令，用完即走。
	- ## 与 [[Npm]] 的关系
		- npx **依赖于 npm**（没有 npm 就没有 npx，因为它是 npm 生态的一部分）
		- npx 的临时执行实际上还是通过 npm 去下载包到缓存目录
		- 两者都可运行命令，但 `npx ...` 更轻量，适合单次任务；`npm run ...` 适合项目中定义好的脚本
-