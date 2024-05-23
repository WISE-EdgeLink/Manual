## ODBC设备

1. 在设备界面选择设备类型为ODBC-MSSQL，可以配置通过在线ODBC服务器采集数据

	![](ODBC_Device.png)

2. 在设备界面中输入ODBC服务配置

	![](ODBC_Extension.png)

	1. 服务器IP地址.
	2. SQL Server的版本，可选择SQL Server2008、SQL Server2005、SQL Server2000等
	3. 登陆SQL Server服务器需要的用户名。
	4. 登陆SQL Server服务器需要的密码。
	5. 需要登录的数据库名名称。

3. 数据采集脚本

	![](ODBC_Tag_Address.png)

	点击Tag点编辑界面的地址栏可以编辑数据采集的SQL脚本。
	
	其中"SQL脚本"中输入SQL查询教本，"列名称"中输入查询结果的列名称。