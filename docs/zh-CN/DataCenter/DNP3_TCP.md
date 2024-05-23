## DNP3(TCP)

### 一、驱动支持开始的版本号：

### 二、快速连接

1.添加设备

- 数据中心--->I/O点--->TCP--->右键：添加设备

![](DNP3_1.jpg)

2.配置设备

- 选择设备类型：DNP3.0 Master Driver--->填写DNP3服务器IP及端口号：如172.21.67.56、20000--->点击“应用”

![](DNP3_2.jpg)

3.添加tag点

4.下载工程，即完成了DNP3的快速配置。

### 三、配置说明详解

1.配置界面详解

![](DNP3_3.jpg)

- 名称：按自己的喜好填写即可。

- 设备类型：选择DNP3.0 Master Driver。

- IP/域名：DNP3服务器的IP。

- 端口号：DNP3服务器的端口号。

- Master Address： Session的Master address。

- Slave Address：Session的Slave Address。

- Request Timeout(s)： 数据请求指令的应答超时时间。

- Keep-Alive Interval(s)： 心跳周期，当此项配置非勾选时，即视为Master端不发送心跳包。

- The period  of TimeSync(s)：时间同步周期，此项配置非勾选时，视为不进行时间同步操作。

- xx variation：可配置每种不同数据类型的默认variation，也就是数据格式，具体可参考规约文档。无特殊要求保持默认即可。

2.tag点地址详解

![](DNP3_4-1.jpg)

- Group：共有6种类型。根据实际情况通过下拉框来选择。

- Index：即序号。在Slave端，同一数据类型下会有多个tag点，index即为tag点的序号。

- 备注：因Linux下的master不能下Frozen指令，Frozen counter点只做采集用。







