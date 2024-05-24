## Edgelink Studio 配置
1. 添加设备

**_串口:_**
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381448892-5b469a30-8470-4277-821a-56c1404b47a5.png#)
**设备类型:** Yokogawa FA-M3
**单元号: **PLC的站号.

**_网口:_**
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381449066-b1f28792-8bc5-456c-85f5-bdb43ca1a96b.png#)
**设备类型: **Yokogawa FA-M3
**单元号:** 任意。网口无特别意义
**IP and Port: **PLC的ip和通讯端口.
**Use ASCII Protocol:** 1-Yes, 0-No
**Use UDP: **1-Yes, 0-No


1. 添加点

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381449243-5f86899b-1885-4ee2-b630-74840873cb34.png#)

| **参数** | **数据类型** | **描述** | **地址格式** |
| --- | --- | --- | --- |
| B | Analog | File Register | B00001 |
| CI | Analog | Counter, Value (Count Up) | CI0001 |
| CP | Analog | Counter, Value (Count Down) | CP0001 |
| CS | Analog | Counter Preset Value | CS0001 |
| D | Analog | Data Register | D00001 |
| R | Analog | Common Register | R0001 |
| TI | Analog | Timer, Value (Count Up) | TI0001 |
| TP | Analog | Timer, Value (Count Down) | TP0001 |
| TS | Analog | Timer, Preset Value | TS0001 |
| V | Analog | Index Register | V001 |
| W | Analog | Link Register | W00001 |
| XW | Analog | Word Input | X00101 |
| YW | Analog | Word Output | Y00101 |
| Z | Analog | Special Register | Z0001 |
| C | Discrete | Counter Relay | CU0001 |
| E | Discrete | Common Relay | E0001 |
| I | Discrete | Internal Relay | I00001 |
| L | Discrete | Link Relay | L00001 |
| M | Discrete | Special Relay | M0001 |
| T | Discrete | Timer Relay | TU0001 |
| X | Discrete | Input Relay | X00101 |
| Y | Discrete | Output Relay | Y00101 |


