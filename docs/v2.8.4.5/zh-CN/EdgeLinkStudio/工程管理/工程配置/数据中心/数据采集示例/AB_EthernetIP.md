## 通过Ethernet/IP协议采集ABPLC

## 1 添加设备
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381366733-f2f48b96-a49a-4177-bb5a-cd443c7749fb.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381367004-67aa56b9-1963-44c6-a54c-e2233f8de7a7.png#)

- **单元号**：CPU在plc所在的槽号

**注**: 单元号不可重复，如果需要写同样的槽号，可勾选下方的设备地址，把槽号写在下面。如下图
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381367307-29e64918-5468-4184-b208-3eaef246698e.png#)

- IP和端口号： PLC的ip和端口号

## 2 添加点
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381367532-2ef9214f-d591-4558-8e18-9c280d38853d.png#)

- **数据类型： 模拟量或数字量**
- **地址： 填写PLC中的点名称即可**
- **起始位和数据长度(bit): 模拟量需注意对应点的数据长度；数字量需注意对应点的起始位。**
## 3 支持的点类型
| **Address format** | **Date Type** | **Description** |
| --- | --- | --- |
| SINT | Analog | 8 bits signed integer |
| INT | Analog | 16 bits signed integer |
| DINT | Analog | 32 bits signed integer |
| LINT | Analog | 64 bits signed integer |
| REAL | Analog | 32 bits signed float |
| BOOL | Discrete | 1 bits value |



