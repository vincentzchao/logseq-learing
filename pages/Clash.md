tags:: [[网络代理]]
---

-
- ## 如何设置代理忽略
	- 参考: [mac配置clashx代理忽略列表](https://wonderlq.github.io/archives/87d77c17.html)
	- 1、在 `~/.config/clash/` 新建 `proxyIgnoreList.plist` 文件。
	- 2、编辑文件，内容如下：
		- ``` xml
		  <?xml version="1.0" encoding="UTF-8"?>
		  <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
		  <plist version="1.0">
		  <array>
		      <string>192.168.0.0/16</string>
		      <string>10.0.0.0/8</string>
		      <string>172.16.0.0/12</string>
		      <string>127.0.0.1</string>
		      <string>localhost</string>
		      <string>*.docker-cn.com</string>
		      <string>*.cn</string>
		  </array>
		  </plist>
		  ```
	- 3、编辑保存后，重启 clashx 即可。