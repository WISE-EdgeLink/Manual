
## WebAccess




![](MQTT_webaccessserver.png)

- **Group ID**: Group ID由WebAccess Cloud的工程名称和SCADA名称中间以下划线"\_"连接组合而成，例如: MyProject\_MySCADA。

- **Device ID**: 工程在WebAccess Cloud中的设备名称。
 
- **心跳周期**: 客户端向服务器端发送心跳信息的周期。

- **上传开关**: 是否由上传开关控制数据上传。

- **Timestamp**: 此选项用于设置发布的报文中的时间戳表示格式，UTC Time表示以UTC时间表示，Local Time表示以设备的本地时间表示。举例来说，如果设备的时区设定为东8区（即北京时间），报文的发送时间是北京时间2018年1月1日上午11:30:45，那么以UTC Time表示将会是2018-01-01T03:30:45+0000，而以Local Time表示将会是2018-01-01T11:30:45+0800。

### 其他配置说明

[点表配置说明](./others/TagList_Setting.html)   

[断点续传配置说明](./others/resume.html)

[点表导入导出配置说明](./others/excel.html)

