## BACnet MS/TP
### 一、驱动支持开始的版本号：v2.8.0
### 二、快速连接
1.添加端口

- 数据中心--->I/O点--->添加端口

![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659241-405cd94f-2725-4398-8b51-3fb3c33d8df6.jpg#from=url&id=HXbPN&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

- 端口类型：选择“Serial(BACnet MS/TP)”--->名称：按个人喜好填写(本文档中填写的为“MSTP”)

2.配置端口
![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659326-593faae6-156a-48e2-bed7-aa5c19ddc3e3.jpg#from=url&id=jmNQO&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

- 串口号：实际使用的网关端串口号
- 其他参数：根据设备特性配置
- 配置完之后，点击“应用”

3.添加设备

- 数据中心--->I/O点--->MSTP--->添加设备

![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659414-76822b95-bc06-41df-886e-589357739366.jpg#from=url&id=sHDMn&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
4.配置设备

- 设备类型：选择“BACnet Device”--->名称：按个人喜好填写(本文档中填写的为“MSTP”)--->点击“应用”

![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659520-95996a43-504c-48f8-ac1e-9540cd4ffcb6.jpg#from=url&id=Pl8ON&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
5.添加tag点
6.下载工程，即完成了BACnet MS/TP的快速配置。
### 三、配置说明详解
1.配置端口界面扩展属性详解
![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659648-53e4e819-15d6-4cc1-bbc4-85eaae4d00c2.jpg#from=url&id=IVeNb&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

- This Station Device ID：设备的ID。
- MAC(0~127)：设备的MAC地址，默认为127。
- Device Unit Number As：设备配置中的Unit Number 值是设备ID还是设备的MAC地址。
- Max Info Frames：指定节点在必须传递令牌之前可以发送的最大信息帧数。
- Max Master：网络中主节点允许的最高地址，默认为127。
- APDU Timeout(MS)：用来指示需要确认的APDU重新传输之间的时间量（毫秒），但未收到确认。对于允许修改此参数的设备，此属性的建议值为10000毫秒。否则，默认值应为60000毫秒。
- Number of APDU Retries：指示APDU应重新传输的最大次数。此属性的建议值为：如果此设备不执行重试，则此属性应设置为零。如果此属性的值大于零，则应在设备对象APDU_Timeout属性中放置一个非零值。

2.配置设备界面扩展属性详解
![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659739-90986c81-5156-4816-82b6-ea7c26c6c5f3.jpg#from=url&id=Mmx5j&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

- Max Property/ Request：每次请求包所包含的最多tag 个数。

3.tag点地址详细说明
![](https://cdn.nlark.com/yuque/0/2024/jpg/43815434/1714014659914-f88457c3-9587-4e69-8aab-b4760bb680c5.jpg#from=url&id=db7wl&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
tag点地址格式为：TypeNo.InstanceNo.PropertyId
具体地址说明可参考BACnet IP中的说明。
