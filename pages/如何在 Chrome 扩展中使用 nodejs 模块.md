tags:: [[Chrome Extension]], [[Browserify]]
---

-
- ## 问题描述
	- 想要开发一款可以接收邮件内容的 chrome 扩展，所以需要用到 nodejs 的 [mail-listener2](https://github.com/chirag04/mail-listener2) 库。
	- 但是在浏览器中，没有 nodejs 环境，所以需要有个办法，将我需要的 nodejs 库转成浏览器能够执行的 js 文件。
- ## 解决方案
	- 使用 `Browserify` 将 nodejs 库及其依赖打包成一个 js 文件。
	  logseq.order-list-type:: number
	- 将此文件复制到 chrome 扩展项目中使用。
	  logseq.order-list-type:: number
- ## 操作步骤
	- 执行 `npm install browserify -g` 安装 Browserify .
	  logseq.order-list-type:: number
	- logseq.order-list-type:: number
-
- ---
- ## 参考
	- [在谷歌插件中使用nodejs模块](https://stableship.github.io/2015/10/07/%E5%9C%A8%E8%B0%B7%E6%AD%8C%E6%8F%92%E4%BB%B6%E4%B8%AD%E4%BD%BF%E7%94%A8nodejs%E6%A8%A1%E5%9D%97/)
	  logseq.order-list-type:: number
-