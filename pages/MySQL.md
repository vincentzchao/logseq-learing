tags:: [[RDBMS]]
---

-
- ## 历史
	- ### 读音
		- 参考: [MySQL究竟怎么发音？ - 蒋川的回答 - 知乎](https://www.zhihu.com/question/49011669/answer/2243496686)
		-
- ## 命令速查
	- ### 数据库参数相关
		- ``` sql
		  -- 查询数据版本
		  select version();
		  ```
	- ### SQL最大大小
		- ``` sql
		  -- 查询MySQL支持的最大SQL字符串大小，单位为 Byte
		  select @@max_allowed_packet;
		  ```
	- ### 数据库参数
		- ``` sql
		  -- 查看全局的变量
		  show global variables;
		  -- 查看当前会话的变量
		  show variables;
		  ```
-