
# 1. PLC 配置
## 1. 网口连接
打开工程树中的“参数”→“FX5UCPU”→“模块参数”→“以太网端口”
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381409163-128f93a1-7e95-48ee-ab19-f9a2b048127e.png#)
打开以太网端口设置项目中的“对象设备连接配置设置”（双击旁边的“…”），打开后将“模块一览”中的“SLMP连接”拖拽至左下侧3接线处，并设置4处的端口号（**注：5000～5009不可用**）。
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381409459-bdc000f8-cbd6-42a5-a180-1f216521db5f.png#)
设置完成后，关闭窗口并保存
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381409744-6891271b-8601-4d9b-abbf-f0524f5c2a62.png#)
返回“以太网端口设置”栏，并点击“应用”
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381410087-1da64909-4825-4949-a388-285d2d93af9e.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381410397-cbbedd86-6e19-4de1-8f4e-31f70180b76a.png#)
**Figure 3.5 Module List Setting**
## 1 RS-485 串口连接
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381410649-6d77bedb-37ae-45cd-a551-7fbf5e60093f.png#)

- 设置Station Number.
- Message Pattern: 选择 **Pattern 4**.

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381410862-fe57f167-2f79-40f8-811a-73b88a727053.png#)
    下载程序后重启PLC

# 2 Edgelink 配置
## 2.1 设备配置
**1）网口 **
**![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381411073-9616e8b3-9be3-4414-be64-9ab0bfa9fbed.png#)**
单元号：任意。网口中单元号无特殊意义
IP和端口号：plc的ip和通讯端口号

**2)  串口**
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381411281-038d18b1-66ce-4f30-a219-e64cdf3b5f6d.png#)

- 单元号：plc的站号

## 2.1 添加点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381411447-ac2e3a72-e757-451b-a604-c962744a6dd5.png#)
设备模板参数如下

| **Parameter** | **Type** | **Description** |
| --- | --- | --- |
| CN | Analog | Counter Current |
| D | Analog | Data Register |
| R | Analog | File Register |
| SD | Analog | Special Register |
| SN | Analog | Retentive Timer Current |
| SW | Analog | Special Link Register |
| TN | Analog | Timer Current |
| W | Analog | Link Register |
| Z | Analog | Index Register |
| ZR | Analog | File Register |
| B | Digital | Link Relay |
| CC | Digital | Counter Coil |
| CS | Digital | Counter Contact |
| DX | Digital | Direct Inout |
| DY | Digital | Direct Output |
| F | Digital | Annunciator |
| L | Digital | Latch Relay |
| M | Digital | Internal Relay |
| S | Digital | Step Relay |
| SB | Digital | Special Link Relay |
| SC | Digital | Retentive TImer Coil |
| SM | Digital | Special Relay |
| SS | Digital | Rententive Timer Contact |
| TC | Digital | Timer Coil |
| TS | Digital | Timer Contact |
| V | Digital | Edge Relay |
| X | Digital | Inout Relay |
| Y | Digital | Output Relay |
| TEXT | Text | TEXT |


