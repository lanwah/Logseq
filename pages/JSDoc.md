tags:: JavaScript

- # 介绍
	- JSDoc 是一种基于 JavaScript 的文档注释规范，通过特定格式的标签（如 `@param` `@returns`）描述代码的功能、参数、返回值等信息。
	- ## 核心价值：
		- 编辑器智能提示：VS Code/WebStorm 会解析 JSDoc 注释，提供精准的参数类型、返回值提示，减少语法错误；
		- 代码可维护性：结构化注释让他人（或未来的你）快速理解代码用途，无需通读实现逻辑；
		- 自动文档生成：通过 jsdoc 工具可将注释直接生成 HTML 文档，无需手动编写接口文档；
		- 类型补充：在纯 JavaScript 项目中，可替代 TypeScript 实现基础类型校验。
	-
- # 官方网站
	- ((6a12f9a3-a956-4f1f-8ae4-87a1248edbcf))
	- ((6a12f9c4-577a-4346-afcd-a77ff57d4374))
- # 用法举例
	- ## 1. 基础函数注释（@param + @returns）
		- 最常用的场景，描述函数的参数、返回值和使用示例：
		  ```javascript
		  /**
		   * 计算两个数字的和（支持整数/小数）
		   * @param {number} a - 第一个加数（必填）
		   * @param {number} [b=0] - 第二个加数（可选，默认值0）
		   * @returns {number} 两个数字的和
		   * @example
		   * add(1, 2) // 返回 3
		   * add(5) // 返回 5（使用默认值）
		   */
		  function add(a, b = 0) {
		    return a + b;
		  }
		  ```
	- ## 2. 变量类型声明（@type）
		- 标记变量的类型，帮助IDE提供智能提示：
		  
		  ```javascript
		  /**
		   * 当前登录的用户ID（支持字符串/数字类型）
		   * @type {string | number}
		   */
		  const userId = 1001;
		  
		  /**
		   * 用户列表数组（数组元素为指定结构的对象）
		   * @type {Array<{id: string, name: string, age: number}>}
		   */
		  const userList = [
		    { id: 'u1', name: '张三', age: 20 }
		  ];
		  ```
	- ## 3. 自定义复杂类型（@typedef + @property）
		- 复用复杂的对象类型，减少重复注释：
		  
		  ```javascript
		  /**
		   * 商品信息类型定义
		   * @typedef {Object} Product
		   * @property {number} id - 商品唯一ID
		   * @property {string} name - 商品名称
		   * @property {number} price - 商品价格（单位：元）
		   * @property {boolean} [inStock=true] - 是否有库存（可选，默认有库存）
		   */
		  
		  /**
		   * 显示商品信息（复用上面定义的Product类型）
		   * @param {Product} product - 商品对象
		   * @returns {string} 格式化的商品信息
		   */
		  function showProduct(product) {
		    return `${product.name} - ￥${product.price}`;
		  }
		  ```
	- ## 4. 类与构造函数注释（@class）
		- 描述类的作用、构造参数和方法：
		  
		  ```javascript
		  /**
		   * 用户类，用于创建用户实例
		   * @class
		   * @param {string} name - 用户名（长度2-10字符）
		   * @param {number} age - 年龄（范围1-120）
		   */
		  class User {
		    constructor(name, age) {
		      this.name = name;
		      this.age = age;
		    }
		  
		    /**
		     * 获取用户的完整信息
		     * @returns {string} 格式化的用户信息
		     */
		    getInfo() {
		      return `${this.name}（${this.age}岁）`;
		    }
		  }
		  ```
	- ## 5. 异步函数与错误处理（@async + @throws）
		- 描述异步函数的返回值和可能抛出的错误：
		  
		  ```javascript
		  /**
		   * 异步获取用户列表
		   * @async
		   * @param {number} [pageSize=10] - 每页条数（默认10）
		   * @param {number} [pageNum=1] - 页码（默认1）
		   * @returns {Promise<{list: Array<{id: string, name: string}>, total: number}>} 
		   *          用户列表和总条数（Promise类型）
		   * @throws {Error} 当网络请求失败时抛出错误
		   */
		  async function fetchUserList(pageSize = 10, pageNum = 1) {
		    const res = await fetch(`/api/users?pageSize=${pageSize}&pageNum=${pageNum}`);
		    if (!res.ok) throw new Error('网络请求失败');
		    return res.json();
		  }
		  ```
	- ## 6. 标记废弃代码（@deprecated）
		- 提示开发者不再使用该函数，并说明替代方案：
		  
		  ```javascript
		  /**
		   * 旧版登录方法（已废弃）
		   * @deprecated v2.0.0 起请使用 `loginV2()` 方法（支持验证码+密码登录）
		   * @param {string} username - 用户名
		   * @param {string} password - 密码
		   * @returns {boolean} 是否登录成功
		   */
		  function login(username, password) {
		    // 旧逻辑（不推荐继续使用）
		    return true;
		  }
		  ```
		- ## 7. 标记待完成功能（@todo）
			- 记录代码中需要后续优化或补充的功能：
			  
			  ```javascript
			  /**
			   * 计算两个数的乘积
			   * @param {number} a - 第一个数
			   * @param {number} b - 第二个数
			   * @returns {number} 乘积结果
			   * @todo 1. 增加对大数相乘的溢出处理 2. 补充负数相乘的边界测试
			   */
			  function multiply(a, b) {
			    return a * b;
			  }
			  
			  ```
		- ## 其他示例
			- ```javascript
			    /** @type {{sentenceMsg:string;onCommitData:Function;rest:object}} */
			    const { sentenceMsg, onCommitData, ...rest } = props;
			  ```
- # 相关参考
	- [Use JSDoc: Index](https://jsdoc.app/)
	  id:: 6a12f9a3-a956-4f1f-8ae4-87a1248edbcf
	- [JSDoc 中文网](https://jsdoc.nodejs.cn/)
	  id:: 6a12f9c4-577a-4346-afcd-a77ff57d4374
	- [一文吃透 JSDoc 注释规范-CSDN博客](https://blog.csdn.net/weixin_45497805/article/details/154825397)