tags:: [[Package Manager]]
alias:: [[RPM Package Manager]]
---

- ## 官方资料
	- [RPM 官网](https://rpm.org/index.html)
- ## 概念
	- 原名: Red Hat Package Manager
	- RPM 文件的扩展名为 `.rpm`。
	- RPM 包由一个存档文件组成，其中包含了一个特定包的库和依赖关系，这些库和依赖关系与系统上安装的其他包不冲突。
	- 当使用 RPM 命令安装一个软件包时，你必须提供 `.rpm` 软件包的确切位置
- ## 命令速查
	- ### 查看安装文件位置
		- ``` sh
		  # 查找已安装应用的rpm文件名称
		  rpm -q 软件名称
		  # 查找rpm文件安装时产生的文件路径
		  rpm -ql rpm文件名称/软件名称
		  ```
-