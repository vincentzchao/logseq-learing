tags:: [[环境变量]]
---

- ## 环境变量配置文件
	- ### macOS
		- #### 使用 bash 时配置文件加载顺序
			- ``` sh
			  # ===========  系统级环境变量配置
			  # 全局环境变量配置
			  /etc/profile
			  
			  # 指定 shell 的环境变量配置
			  /etc/bashrc
			  
			  # macOS 特有的环境变量配置，用于配置 path 变量
			  /etc/paths
			  # paths.d 目录下的每一个文件的每一行都会被作为 path 变量的一个目录
			  /etc/paths.d/xxx
			  
			  # =========== 用户级环境变量配置(不同用户使用独立的配置文件)
			  # 以下文件如果不存在，则往下查找; 如果存在，则忽略后面的文件
			  ~/.bash_profile
			  ~/.bash_login
			  ~/.profile
			  ```
		- #### 使用 zsh 时配置文件加载顺序
			- 参见 [[zsh]] 的 **Startup Files**
	- ### Linux
		- ``` sh
		  # ===========  系统级环境变量配置
		  # 全局环境变量配置
		  /etc/profile
		  
		  # 指定 shell 的环境变量配置
		  /etc/bashrc
		  
		  # =========== 用户级环境变量配置(不同用户使用独立的配置文件)
		  ~/.bashrc
		  ~/.bash_login
		  ~/.profile
		  ```
- ## 查看环境变量
	- 使用 [[export command]] 可以查看所有环境变量 .
	- 执行 `echo $PATH` 可以查看 `PATH` 变量 .
- ## PATH 变量
	- ### 增加路径
		- ``` sh
		  # 在配置文件中添加如下格式的内容
		  export PATH="你要添加的路径:$PATH"
		  ```
- ## 查看命令的路径
	- `which 你的命令` 和 `whereis 你的命令` 可以查看命令的路径
- ## 参考
	- [macOS/Linux 环境变量设置](https://zhuanlan.zhihu.com/p/25976099)
	  logseq.order-list-type:: number