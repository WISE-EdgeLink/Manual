## BACnet IP(TCP/IP)
### 1.驱动支持开始的版本号：
### 2.添加设备
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714014657376-c18a1fdb-d347-4ef5-9271-2a680bb9ffd1.png#from=url&id=kGB9y&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

- 数据中心--->I/O点--->TCP--->右键：添加设备

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714014657502-ff86c4e6-c856-4eff-a744-49ec2d047a30.png#from=url&id=obj6I&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

- 名称：按自己的喜好填写即可。
- 设备类型：选择BACnet IP。
- IP/域名：BACnet服务器的IP。
- 端口号：BACnet服务器的端口号。
- Device Broadcast[I AM] Time (second)：EdgeLink发送“I AM”的频率。
- Polling Cycle：数据采集周期
- Device Instance #：BACnet 服务器的设备实例号。
- Max Property/Request： 0 表示一次轮询 70 个点，其他值表示一次轮询所配置的点数。
- Synchronize Time at (Ex. 23:50:00) ：在何时与服务器同步时间 。
- 上面的参数配置完成后，点击应用，完成添加。点击取消，可撤销操作。
### 3.添加tag点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714014657569-3e5a48b5-9605-4ed9-986b-98c3173fbea1.png#from=url&id=SC4yf&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
1).根据需求填写或选择上面界面的参数，填写完成后，点击“确定”即可。
2).tag点地址格式为：TypeNo.InstanceNo.PropertyId

- TypeNo：代表类型号。驱动协议支持Analog Input、Analog Output、Analog Value、Binary Input、Binary Output及 Binary Value这6种类型。具体类型号如下：
| 类型 |  类型号  |
| --- | --- |
| Analog Input | 0 |
| Analog Output | 1 |
| Analog Value | 2 |
| Binary Input | 3 |
| Binary Output | 4 |
| Binary Value | 5 |

- InstanceNo：tag点在 server 中的序号。
- PropertyId：请参照 BACNet 协议。例如：present value的PropertyId 为 85 。 则读取 present value 地址示例如下:
| 类型及序号 | 地址 |
| --- | --- |
| AI_2 | 0.2.85 |
| AO_2 | 1.2.85 |
| AV_2 | 2.2.85 |
| BI_2 | 3.2.85 |
| BO_2 | 4.2.85 |
| BV_2 | 5.2.85 |

### 4.常见问题
#### 4.1.错误代码
| 错误代码 | 说明 |
| --- | --- |
| GOOD | No error |
| C010 | Device Idle, I-AM timeout |
| C002 | Data type mismatch |
| A00X | iscrete value over max state |
| QCode bit coded | 0001 in alarm, 0002 Fault, 0004 Overridden, 0008 Out of service |
| b014 | No space to write property |
| b01b | Read access denied |
| b01f | Unknown object |
| b020 | Unknown property |
| b025 | Value out of range |
| b028 | Write access denied |
| b02a | Invalid array index |
| b02f | Datatype not supported |
| b030 | Duplicate name |
| b031 | Duplicate object id |
| b032 | Property is not an array |
| b033 | Abort buffer overflow |
| b034 | Abort invalid apdu in this state |
| b035 | Abort preempted by higher priority task |
| b036 | Abort segmentation not supported |
| b037 | Abort proprietary |
| b038 | Abort other |
| b03b | Reject buffer overflow |
| b03c | Reject inconsistent parameters |
| b03d | Reject invalid parameter data type |
| b03e | Reject invalid tag |
| b03f | Reject missing required parameter |
| b040 | Reject parameter out of range |
| b041 | Reject too many arguments |
| b042 | Reject undefined enumeration |
| b043 | Reject unrecognized service |
| b044 | Reject proprietary |
| b045 | Reject other |
| b050 | Parameter out of range |
| b07b | Abort apdu too long |
| b07c | Abort application exceeded reply time |
| b07d | Abort out of resources |
| b07e | Abort tsm timeout |
| b07f | Abort window size out of range |
| b0100 | Loss of port connection |
| b0101 | Header timeout error |
| b0102 | Data timeout error |
| b0103 | NPDU Timeout error |
| b0104 | Header CRC error |
| b0105 | Data CRC error |
| b0106 | Non-NPDU message error |
| b0107 | Timeout error |
| b0108 | Serial port error |
| b0109 | Invalid Write Properity Error |
| b010a | Invalid Read Properity Error |
| b010b | No valid read data |
| b010c | Unsupported Frame Type |
| b010d | Error in the MS/TP Network |
| b010e | Unknown Data Type to write |
| b010f | Invalid Destination MAC Address |
| b0110 | Invalid Source MAC Address |
| b0111 | Invalid Header Information |
| b0112 | Unable to get a valid Invoke ID |

