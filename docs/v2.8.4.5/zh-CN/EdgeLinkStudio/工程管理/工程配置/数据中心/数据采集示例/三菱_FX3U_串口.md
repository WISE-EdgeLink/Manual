**此文档介绍网关如何和FX3U通过PLC自带的485串口连接**

1. PLC配置

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381403555-2b9e2062-0956-4030-aa29-92dedea0e5ea.png#)

1. Edgelink Studio配置
2. 串口下添加设备

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381403803-2fb269d4-2347-4e2d-aadd-ba55293e3487.png#)
设备类型：选择FX3驱动
单元号：和plc参数中的站号一致
Use RS-485：1，使用485

1. 添加点

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381403993-4eee7283-37f2-43ce-b3f0-3ec2fc3454a6.png#)

| **Parameter** | **Date Type** | **Description** | **Address format** |
| --- | --- | --- | --- |
| CN | Analog | Counter Current | CN0000 |
| D | Analog | Data Register | D0000 |
| TN | Analog | Timer-Current Value | TN000 |
| CC | Discrete | Counter Coil | CC000 |
| CR | Discrete | Counter- | CR000 |
| CS | Discrete | Counter-Contact | CS000 |
| M | Discrete | Auxiliary Relay | M0000 |
| S | Discrete | State | S0000 |
| TC | Discrete | Timer Coil | TC000 |
| TR | Discrete | Timer- | TR000 |
| TS | Discrete | Timer- Contact | TS000 |
| X | Discrete | Input | X000 |
| Y | Discrete | Output | Y000 |


