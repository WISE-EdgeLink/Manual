1. 使用UAExpert测试要连接的OPCUAserver来确认OPCUAserver可以正常使用。
2. Edgelink OPCUA 驱动配置
3. 添加OPCUA驱动

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381428836-bf6f0c77-4211-414b-80da-9af9f1b6ad10.png#)
设备类型: OPCUA
单元号: 和其他设备不冲突即可。
IP和端口: OPCUA server的IP和端口号.
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381428982-8df5109d-fbff-4a36-876e-bd64464150a2.png#)
Use URL as Connection Address: OPCUA Server必须用URL连接时，勾选此处并填写server的URL。
Security Policy and Authentication Setting: 根据server的要求设置。
Certificate and Private Key: 如果server在连接时需要ca和key文件，选择server提供ca和key文件。如没有要求，保持默认的自认证证书即可。
Cyclic rate of subscribing data changes: 驱动中的默认模式是问答模式。如果勾选此处，将改为server主动发送模式：Client给server发送一条消息，让它**周期**检查自己的数据是否有变化，如有变化，主动向client发送。

1. 添加点

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381429165-dc6356c7-86f3-4bc8-b2e6-3889855bed5d.png#)
**地址填写语法为 : ns=<Namespace Index>;<type>=<value>**
**示例**

| **Address Type** | **Namespace Index** | **Example** |
| --- | --- | --- |
| Numeric | 2 | ns=2;i=1234 |
| String | 2 | ns=2;s=Device.System_Tag.#SYS_TIME_SECOND |
| GUID | 0 | ns=0;g={8ACE8827-ECC3-4c9a-8032-CA1E9957A8E8} |
| Opaque | 2 | ns=2;b=M/RbKBsRVkePCePcx24oRA==  |

**支持数据类型如下：**

| **Data Type** | **Description** |
| --- | --- |
| Boolean | Single bit |
| Byte | Unsigned 8 bit value  |
| SByte | Signed 8 bit value |
| UInt16 | Unsigned 16 bit value |
| Int16 | Signed 16 bit value |
| UInt32 | Unsigned 32 bit value |
| Int32 | Signed 32 bit value |
| Float |  |
| Double  |  |
| Enumeration |  |
| StatusCode  | StatusCode is a 32-bit unsigned integer  |


可以用opcua测试工具UaExpert来看server中tag点的nodeid来写地址
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381429334-a8e031b2-5132-460f-9a7b-4d9a0d7f95d2.png#)
上图中，NS（NameSpace）为2，类型为String，value为abcd.asd123。所以地址应该填写ns=2;s=abcd.asd123
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381429489-88ff5635-5192-4b98-bb7e-f834ec1e54d8.png#)

1. 下载工程，在线监控查看采集值

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381429667-a1e50eff-44fc-446b-a54e-512960a63954.png#)



