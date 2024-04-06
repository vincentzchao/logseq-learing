## 概念
	- 原全称为 `Red Hat Package Manager` , 后来由于一些非 Red Hat 的 Linux 发行版本也在使用, 则把全称改为 `RPM Package Manager` (递归命名方式) 。
	- 当使用 RPM 命令安装一个软件包时，你必须提供 `.rpm` 软件包的确切位置 。
- ## RPM 包名
  id:: 66093f53-593a-47ed-9581-f1a46556fcf4
	- 以 `amanda-2.6.1p2-7.el6.x86_64.rpm` 为例
	- ![image.png](../assets/image_1711882543593_0.png)
	- `release` 是打包者添加的发布信息。
		- 这里的 `7` 表示这个包发布了 7 次 (可能要修复 bug)
		- `el6` 表示 **Red Hat Enterprise Linux 6** 。
- ## 使用 RPM 命令安装 package 会发生什么
	- 将 package 中的文件放置到系统中的相应位置。
	  logseq.order-list-type:: number
	- 将 package 的 metadata 储存到本地 RPM 数据库。
	  logseq.order-list-type:: number
	- 在某些情况，会执行脚本以配置这个 package 。
	  logseq.order-list-type:: number
-
- ## 参考
	- [rpm_tutorial_20120831.pdf](https://access.redhat.com/sites/default/files/attachments/rpm_tutorial_20120831.pdf)
	  logseq.order-list-type:: number
	-
-