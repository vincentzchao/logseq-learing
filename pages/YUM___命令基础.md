## 命令速查
	- ### 查看信息
		- `yum info {list options}` 查看包的信息
		- `yum list {list options}` 查看包的列表
		- yum info 的参数与 yum list 的 一致，man page 搜索 list options
		- ``` sh
		  # 查看包的信息
		  yum info 包名
		  
		  # 查看所有可安装的包
		  yum list available
		  # 查看所有已安装的包
		  yum list installed
		  
		  # 查看所有的 yum 库
		  yum repolist all
		  
		  # 列出可更新的包
		  yum check-update
		  ```
	- ## 清除各种缓存
		- `yum clean {clean options}` 清除各种东西的缓存目录中的缓存
		- man page 搜索 clean options
		- ``` sh
		  ```
- ## SPECIFYING PACKAGE NAMES
	- man page 搜索 `SPECIFYING PACKAGE NAMES` 查看如何指定一个包名。
	- name: 名称
	- ver: 版本
	- rel: 发布版本
	- arch: 指令架构
	- 参见: ((66093f53-593a-47ed-9581-f1a46556fcf4))
	- ``` sh
	  SPECIFYING PACKAGE NAMES
	         A  package can be referred to for install, update, remove, list, info etc with any of the following as
	         well as globs of any of the following:
	  
	                name
	                name.arch
	                name-ver
	                name-ver-rel
	                name-ver-rel.arch
	                name-epoch:ver-rel.arch
	                epoch:name-ver-rel.arch
	  
	                For example: yum remove kernel-2.4.1-10.i686
	                     this will remove this specific kernel-ver-rel.arch.
	  
	                Or:          yum list available 'foo*'
	                     will list all available packages that match 'foo*'. (The  single  quotes  will  keep  your
	                shell from expanding the globs.)
	  ```
	-