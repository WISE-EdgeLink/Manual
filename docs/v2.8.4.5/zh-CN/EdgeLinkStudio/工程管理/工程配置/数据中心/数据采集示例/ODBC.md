## ODBC设备
1. 在设备界面选择设备类型为ODBC-MSSQL，可以配置通过在线ODBC服务器采集数据![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714014679046-71fc1365-96e8-4b7c-93cb-6fcdc7db0566.png#from=url&id=ZgKP5&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
2. 在设备界面中输入ODBC服务配置![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714014679132-453d4d6b-2b5d-4bd3-8684-1c0d6479093c.png#from=url&id=MSKxM&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
   1. 服务器IP地址.
   2. SQL Server的版本，可选择SQL Server2008、SQL Server2005、SQL Server2000等
   3. 登陆SQL Server服务器需要的用户名。
   4. 登陆SQL Server服务器需要的密码。
   5. 需要登录的数据库名名称。
3. 数据采集脚本![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714014679222-5372aea4-2949-4192-a3f5-a299702700bc.png#from=url&id=kq2xO&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)点击Tag点编辑界面的地址栏可以编辑数据采集的SQL脚本。其中"SQL脚本"中输入SQL查询教本，"列名称"中输入查询结果的列名称。
