refrence:: [[Logseq]], [[Advanced Queries]], [[Logseq属性]], [[Logseq模板]]

- [Queries](https://docs.logseq.com/#/page/queries)
-
- # 使用格式说明
	- `{{query ....}}`
-
- # 例子
	- ```markdown
	  // 查询当前任务（Now）
	  {{query(task Now)}}	
	  // 或者
	  {{query (or (task NOW DOING))}}
	  
	  // 查询待办任务（Later）
	  {{query(task Later)}}
	  
	  // 查询已完成任务（Done）
	  {{query(task Done)}}	
	  ```
-
- # 相关参考
	- ((69dd8e81-b49e-474c-bace-1e883e561d62))