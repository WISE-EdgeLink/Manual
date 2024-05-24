# 网关与三菱Q系列PLC编程串口的通讯配置文档
## 适用设备类型
三菱Q系列PLC
## 采集设备配置

1. **驱动类型与PLC适用范围**

使用网关TagLink中自带的MitsuQCPU驱动，可与下列三菱Q系列PLC上自带的编程串口通讯，PLC列表：

| Q02CPU | Q02HCPU | Q06HCPU | Q12HCPU | Q25HCPU |
| --- | --- | --- | --- | --- |
| Q00UJCPU | Q00UCPU | Q01UCPU | Q02UCPU | Q03UDCPU |
| Q04UDHCPU | Q06UDHCPU | Q10UDHCPU | Q20UDHCPU | Q26UDHCPU |
| Q03UDECPU | Q04UDEHCPU | Q06UDEHCPU | Q10UDEHCPU | Q13UDEHCPU |
| Q20UDEHCPU | Q26UDEHCPU | Q03UDVCPU | Q04UDVCPU | Q06UDVCPU |
| Q13UDVCPU | Q26UDVCPU | Q172HCPU | Q172DCPU | Q173DCPU |

Tip: Q系列中，Q00CPU/Q01CPU/Q02UCPU 这三种类型PLC编程串口不属于此驱动文档适用范围，请参考MitsuQ驱动文档。

1. **PLC接线方式**

三菱Q系列的PLC本体上自带圆形编程串口(RS-232)，与网关的连接方式见图1：

PLC接线端
网关串口端子

| 1 RX |
| --- |
| 2 TX |
| 3 GND |

| 1 RXD |
| --- |
| 2 TXD |
| 3 SG |
| 5 CTS |
| 6 RTS |



![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381499145-dd5e3741-b40b-4b2a-8444-15d2224843ee.png#)



图1
注意：网关使用的通讯串口需要拨码设置为RS-232模式。

1. **三菱Q系列编程串口只支持默认配置，无法通过PLC编程软件进行设置。**

## TagLink Studio通讯配置

1. **新建端口**

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381499310-ab02e2dd-3c3d-43f0-b793-13dc803a37ca.png#)
图2

- 端口类型：Serial
- 串口号：真实通讯使用的串口编号
- 波特率：QCPU固定为9600
- 数据位：QCPU固定为8
- 停止位：QCPU固定为1
- 奇偶校验：QCPU固定为 Odd
- 根据实际需求配置 扫描时间/超时/重试计数/自动恢复时间 
1. **新建仪表**

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381499500-b2063d26-6dea-477b-bfb0-f550950524f8.png#)
图3

- 仪表类型：MitsuQCPU
- 单元号：QCPU固定为0
1. **IO点配置**
   1. QCPU的数字量输入点，以PLC中的X0B点位为例，其中
- 数据类型：Discrete
- 地址：X0B
- 起始位：0
- 长度：1

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381499685-f1bf1fe5-098d-4cd5-b09d-4ed52d192b49.png#)
图4

   1. QCPU的数字量输入点，以PLC中的Y01点位为例，其中
- 数据类型：Discrete
- 地址：Y01
- 起始位：0

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381499858-39c54a0f-cb18-423d-ba2c-fa66d8783640.png#)
图5

   1. QCPU的模拟量内部寄存器，以PLC中的D00019点位为例，其中
- 数据类型：Analog
- 转换代码：默认为Unsigned Integer，可根据PLC实际点表进行改动
- 地址：D00019
- 起始位：0
- 长度：默认为16，可根据PLC实际点表进行改动

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381500034-8e5b2132-7b52-4309-83aa-708887450525.png#)
图6
## 设备点表
| 　 | PLC | WebAccess配置 |  |  |
| --- | --- | --- | --- | --- |
|  | 点位地址Sample | 地址 | 地址模式 | 地址最大值 |
| 数字量 | B0A | B0A | 16进制 | 0x1FFF |
|  | CC09 | CC09 | 10进制 | 1023 |
|  | CS09 | CS09 | 10进制 | 1023 |
|  | DX0A | DX0A | 16进制 | 0x1FFF |
|  | DY0A | DY0A | 16进制 | 0x1FFF |
|  | F09 | F09 | 10进制 | 2047 |
|  | L09 | L09 | 10进制 | 8191 |
|  | M09 | M09 | 10进制 | 8191 |
|  | S09 | S09 | 10进制 | 8191 |
|  | SB0A | SB0A | 16进制 | 0x7FF |
|  | SC09 | SC09 | 10进制 | 2047 |
|  | SM09 | SM09 | 10进制 | 2047 |
|  | SS09 | SS09 | 10进制 | 2047 |
|  | TC09 | TC09 | 10进制 | 2047 |
|  | TS09 | TS09 | 10进制 | 2047 |
|  | V09 | V09 | 10进制 | 2047 |
|  | X0A | X0A | 16进制 | 0x1FFF |
|  | Y0A | Y0A | 16进制 | 0x1FFF |
| 模拟量 | CN09 | CN09 | 10进制 | 1023 |
|  | D09 | D09 | 10进制 | 12287 |
|  | R09 | R09 | 10进制 | 32767 |
|  | SD09 | SD09 | 10进制 | 2047 |
|  | SN09 | SN09 | 10进制 | 2047 |
|  | SW0A | SW0A | 16进制 | 0x7FF |
|  | TN09 | TN09 | 10进制 | 2047 |
|  | W0A | W0A | 16进制 | 0x1FFF |
|  | Z09 | Z09 | 10进制 | 15 |
|  | ZR09 | ZR09 | 10进制 | 32767 |


