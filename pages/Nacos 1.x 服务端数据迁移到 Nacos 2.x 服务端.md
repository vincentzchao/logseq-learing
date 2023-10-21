tags:: [[Nacos]]
---

- ## 直接迁移 data 目录会遇到的问题
	- 先执行 `sh ${NACOS_HOME}/bin/shutdown.sh` 将 旧 Nacos 1.x 服务端 关闭。
	  logseq.order-list-type:: number
	- 将 Nacos 1.x 服务端根目录的 `data` 目录，复制到新的 Nacos 2.x 服务端根目录。
	  logseq.order-list-type:: number
	- 执行 `sh ${NACOS_HOME}/bin/startup.sh -m standalone` 启动新的  Nacos 2.x 服务端 。
	  logseq.order-list-type:: number
	- 打开 Web 端查看配置时，会出现如下错误：
	  logseq.order-list-type:: number
		- ``` crystal
		  caused: PreparedStatementCallback; bad SQL grammar [SELECT id,data_id,group_id,tenant_id,app_name,content,md5,gmt_create,gmt_modified,src_user,src_ip,c_desc,c_use,effect,type,c_schema,encrypted_data_key FROM config_info WHERE data_id=? AND group_id=? AND tenant_id=?]; nested exception is java.sql.SQLSyntaxErrorException: Column 'ENCRYPTED_DATA_KEY' is either not in any table in the FROM list or appears within a join specification and is outside the scope of the join specification or appears in a HAVING clause and is not in the GROUP BY list. If this is a CREATE or ALTER TABLE statement then 'ENCRYPTED_DATA_KEY' is not a column in the target table.;caused: Column 'ENCRYPTED_DATA_KEY' is either not in any table in the FROM list or appears within a join specification and is outside the scope of the join specification or appears in a HAVING clause and is not in the GROUP BY list. If this is a CREATE or ALTER TABLE statement then 'ENCRYPTED_DATA_KEY' is not a column in the target table.;caused: Column 'ENCRYPTED_DATA_KEY' is either not in any table in the FROM list or appears within a join specification and is outside the scope of the join specification or appears in a HAVING clause and is not in the GROUP BY list. If this is a CREATE or ALTER TABLE statement then 'ENCRYPTED_DATA_KEY' is not a column in the target table.;
		  ```
		- 这是因为 Nacos 2.x 服务端数据读取内嵌的 `Derby` 时，会读 `encrypted_data_key` 字段。
		- 所以 `config_info`, `config_info_beta`, `his_config_info` 三个表都要增加 `encrypted_data_key` 字段。
		- 参见: [Nacos -配置加密](https://nacos.io/zh-cn/docs/v2/plugin/config-encryption-plugin.html)
- ## 修改 Derby 表结构进行迁移
	- 先执行 `sh ${NACOS_HOME}/bin/shutdown.sh` 将 旧 Nacos 1.x 服务端 关闭。
	  logseq.order-list-type:: number
	- 将 Nacos 1.x 服务端根目录的 `data` 目录，复制到新的 Nacos 2.x 服务端根目录。
	  logseq.order-list-type:: number
	- 使用如下命令新增字段。 ==参见 [[Derby]] 查看如何执行 sql .==
	  logseq.order-list-type:: number
		- ``` sql
		  ALTER TABLE NACOS.config_info ADD COLUMN encrypted_data_key LONG VARCHAR;
		  ALTER TABLE NACOS.config_info_beta ADD COLUMN encrypted_data_key LONG VARCHAR;
		  ALTER TABLE NACOS.his_config_info ADD COLUMN encrypted_data_key LONG VARCHAR;
		  ```
	- 执行 `sh ${NACOS_HOME}/bin/startup.sh -m standalone` 启动新的  Nacos 2.x 服务端 。
	  logseq.order-list-type:: number
	- 打开 Web 端查看配置时，发现一切正常。
	  logseq.order-list-type:: number
- ##