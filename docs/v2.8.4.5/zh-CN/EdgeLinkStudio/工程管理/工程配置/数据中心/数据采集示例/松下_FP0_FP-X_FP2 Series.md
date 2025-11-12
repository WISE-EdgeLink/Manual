# Edgelink配置
## 1 添加设备
### 网口
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381433497-eb9b9f3f-67c3-48f7-9cec-6e1f244574f9.png#)
设备类型：选择Panasonic驱动
单元号：任意。无特殊意义。
IP和端口号： PLC的ip和端口号
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381433688-15934c95-a01d-4a3d-8ae5-e5443c3df6bb.png#)
Source Station No.: 网关设备站号，可任意，不和网络中plc的站号相同即可。
Destination Station No.: PLC的站号
Block Size：一个请求中包含的寄存器数量。一般保持默认即可。
TCP/UDP：0使用TCP，1使用UDP
Header: %/< (0/1) : 报文头类型。0代表%开头，1代表<开头



### 串口
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381433881-bc8521e1-c97a-4446-a28f-52e80b622bd7.png#)
设备类型：选择Panasonic驱动
单元号：PLC的站号
Block Size：一个数据包中包含的tag点数量。一般保持默认即可。
Header: %/< (0/1) : 报文头类型。0代表%开头，1代表<开头
## 2 添加点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381434090-47bd0a77-316d-491b-bd22-7e8663a930dc.png#)


| **Parameter** | **Type** | **Address** | **Description** |
| --- | --- | --- | --- |
| AO_DT | Analog | D00000 | Data (Data Registry) |
| AO_EV | Analog | K0000 | Data (Timer/Counter Elapsed Value) |
| AO_FL | Analog | F00000 | Data (File Registry) |
| AO_ID | Analog | ID | Data (Index Registry 0 & 1) |
| AO_IX | Analog | IX | Data (Index Registry 0) |
| AO_IY | Analog | IY | Data (Index Registry 1) |
| AO_LD | Analog | L0000 | Data (Link Data Registry) |
| AO_SR | Analog | R000 | Data (System Registry) |
| AO_SV | Analog | S0000 | Data(Timer/Counter Value) |
| AO_WL | Analog | WL0000 | Data (Link Relay) |
| AO_WR | Analog | WR0000 | Data (Internal Relay) |
| AO_WX | Analog | WX0000 | Data (External Input Relay) |
| AO_WY | Analog | WY0000 | Data (External Output Relay) |
| C | Digital | C0000 | Counter |
| DI_C | Digital | C0000 | Contact (Counter) |
| DI_T | Digital | T0000 | Contact (Timer) |
| DO_L | Digital | L000X | Contact (Link Relay) |
| DO_R | Digital | R000X | Contact (Internal Relay) |
| DO_X | Digital | X000X | Contact (External Input) |
| DO_Y | Digital | Y000X | Contact (External Output) |


