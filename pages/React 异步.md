tags:: React

- # 介绍
	- 在 React 中实现“异步线程休眠”本质上就是延迟执行一段代码，同时不阻塞 UI 线程。JavaScript 本身没有 `sleep` 函数，但可以通过 `Promise` + `setTimeout` 模拟。
- # 实现
	- ```javascript
	  const sleep = (ms) => new Promise(resolve => setTimeout(resolve, ms));
	  ```
	- ## 使用示例
		- ### 1. 事件处理函数中休眠（如点击按钮后延迟更新）
			- ```jsx
			  import { useState } from 'react';
			  
			  function DelayedCounter() {
			    const [count, setCount] = useState(0);
			  
			    const handleClick = async () => {
			      await sleep(1000);          // 等待 1 秒
			      setCount(prev => prev + 1); // 然后更新状态
			    };
			  
			    return <button onClick={handleClick}>延时 +1</button>;
			  }
			  ```
		- ### 2. 在  `useEffect`  中休眠（例如轮询、顺序动画）
			- ```jsx
			  import { useEffect, useState } from 'react';
			  
			  function DelayedEffect() {
			    const [data, setData] = useState(null);
			  
			    useEffect(() => {
			      let isCancelled = false;  // 防止组件卸载后仍执行状态更新
			  
			      const fetchWithDelay = async () => {
			        await sleep(2000);       // 模拟网络延迟或等待
			        if (!isCancelled) {
			          setData('延迟加载的数据');
			        }
			      };
			  
			      fetchWithDelay();
			  
			      return () => { isCancelled = true; };
			    }, []);
			  
			    return <div>{data || '加载中...'}</div>;
			  }
			  ```
		- ### 3. 带取消控制的延时轮询
		- ```jsx
		  import { useEffect, useState } from 'react';
		  
		  function PollingComponent() {
		    const [status, setStatus] = useState('waiting');
		  
		    useEffect(() => {
		      const abortController = new AbortController();
		  
		      const poll = async () => {
		        for (let i = 1; i <= 5; i++) {
		          if (abortController.signal.aborted) return;
		          setStatus(`第 ${i} 次轮询`);
		          await sleep(1000);
		        }
		        setStatus('完成');
		      };
		  
		      poll();
		  
		      return () => abortController.abort();
		    }, []);
		  
		    return <div>{status}</div>;
		  }
		  ```
- # 重要注意事项
	- | 问题 | 说明 | 解决方案 |
	  | ---- | ---- | ---- |
	  | **不会阻塞 UI** | `await sleep(...)` 只是暂停当前 `async` 函数的后续代码，不影响 UI 渲染 | 无需特殊处理 |
	  | **组件卸载后更新状态** | 如果在 `sleep` 期间组件被卸载，`setState` 会引发警告/内存泄漏 | 使用取消标记（如 `isMounted` 或 `AbortController`） |
	  | **不要在渲染中直接调用** | 函数组件内部不能直接 `await sleep`（会破坏渲染规则） | 始终放在 `useEffect` 或事件处理函数中 |
	  | **类组件中的使用** | 同样支持，方法内定义 `async` 函数 | 注意检查 `this._isMounted` |
-