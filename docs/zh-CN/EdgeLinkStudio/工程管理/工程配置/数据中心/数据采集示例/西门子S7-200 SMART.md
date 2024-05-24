# 网关与西门子S7-200 SMART的通讯配置文档
## 适用设备类型
西门子S7-200 SMART
## 采集设备配置

1. **PLC接线方式**

西门子S7-200 Smart PLC一般都自带以太网口和RS-485串口(PPI)。

   1. 以太网口使用普通网线直连；
   2. 网关与PLC的RS-485串口(PPI)连接方式见图1：
| 1 D+ |
| --- |
| 2 D- |
| 3 GND |

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381504950-33115026-c3b4-4a99-86b8-6bae29b4ecba.png#)
PLC接线端(DB9)
网关串口端子

| 3 D+ |
| --- |
| 8 D- |
| 5 GND |

图1
注意：网关使用的通讯串口需要拨码设置为RS-485模式。

1. **PLC编程软件使用**

西门子STEP 7-Micro/WIN SMART是专门为西门子PLC S7-200 SMART开发的编程软件，能在Windows XP SP3/Windows 7以上操作系统运行，可通过此软件对PLC进行参数配置、编程等动作。

   1. PLC编程软件的连接方式

PC使用网线连接PLC，启动西门子STEP 7-Micro/WIN SMART，搜索PLC，如下图2所示PLC的IP地址为：192.168.0.11；将PC的IP改到与PLC同一网段，则可以进行PLC配置。
Tip：S7-200SMART的出厂IP地址为：192.168.2.1。
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381505219-386c749d-2513-4751-8af3-a54f92821120.png#)
图2

   1. 编程软件中的通讯参数获取与配置
      1. 若需要配置PLC以太网通讯IP参数，请参考图3； 
      2. 若需要获取或配置PLC串口通讯参数，请参考图4；

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381505470-3e6c47b1-c3bb-4208-ad98-ecda7aa05443.png#)
图3
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381505795-431e0b64-5e2a-4891-83a8-17b3d83b78e1.png#)
图4

   1. 注意事项
## TagLink Studio通讯配置

1. **以太网口通讯方式配置**
   1. 新建通讯端口，端口类型选择“TCPIP”

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381506040-7404bd2f-c75f-4f7b-86f1-bc70febb1803.png#)
图5

   1. 新建通讯设备

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381506368-0baa80c4-e537-49f6-bd25-e2d9741b0ebd.png#)
图6

- 仪表类型：SiemS7
- IP地址：参照上一章中2->a)->S5或2->b)->i->S4
- 通讯端口号：S7-200 SMART固定为102
- TSAP in Hex: Device ID, RackSlot：S7-200 SMART固定为02.00

1. **串口通讯方式配置**
   1. 新建通讯端口

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381506756-5d0943da-9f86-4495-94ef-a5a22374c079.png#)
图7

- 端口类型：Serial
- 波特率：参照上一章中2->b)->ii->S4
- 数据位：S7-200 SMART固定为8
- 停止位：S7-200 SMART固定为1
- 奇偶校验：S7-200 SMART固定为Even
   1. 新建通讯设备

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381507018-fd3434da-a95f-4a9f-a78e-67d4c6e58661.png#)
图8

- 仪表类型：SiemS72
- 单元号：参照上一章中2->b)->ii->S3
1. **地址配置**

地址书写格式为数据块,偏移量。
1）**模拟量**
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381507311-64109d91-7404-49a1-8894-eace46edc9e9.png#)
模拟量点定义应用举例：

| S7 PLC地址 | 对应IO点配置 |  |  |  |
| --- | --- | --- | --- | --- |
| 寄存器地址 | 对应edgelink地址格式 | 起始位 | 长度 | 转换代码 |
| DB28.DBW2 | DBW28,2 | 0 | 16 | Unsigned Integer |
| DB12.DBD86 | DBD12,86 | 0 | 32 | Unsigned Integer |
| DB2.DBB1 | DBB2,1 | 0 | 8 | Unsigned Integer |
| DB2.DBW64  取Float值 | DBW2,64 | 0 | 32 | Real |


**注：V区需要使用DB1代替，地址举例：VW10对应写成DBW1,10，VB10对应写成DBB1,10**

**2）数字量**
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381507600-7c4bd871-d38e-4b4c-a9e6-fb6e4cac2f2a.png#)
数字量点定义应用举例：
在定义数字量点时，默认定义数字量点起始位0，长度1；SiemensS7系列PLC，在定义数字量点时，往往起始位不为0，根据需要定义，例如：I0001.2，意为采集I0001寄存器的第二个bit，需更改起始位，以下为配置示例；   

| S7 PLC地址 | 对应IO点配置 |  |  |  |
| --- | --- | --- | --- | --- |
| 寄存器地址 | 对应地址格式 | 起始位 | 长度 | 转换代码 |
| **I0001.2** | **IX0001** | 2 | 1 | Unsigned Integer |
| **I0003.5** | **IX0003** | 5 | 1 | Unsigned Integer |
| **Q1003.2** | **QX1003** | 2 | 1 | Unsigned Integer |





