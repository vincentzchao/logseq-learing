tags:: [[Package Manager]], [[Free Software]] 
alias:: [[RPM Package Manager]]
---

- ## 官方资料
	- [RPM 官网](https://rpm.org/index.html)
- ## 学习路线
	- 什么 RPM，其原理是啥: [[RPM Concept]]
	  logseq.order-list-type:: number
- ## 学习进度
-
- ## 命令速查
	- ### 查看安装文件位置
		- ``` sh
		  # 查找已安装应用的rpm文件名称
		  rpm -q 软件名称
		  # 查找rpm文件安装时产生的文件路径
		  rpm -ql rpm文件名称/软件名称
		  # 查找指定rpm包的文档 
		  rpm -qd rpm文件名称/软件名称
		  ```
-