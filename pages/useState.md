tags:: React, React Hook

- # 介绍
	- `useState` 是一个 React Hook，它允许你向组件添加一个 [状态变量](https://zh-hans.react.dev/learn/state-a-components-memory)。
- # state 识别
	- 哪些是 state 呢？标记出那些不是的:
		- 随着时间推移 **保持不变**？如此，便不是 state。
		- 通过 props **从父组件传递**？如此，便不是 state。
		- 是否可以基于已存在于组件中的 state 或者 props **进行计算**？如此，它肯定不是state！
- # 相关参考
	- [useState – React 中文文档](https://zh-hans.react.dev/reference/react/useState)
-