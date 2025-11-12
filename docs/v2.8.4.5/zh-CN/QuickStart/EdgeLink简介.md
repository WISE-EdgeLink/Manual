# 1  软件概述
## 1.1 什么是EdgeLink
网关在实际应用场景中一方面连接南向各种智能设备，另一方面和北向各种平台对接，从物联网业务上来看，处于设备和平台的中间层，集数据采集、数据处理、数据转发为一体，成为了物联网大数据流的核心枢纽。
EdgeLink是应用于研华网关的软件系统，由EdgeLink Studio和EdgeLink Runtime两部分组成。
EdgeLink Studio：网关配置工具，离线界面化配置通讯以及网络等，一键下载到网关设备中，且可在线管理和监控设备状态。
EdgeLink Runtime：网关中运行的EdgeLink服务，用来执行EdgeLink Studio做的配置
## 1.2 系统架构
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963334912-fa13f3b3-95da-4555-ae12-e7c745d5cf03.png#averageHue=%23aad171&id=Up5xm&originHeight=504&originWidth=775&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
## 1.3 EdgeLink特点

- Windows界面化配置网关设备
- 支持南北向多种通讯协议的采集与转发 (MQTT, AMQP, LwM2M, OPC UA, Modbus, IEC-104, DNP3……)
- 数据通讯以及网络等配置一键下载
- 设备联网统一管理
- 网关状态实时监控
## 1.4 EdgeLink使用方法
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963335192-074ad4fb-a026-45af-9f63-ef5fac3524ac.png#averageHue=%23d4b982&id=jSXyy&originHeight=596&originWidth=1223&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### 1.4.1 软件安装
软件安装文件名为：SetupEdgeLinkStudio_xxxx_v2.x.x.exe，鼠标双击，弹出安装界面，一直选择下一步即可，默认安装在 C:\Program Files (x86)\Advantech\EdgeLink Studio 目录下。
### 1.4.2 工程部署
工程文件:即Advantech EdgeLink Studio创建的文件，是单个或多个网关配置的集合。通过工程文件，
使用者可以有效管理不同的项目配置。配置方式可以参考[示例场景](#_示例场景)章节
### 1.4.3 远程运维
实际应用场景中，网关连接4G网络，数据中心无法找到网关，所以需要先建立VPN网络，让PC和网关都接入到
VPN网络，实现数据中心对网关的远程运维, 可以是任何授权的VPN连接，这里以研华WebAccess/VPN举例

步骤1：通过WebAccess/VPN联系窗口申请账号和密码。登录WebAccess/VPN首页
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963335452-aaca0d8c-193f-4890-8137-60900de7e369.png#averageHue=%23f7f864&id=ePEwj&originHeight=342&originWidth=643&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤2：在EdgeLink Studio使能WebAccess/VPN, 并填写对应信息，下载工程到网关
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963335654-c1b70e04-a61d-47c9-a28e-2b0bb77a58a7.png#averageHue=%23adc8b0&id=b3UVH&originHeight=263&originWidth=644&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963335926-532a6bfe-2b13-4f0c-a7dd-e9fefda2ef6e.png#averageHue=%23ddd8d2&id=R1Okd&originHeight=189&originWidth=645&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤3：在WebAccess/VPN设置页面点击“validate”
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963336499-346e5c8a-0e5e-4f62-a92b-303a372c26db.png#averageHue=%23eae3d2&id=LyZVX&originHeight=262&originWidth=645&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤4：请在“router”列表中验证
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963336699-0c0a66fd-197c-4e14-a17e-0ea710e23219.png#averageHue=%23f9f9f0&id=PIaDF&originHeight=198&originWidth=643&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤5：用putty连接到网关查看获取VPN IP
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963336913-37737aec-207d-473f-b0dc-e849079bb95e.png#averageHue=%23100e0d&id=QA0fG&originHeight=130&originWidth=437&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
## 1.5 工程配置功能列表

工程文件中可以涉及的功能：工程管理、数据采集、数据处理、数据转发、远程管理、连接机制、系统配置、安全机制

| 功能列表 | 功能分类 | 功能概述 | Container版是否支持 |
| --- | --- | --- | --- |
| 工程管理 | 工程创建 | 创建新工程：
通过EdgeLink Studio新建工程文件 | 是 |
|  |  | 上载网关现有工程：
通过在线设备进行工程upload操作 |  |
|  | 部署方式：
单个网关下载
批量网关下载 | 在线部署
下载时节点识别方式有3种：
**Node ID**
**IP/域名**
**Azure连接字符串** |  |
|  |  | 离线部署：
工程导出到SD卡，手动导入放到设备 |  |
|  | 网关复制 | 在工程中将网关配置复制一份 |  |
|  | 显示工程总点数 | 显示工程中所有的tag点总数（不包含系统点） |  |
|  | 设备添加与删除 | 网关下连接的设备可以灵活管理 |  |
|  | Excel导入导出（所有tag点） | 将tag点导出到excel，方便编辑并可以导入到工程中 |  |
|  | Export to EdgeSync 360/EdgeHub | 将Studio生成的工程文件上传至EdgeSync 360/EdgeHub，用于从EdgeSync 360/EdgeHub远程部署网关 | 是 |
| 数据采集 | 南向采集 | 端口：
以太网
串口
CAN
USB | 是 |
|  |  | 设备：
南向协议
参数配置
添加点
点属性
设备模板 |  |
|  | 系统点 | 网关的基本信息和硬件状态 | 是 |
|  | 用户点 | 非实际IO的点，是用户可选可配 |  |
|  | 计算点 | 某个表达式的计算结果 |  |
| 数据处理 | 数据存储 | 将数据存储到扩展卡/Container版本存储到/data路径 | 是 |
|  |  | 断点续传：
在数据转发过程中出现网络中断/恢复，中断过程中产生的数据可以补传 | 是 |
|  | 逻辑运算 | 支持较复杂的逻辑运算 | 否 |
|  | 事件触发（报警） | 报警方式：
发短信
发邮件
写tag点 | 否 |
|  | 数据传送 | 现场不同设备之间可以相互赋值 | 是 |
| 数据转发 | 行业协议 | 电力：DNP3 | 否 |
|  |  | 电力：IEC104 | 是 |
|  |  | BA：
BACnet | 是 |
|  |  | 工业通用协议：
Modbus | 是 |
|  |  | 研华专用协议：
WASCADA | 是 |
|  |  | OPCUA | 是 |
|  | 云连接 | MQTT：
EdgeSync 360/EdgeHub
AWS
Azure
CumulocityIot
DeviceOn/BI
Google Cloud IoT Core
IotConnect
iSysCore OS
MindSphere
SimpleMQTT
Sparkplug(B)
T-System
WebAccess
WISE-Paas/DataHub
阿里云
百度天工
蓝卓supOS
普奥云 | 是 |
|  | 轻量级M2M | LwM2M | 是 |
|  | Excel导入导出（北向协议和云连接的tag点） |  | 是 |
|  | 数据库转存 | SQL Server | 否 |
|  |  | MySQL |  |
|  |  | ORACLE |  |
|  |  | FTP Server |  |
| 远程管理 | VPN | Open VPN | 否 |
|  |  | WebAccess/VPN |  |
|  |  | EdgeLink/VPN |  |
|  | 在线监控 | tag点读写 | 是 |
|  |  | IO状态：
网关本身的IO状态监测 | 是 |
|  |  | 系统信息：
GPRS状态 | 否 |
|  |  | 系统日志 | 是 |
|  |  | 存储数据查询 | 是 |
|  |  | 系统配置：
系统升级
时间设定 | 否 |
| 连接机制 | 系统连接 | VPN：
OpenVPN （自行搭建）
蒲公英VPN（自行搭建）
Advantech VPN
WebAccess/VPN（自行搭建）
EdgeLink/VPN（国内用户10台网关内提供免费试用） | 否 |
|  |  | L2TP/IPsec | 否 |
|  |  | PPPOE | 否 |
|  | TCP连接 | 主动连接：
连接WebAccess/SCADA
连接四信
其他可定制 | 否 |
|  | 串口桥接 |  | 否 |
| 系统配置 | 网络配置 | 基础配置：
DHCP
固定IP | 否 |
|  |  | WIFI/4G |  |
|  |  | 断线重连：
监控网络状态，实时修复 |  |
|  |  | 路由设置 |  |
|  |  | 优先级设置 |  |
|  |  | 端口转发 |  |
|  |  | NAT |  |
|  |  | DHCP Server |  |
|  | LED配置 | RUN |  |
|  |  | Program |  |
|  |  | Error |  |
|  | 时间配置 | 日期 |  |
|  |  | 时间 |  |
|  |  | 时区 |  |
|  | 服务配置 | SSH |  |
|  |  | HTTPS |  |
|  |  | Telnet |  |
|  |  | FTP Server |  |
|  | 防火墙配置 |  |  |
| 安全机制 | 工程下载 | 配置密码 | 是 |
|  |  | 文件传输加密 TLS1.2 | 是 |
|  | 在线监控 | 密码登录 | 是 |
|  | 安全策略 | 定期漏洞扫描 | 是 |
|  |  | 漏洞修补 | 是 |


## 1.6 南向驱动列表
| EdgeLink Driver List |  |  |  |
| --- | --- | --- | --- |
| ►Standard Protocol |  |  |  |
| Device Type | Models |  EdgeLink Driver | Interface |
| Power Industry Protocol | DNP 3.0 | DNP 3.0 (Only ADAM-3600/ECU-1051/ECU-1251/ECU-4553 supported) | SERIAL & TCP/IP |
|  | IEC 60870-5-101 | IEC 60870-5-101 | SERIAL |
|  | IEC 60870-5-103 | IEC 60870-5-103 | SERIAL |
|  | IEC 60870-5-104 | IEC 60870-5-104 | TCP/IP |
| Power Meter | DL/T 645-2007 | DL/T 645-2007 | SERIAL |
|  | DL/T 645-1997 | DL/T 645-1997 | SERIAL |
|  | IEC 62056-21 | IEC 62056-21 | SERIAL |
|  | WISE-M500 series(Advantech) | Modbus/RTU | SERIAL |
| Database | MS SQL Server  | ODBC for Microsoft SQL Server | TCP/IP |
|  | ORACLE | JDBC for ORACLE Database | TCP/IP |
| OPC UA | OPCUA Client | OPC UA | TCP/IP |
| BACnet | Standard protocol for building controllers | BACnet IP | TCP/IP |
|  |  | BACnet MS/TP | SERIAL |
| SNMP | Simple Network Management Protocol  | SNMP | TCP/IP |
| Modbus | Modbus GW | Modbus TCP with limited connections | TCP/IP |
| 　 | 　 | 　 | 　 |
| ►PLC Driver |  |  |  |
| Manufacturer  | Models |  EdgeLink Driver | Type |
| ABB | Advant Controller models: AC31, AC80, AC410, AC450. Modbus via MVI module.  | Modicon (Modbus RTU) | SERIAL |
|  | 4600 Dissolved Oxygen Analyzer | Modicon (Modbus RTU) | SERIAL |
|  | Commander 1900 Controller Recorders.   | Modicon (Modbus RTU) | SERIAL |
|  | INSUM Modbus-LON Network Gateway | Modicon (Modbus RTU) | SERIAL |
|  | MODCELL, MOD 30ML and Commander 100, 150, 200, and 300 Loop Controllers.   | Modicon (Modbus RTU) | SERIAL |
| Advantech | ADAM-2000 series | Advantech ADAM 2000 Series (ADAM ASCII/Modbus RTU) | SERIAL |
|  | ADAM-4000 series | Advantech ADAM 4000 Series (ADAM ASCII/Modbus RTU) | SERIAL |
|  | ADAM-5000 series Ethernet  | Advantech ADAM-5000 Ethernet (Modbus TCP) | TCP/IP |
|  | APAX series Controller | Advantech APAX Series PLC (CODESYS API) | SERIAL & TCP/IP |
|  | WebCon 2000 Series | Advantech WebCon 2000 Series | SERIAL & TCP/IP |
|  | WebOP HMI | Advantech WebOP HMI (Modbus RTU/TCP) | SERIAL & TCP/IP |
| Allen-Bradley  | PLC-5 Series Models: PLC-5/11, 5/20, 5/30, 5/40, 5/40L, 5/60, 5/60L, Serial DF1 full duplex | Allen-Bradley PLC-5 Series (DF1 Protocol over Serial) | SERIAL |
|  | SLC-500 Series Models: SLC 5/03, 5/04, 5/05, Serial DF1 full duplex | Allen-Bradley SLC-500 Series (DF1 Protocol over Serial) | SERIAL |
|  | Micro Logix  Series PLC | Allen-Bradley Micro Logix Series PLC (DF1 Protocol over Ethernet) | TCP/IP |
|  | Allen Bradley CSP to Modbus Ethernet | Modicon (Modbus TCP/RTU) | SERIAL & TCP/IP |
|  | ControlLogix series, CompactLogix series PLC | Allen-Bradley ControlLogix&CompactLogix Series PLC (Ethernet/IP) | TCP/IP |
| BECKHOFF | BECKHOFF TwinCAT PLC | BECKHOFF TwinCAT PLC (BECKHOFF ADS API) | TCP/IP |
| DELTA | DVP series PLC | Delta DVP Series PLC (Modbus RTU/TCP) | SERIAL & TCP/IP |
| FATEK | FACON FB series PLC | Fatek and Facon PLCs | SERIAL & TCP/IP |
| GE | GE Fanuc Series 90-30 via SNP, Serial SNP | GE Fanuc Series 90-30 via SNP, Serial SNP (SNP and SNP-X serial) | SERIAL & TCP/IP |
|  | GE Fanuc Series 90-70 via SNP, Serial SNP | GE Fanuc Series 90-70 via SNP, Serial SNP (SNP and SNP-X serial) | SERIAL & TCP/IP |
|  | FieldServer Modbus | Modicon (Modbus TCP/RTU) | SERIAL & TCP/IP |
|  | GE Multilin Power Management Modules via Modbus | Modicon (Modbus RTU) | SERIAL |
|  | FieldServer Modbus Ethernet | Modicon (Modbus TCP/RTU) | SERIAL & TCP/IP |
| Honeywell | 7800 series Burner Controls with S7810M ModBus Networking module | Modicon (Modbus RTU) | SERIAL |
|  | DCP100 with Modbus communications | Modicon (Modbus RTU) | SERIAL |
|  | DPR100 DPR180/250 Recorders with Modbus | Modicon (Modbus RTU) | SERIAL |
|  | DR 4300/4500 Recorders with Modbus | Modicon (Modbus RTU) | SERIAL |
|  | UDC700 UDC1000 UDC1500 Loop Controller with Modbus | Modicon (Modbus RTU) | SERIAL |
|  | UDC 3000, UDC 3300 Loop Controllers with Modbus  | Modicon (Modbus RTU) | SERIAL |
|  | UDC 6000 Loop Controller with Modbus | Modicon (Modbus RTU) | SERIAL |
|  | UMC800 Setpoint Programmer / Controller with Modbus | Modicon (Modbus RTU) | SERIAL |
|  | VPR/VRX Recorders with Modbus  | Modicon (Modbus RTU) | SERIAL |
|  | Honeywell HC900 Hybrid Control System | Modicon (Modbus TCP) | TCP/IP |
| Keyence | Keyence KV-700/ KV-1000 Serial | KEYENCE KV-700/ KV-1000 Serial (Host Link) | SERIAL |
|  | Keyence KV-700/1000/3000/5000/5500/7500 TCP/IP | KEYENCE KV-700/ KV-1000 TCP/IP (Host Link) | TCP/IP |
| Mitsubishi | Melsec A | Mitsubishi MELSEC-A Series PLC(MC Protocol) | SERIAL & TCP/IP |
|  | Melsec A1S | Mitsubishi MELSEC-AnS Series PLC(MC Protocol) | SERIAL & TCP/IP |
|  | MitsuA2 | Mitsubishi MELSEC-AnN Series PLC(MC Protocol) | SERIAL |
|  | MitsuAnA | Mitsubishi MELSEC-AnA Series PLC(MC Protocol) | SERIAL & TCP/IP |
|  | MitsuAnAD | Mitsubishi MELSEC-AnAD Series PLC(MC Protocol) | SERIAL |
|  | Melsec FX Series PLC | Mitsubishi MELSEC-Fx Series PLC (MC Protocol) | SERIAL & TCP/IP |
|  | Melsec FX - Series MultiDrop IO | Mitsubishi MELSEC-Fx Series PLC (MC Protocol) | SERIAL |
|  | Melsec FX2 Series PLC | Mitsubishi MELSEC-Fx2 Series PLC (MC Protocol) | SERIAL & TCP/IP |
|  | Melsec FX3 Series PLC | Mitsubishi MELSEC-Fx3 Series PLC (MC Protocol) | SERIAL & TCP/IP |
|  | Melsec FX5 Series PLC | Mitsubishi MELSEC-Fx5 Series PLC (MC Protocol) | SERIAL & TCP/IP |
|  | Melsec Q | Mitsubishi MELSEC-Q Series PLC with Extension Module(MC Protocol) | SERIAL & TCP/IP |
|  | Melsec QCPU | Mitsubishi MELSEC-Q Series PLC(MC Protocol) | SERIAL |
| Omron | Omron C Series PLCs | Omron C Series PLC (HostLink) | SERIAL & TCP/IP |
|  | Omron CJ Series PLCs | Omron CJ Series PLC (HostLink) | SERIAL & TCP/IP |
|  | Omron CP Series PLCs | Omron CP Series PLC (HostLink) | SERIAL & TCP/IP |
|  | Omron CS Series PLCs | Omron CS Series PLC (HostLink) | SERIAL & TCP/IP |
|  | Omron CV Series PLCs | Omron CV Series PLC (HostLink) | SERIAL & TCP/IP |
|  | Omron E5 Series PLCs | Omron E5 Series PLC (HostLink) | SERIAL |
|  | Omron NX/NJ Series PLCs | Omron NX/NJ Series PLC (EtherNet/IP) | TCP/IP |
| Panasonic | FP3 Serial via Modbus MB Link module AFP3492 | Modicon (Modbus RTU) | SERIAL |
|  | FPSH10 Serial via Modbus MB Link module AFP3492 | Modicon (Modbus RTU) | SERIAL |
|  | FP0,FP-X, FP2 series PLC via Mewtocol | Panasonic FP0, FP-X, FP2 Series PLC (Mewtocol) | SERIAL & TCP/IP |
|  | FP7 series PLC via Mewtocol7 | Panasonic PLC Mewtocol7-COM | SERIAL & TCP/IP |
| Schneider | TSX Premium and TSX Micro Series via Modbus | Modicon (Modbus RTU) | SERIAL |
|  | Modcion 484, 584, 884 PLCs | Modicon (Modbus RTU) | SERIAL |
|  | Modicon 984 PLCs | Modicon (Modbus RTU) | SERIAL |
|  | Quantum PLCs  | Modicon (Modbus RTU) | SERIAL |
|  | AEG Compact PLC | Modicon (Modbus RTU) | SERIAL |
|  | ION6200  | Schneider ION6200 (Modbus RTU) | SERIAL |
|  | Modicon Momentum M1E PLCs | Modicon (Modbus TCP) | TCP/IP |
|  | Modicon Quantum PLCs | Modicon (Modbus TCP) | TCP/IP |
| Sharp | Sharp JW series PLC | Sharp JW series PLC | SERIAL |
| Siemens | Siemens Cerberus MXL | Modicon (Modbus TCP/RTU) | SERIAL & TCP/IP |
|  | Siemens S7-200 PLC | Siemens S7-200 PLC  | Serial |
|  | Siemens S7-200 PLC via Modbus  | Modbus RTU (Modicon) | RS-232, RS-485 |
|  | Siemens S7-200 smart | Siemens S7-300/1200/1500 PLC (S7Comm TCPIP) | TCP/IP |
|  |  | Siemens S7-200 PLC | Serial |
|  | Siemens S7-300 | Siemens S7-300/1200/1500 PLC (S7Comm TCPIP) | SERIAL & TCP/IP |
|  | Siemens S7-1200 | Siemens S7-300/1200/1500 PLC (S7Comm TCPIP) | SERIAL & TCP/IP |
|  | Siemens S7-1500 | Siemens S7-300/1200/1500 PLC (S7Comm TCPIP) | SERIAL & TCP/IP |
|  | Siemens LOGO! PLC via Ethernet | Siemens LOGO! PLC via Ethernet | TCP/IP |
| Toyopuc | Toyopuc PLCs | Toyopuc 2PORT-EFR PLC via Ethernet | SERIAL & TCP/IP |
| Wago 750 | WAGO I/O System 750 Fieldbus Coupler for Modbus Serial.  Models 750-312,  750-314,  750-315,  750-316,  750-812,  750-814,  750-815   | WAGO I/O System 750 | SERIAL |
|  | WAGO I/O System 750 Fieldbus Coupler for Modbus.  Models 750-342  | WAGO I/O System 750 | TCP/IP |
| Yaskawa | YASKAWA MP series  | YASKAWA MP Series Ethernet (Extension) | TCP/IP |
|  | MP900 series  | YASKAWA MP900 series, MemoBus Modbus compatible (Modbus RTU/TCP) | SERIAL & TCP/IP |
|  | MP3000 series  | YASKAWA MP3000 series |  TCP/IP |
| Yokogawa | FA-M3 RS-232 Factory ACE PLCs | Yokogawa FA-M3 Ethernet Factiry ACE PLC | SERIAL & TCP/IP |


## 1.7 北向服务列表
| 服务分类 | 服务列表 |
| --- | --- |
| 北向协议、平台 | ActiveConnection (WASCADA)
MQTT
Modbus/RTU
Modbus/TCP
BACnet
OPC UA
IEC-104
DNP3 (Only for ADAM-3600 and ECU Series) |
| 北向数据库 | SQL Server
MySQL
ORACLE
FTP Server |
| 云平台 | EdgeSync 360/EdgeHub
阿里云(Aliyun)
AWS
百度天工(Baidu)
CumulocityIot
CustomMQTT
DeviceOn/BI
Google Cloud IoT Core
IotConnect
iSysCore OS
MindSphere
蓝卓supOS
普奥云(Proudsmart)
SimpleMQTT
Sparkplug(B)
T-System
WebAccess
WISE-PaaS/DataHub
Azure
LwM2M |


# 2 示例场景
## 2.1 场景示意图
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963337076-7f5c8f8f-bd68-4ee7-8b71-41f2a9c77f15.png#id=FQX85&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
## 2.2 场景描述
网关采用ModbusRTU协议采集PLC的数据并使用MQTT协议转发到WISE-PaaS云平台
**ModbuRTU PLC设备信息：**
**串口：**RS485，波特率9600，无奇偶校验，停止位1
**Modbus信息**：DeviceID为1，数据点地址40001
## 2.3 物理设备连接

1. 网关的LAN1口直连到安装好EdgeLink Studio的PC（建议win10）

（注：网关在直连的情况下LAN1的IP为10.0.0.nodeid）

1. 网关的COM1在485模式下连接到PLC的数据采集串口上

（注：485模式设置方式请参考硬件手册，确认跳线位置）

1. 4G模块上网
## 2.4 EdgeLink Studio配置
### 2.4.1 新建工程
步骤1：打开Advantech EdgeLink Studio
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963337248-9c1d1907-83a1-4a21-8a14-402a96ddcb4d.png#id=KZCGD&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤2：点击新建工程
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963337479-b5d31323-305b-4114-ae83-5684ffeafbb7.png#id=sN7hP&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤3：编辑工程名称，存储路径，工程描述，然后点击确定
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963337687-4dc72556-0ace-43b2-bd53-21a90559e58f.png#id=gfEVf&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

步骤4:确定后可以在工程管理页面看到新的工程
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963337944-758f3950-1914-4042-8405-f8db3523ddaf.png#id=dG4eX&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤5：此时可以添加设备到工程中，右键单击工程名”新工程”，选择添加设备(此处的设备是指网关，即下文提到的节点)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963338122-da46dcde-5e40-46be-88ef-e55014361af8.png#id=SMBUE&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤6：弹出新建节点的画面：
名称：客户自己定义
类型：网关的设备型号
密码：工程下载密码。默认00000000
节点识别方式：Node ID 
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963338407-670723a2-74e5-4bf3-afd8-955836b41177.png#id=s5ww3&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

步骤7：以ADAM-3600为例，配置完成后点击应用
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963338620-07473df9-c99a-49b3-a536-dac605267cd6.png#id=GQMF7&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

步骤8：工程创建完毕
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963338775-80f89e3a-37f7-4667-b36b-ab20125715de.png#id=HkLEt&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### 2.4.2 Modbus采集配置
步骤1：在工程中使能COM1，将串口设定部分，填写为与设备Device1串口设定一致，点击应用
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963338993-6348c35a-d31d-410e-8f69-3007407d5a13.png#id=tzWJh&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤2：在COM1上右键，点击添加设备(此处设备为串口连接的PLC)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963339176-61e869e8-d5ae-4ec1-8da6-67c0df5167c7.png#id=BHem0&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤3：在弹出的对话框中，添加设备Device1的信息，名称可以自定义，点击应用
设备类型选择Modicon Modbus Series(Modbus RTU), 单元号：1
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963339365-3cde8486-02b6-4d91-9722-29563367b22b.png#id=Mchiq&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤4：设备添加成功
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963339535-f68a4578-4879-4055-a706-6b24d1c4e495.png#id=KxwJw&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤5：添加I/O点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963339754-898e1612-0065-4fd9-9ad8-115a971487f1.png#id=jL4mh&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

步骤6：在弹出的对话框中，按照Device1的地址信息添加
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963339960-538e076f-3b42-452d-adff-b9082f3a1aa8.png#id=v4vQf&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤6：添加I/O点完成
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963340143-9c33cfc7-dc77-40f3-a902-d34e9c82ffa1.png#id=NVIqS&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### 2.4.3 MQTT转发配置
步骤1：通过WISE-PaaS联系窗口申请账号和密码。登录WISE-PaaS首页
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963340379-53d3d379-1f82-42ed-a2a5-5509c8bcee89.png#id=gazHj&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤2：创建新项目后，您可以单击“项目名称”到另一个Node List列表页面。
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963340624-48ff0f67-d40f-4001-ad93-ac9e7e4d8252.png#id=hzMB0&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤3：创建新的Node，会提示相关信息，创建后也可以通过单击Detail获取详细信息
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963340831-4afaa877-06c0-4d31-ba0d-db3d5ba63a42.png#id=UcCyr&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤4：因为网关设备已经实现了“即插即用”功能，所以不需要添加任何设备。一旦设备上线，Node下面将创建一个新设备。用户可以单对设备进行监控。

步骤5：回到EdgeLink Studio的工程配置页面
步骤6：启动WISE-PaaS/DataHub连接
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963341021-1d1030d6-7326-4855-b204-7116ad88d703.png#id=Dm7pX&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤7：填写对应的参数到工程配置页面，并添加要上传的tag点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963341189-6fba23e2-5083-4864-8180-900c42a76c64.png#id=SB1FJ&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤8：点击应用，完成配置
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963341360-59f6ddd3-a138-4654-9920-084cc111da9c.png#id=H9Ecq&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### 2.4.4 网络配置4G拨号
步骤1：打开系统设置🡪网络设置🡪启用Celluar拨号
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963341738-6fb9bc99-4151-49fc-a3d1-3d7c789ad423.png#id=yfCUC&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### 2.4.5 工程下载
以上配置完成后，下载工程到网关
步骤1：单击下载工程按钮，弹出下载对话框
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963341885-865170d5-2a93-49d4-bdf7-403fe2e1f139.png#id=uGiK3&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤2：等待“编译成功”的提示信息出现后, 单击下载按钮
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963342137-ac950bdb-ba37-427c-bea0-65464af9fa47.png#id=n5Lzy&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
步骤3：等待下载完成，网关上的应用程序重启完成，即下载完毕
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963342331-96c2d464-cf11-47f6-9168-647c02e2e4e2.png#id=c7nyu&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

步骤4：关闭下载窗口
## 2.5 结果展示
以上配置完成后，可以在WISE-PaaS看到PLC的数据
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714963342504-6973a344-34d2-4af1-88a9-1b7891c1e0a2.png#id=sMq6B&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
# 3 硬件平台
## 3.1 内置EdgeLink的硬件
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1714963342777-179b261b-9cec-4200-80d5-0e9e619b7146.jpeg#id=X1IzX&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

## 3.2 其他厂商硬件
Container版EdgeLink可以支持跨平台部署，x86平台硬件只需简单的几步即可实现EdgeLink的应用，参考EdgeLink_Container_部属说明。
