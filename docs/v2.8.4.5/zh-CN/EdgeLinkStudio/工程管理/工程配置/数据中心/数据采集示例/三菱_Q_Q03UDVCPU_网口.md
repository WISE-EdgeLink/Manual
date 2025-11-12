**Edgelink 配置**
## 1 添加设备
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381398350-8d6dd331-a216-418f-abce-5940c08f6158.png#)
单元号：任意。

端口号：默认是5001，可在plc配置中看到

Use UDP: 0:TCP, 1:UDP。

Destination IO#：保持默认。

## 2 添加点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381398789-719656ab-a51f-45e6-a767-c66f766e5ba0.png#)
参数列表：

| **Parameter** | **Date Type** | **Description** | **Address format** |
| --- | --- | --- | --- |
| CN | Analog | Counter Current | CN0000 |
| D | Analog | Data Register | D00000 |
| R | Analog | File Register | R00000 |
| SD | Analog | Special Register | SD0000 |
| SN | Analog | Retentive Timer Current | SN0000 |
| SW | Analog | Special Link Register | SW0000 |
| TN | Analog | Timer Current | TN0000 |
| W | Analog | Link Register | W0000 |
| Z | Analog | Index Register | Z0000 |
| ZR | Analog | File Register | ZR00000 |
| B | Discrete | Link Relay | B0000 |
| CC | Discrete | Counter Coil | CC0000 |
| CS | Discrete | Counter Contact | CS0000 |
| DX | Discrete | Direct Inout | DX0000 |
| DY | Discrete | Direct Output | DY0000 |
| F | Discrete | Annunciator | F0000 |
| L | Discrete | Latch Relay | L0000 |
| M | Discrete | Internal Relay | M0000 |
| S | Discrete | Step Relay | S0000 |
| SB | Discrete | Special Link Relay | SB0000 |
| SC | Discrete | Retentive TImer Coil | SC0000 |
| SM | Discrete | Special Relay | SM0000 |
| SS | Discrete | Rententive Timer Contact | SS0000 |
| TC | Discrete | Timer Coil | TC0000 |
| TS | Discrete | Timer Contact | TS0000 |
| V | Discrete | Edge Relay | V0000 |
| X | Discrete | Inout Relay | X0000 |
| Y | Discrete | Output Relay | Y0000 |


