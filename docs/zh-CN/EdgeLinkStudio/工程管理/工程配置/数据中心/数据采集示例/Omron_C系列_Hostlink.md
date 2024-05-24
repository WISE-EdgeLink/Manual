
# 1 Edgelink 配置 — 串口
## 2 串口配置
根据PLC设置填写串口信息
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381420777-376e2f4d-5464-4542-95d2-5546319d9cf0.png#)
## 3 设备配置 – OmronCJ (示例)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381420950-e81e58e3-3e24-42af-b6ec-6ebc357c4300.png#)
单元号：对应PLC配置
Use Serial FINS COMMAND: 0不使用，1使用.
# 4 Edgelink 配置 — 网口
## 5 网口配置
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381421125-61295809-612c-4012-a597-fa0270c502c7.png#)

## 6 设备配置 – OmronCP (Example)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381421316-3e65c8d7-2fce-4f5b-8c98-d27862819ef2.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714381421481-53bff007-3003-463a-9c40-8cee0a7ff7b0.png#)
**单元号：**无特殊意义。
**IP or Domain:** PLC的IP
**Port: **PLC的端口号，默认为9600
**Fins No. : **根据plc中配置填写
**Use TCP:** 0不使用（UDP），1使用（TCP）.

# 7 点地址
###### 8 **Omron C**
| Parameter | Description | Address | Data Type |
| --- | --- | --- | --- |
| AR | AR AREA | AR0000 | Analog |
| CPV | Counter Present Value | CPV0000 | Analog |
| DM | Dm Area | DM0000　 | Analog |
| HR | HR AREA | HR0000　 | Analog |
| IR | IR AREA | 　IR0000 | Analog |
| LR | LR AREA | 　LR0000 | Analog |
| TPV | Timer Present Value | TPV0000 | Analog |
| C | Counter Status | CNT0000 | Discrete |
| IRD | Bit in IR | IR0000 | Discrete |
| MODE | CPU Mode | ST0 | Discrete |
| T | Timer status | TIM0000 | Discrete |


###### 9 **Omron CJ**
**Analog:**

| **Parameter Name** | **Type** | **Address templete** | **Conversion** | **Start bit** | **length** | **Description** |
| --- | --- | --- | --- | --- | --- | --- |
| A | Analog | AR0000 | Unsigned Interger | 0 | 16 | AR Area |
| CIO | Analog | CIO0000 | Unsigned Interger | 0 | 16 | CIO |
| CPV | Analog | CPV0000 | BCD | 0 | 16 | Counter Present Value |
| D | Analog | DM0000 | Unsigned Interger | 0 | 16 | DM |
| E0 | Analog | B0E0000 | Unsigned Interger | 0 | 16 | EM Bank 0 |
| E1 | Analog | B1E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E2 | Analog | B2E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E3 | Analog | B3E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E4 | Analog | B4E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E5 | Analog | B5E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E6 | Analog | B6E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E7 | Analog | B7E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E8 | Analog | B8E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E9 | Analog | B9E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EA | Analog | BAE0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EB | Analog | BBE0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EC | Analog | BCE0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EM | Analog | EM0000 | Unsigned Interger | 0 | 16 | EM Current Bank |
| H | Analog | HR0000 | Unsigned Interger | 0 | 16 | HR Area |
| TPV | Analog | TPV0000 | BCD | 0 | 16 | Timer Present Value |
| W | Analog | WR0000 | Unsigned Interger | 0 | 16 | WR Area |
| MODE | Analog | ST0 | Unsigned Interger | 8 | 2 | CPU Mode |


**Digital:**

|  | Type | Address templete | Start bit | length | Description |
| --- | --- | --- | --- | --- | --- |
| C | Discrete | CNT0000 | 0 | 1 | Counter Status |
| CIOD00 | Discrete | CIO0000 | 0 | 1 | CIO Bit 0 |
| CIOD01 | Discrete | CIO0000 | 1 | 1 | CIO Bit 1 |
| CIOD02 | Discrete | CIO0000 | 2 | 1 | CIO Bit 2 |
| CIOD03 | Discrete | CIO0000 | 3 | 1 | CIO Bit 3 |
| CIOD04 | Discrete | CIO0000 | 4 | 1 | CIO Bit 4 |
| CIOD05 | Discrete | CIO0000 | 5 | 1 | CIO Bit 5 |
| CIOD06 | Discrete | CIO0000 | 6 | 1 | CIO Bit 6 |
| CIOD07 | Discrete | CIO0000 | 7 | 1 | CIO Bit 7 |
| CIOD08 | Discrete | CIO0000 | 8 | 1 | CIO Bit 8 |
| CIOD09 | Discrete | CIO0000 | 9 | 1 | CIO Bit 9 |
| CIOD10 | Discrete | CIO0000 | 10 | 1 | CIO Bit 10 |
| CIOD11 | Discrete | CIO0000 | 11 | 1 | CIO Bit 11 |
| CIOD12 | Discrete | CIO0000 | 12 | 1 | CIO Bit 12 |
| CIOD13 | Discrete | CIO0000 | 13 | 1 | CIO Bit 13 |
| CIOD14 | Discrete | CIO0000 | 14 | 1 | CIO Bit 14 |
| CIOD15 | Discrete | CIO0000 | 15 | 1 | CIO Bit 15 |
| T |  | TIM0000 | 0 | 1 | Timer Status |



###### 10 **Omron CS**
| **Parameter Name** | **Type** | **Address templete** | **Conversion** | **Start bit** | **length** | **Description** |
| --- | --- | --- | --- | --- | --- | --- |
| A | Analog | AR0000 | Unsigned Interger | 0 | 16 | AR Area |
| CIO | Analog | CIO0000 | Unsigned Interger | 0 | 16 | CIO |
| CPV | Analog | CPV0000 | BCD | 0 | 16 | Counter Present Value |
| D | Analog | DM0000 | Unsigned Interger | 0 | 16 | DM |
| E0 | Analog | B0E0000 | Unsigned Interger | 0 | 16 | EM Bank 0 |
| E1 | Analog | B1E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E2 | Analog | B2E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E3 | Analog | B3E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E4 | Analog | B4E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E5 | Analog | B5E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E6 | Analog | B6E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E7 | Analog | B7E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E8 | Analog | B8E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| E9 | Analog | B9E0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EA | Analog | BAE0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EB | Analog | BBE0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EC | Analog | BCE0000 | Unsigned Interger | 0 | 16 | EM Bank 1 |
| EM | Analog | EM0000 | Unsigned Interger | 0 | 16 | EM Current Bank |
| H | Analog | HR0000 | Unsigned Interger | 0 | 16 | HR Area |
| TPV | Analog | TPV0000 | BCD | 0 | 16 | Timer Present Value |
| W | Analog | WR0000 | Unsigned Interger | 0 | 16 | WR Area |
| MODE | Analog | ST0 | Unsigned Interger | 8 | 2 | CPU Mode |
| C | Discrete | CNT0000 |  | 0 | 1 | Counter Status |
| T | Discrete | TIM0000 |  | 0 | 1 | Timer Status |


###### 11 **Omron CV**
| **Parameter Name** | **Type** | **Address templete** | **Conversion** | **Start bit** | **length** | **Description** |
| --- | --- | --- | --- | --- | --- | --- |
| A | Analog | AR0000 | Unsigned Interger | 0 | 16 | AR Area |
| CIO | Analog | CIO0000 | Unsigned Interger | 0 | 16 | CIO |
| CPV | Analog | CPV0000 | BCD | 0 | 16 | Counter Present Value |
| D | Analog | DM0000 | Unsigned Interger | 0 | 16 | DM |
| EM | Analog | EM0000 | Unsigned Interger | 0 | 16 | EM Current Bank |
| H | Analog | HR0000 | Unsigned Interger | 0 | 16 | HR Area |
| TPV | Analog | TPV0000 | BCD | 0 | 16 | Timer Present Value |
| MODE | Analog | ST0 | Unsigned Interger | 8 | 2 | CPU Mode |
| C | Discrete | CNT0000 |  | 0 | 1 | Counter Status |
| T | Discrete | TIM0000 |  | 0 | 1 | Timer Status |


###### 12 **Omron E5**
| **Parameter Name** | **Type** | **Address templete** | **Conversion** | **Start bit** | **length** | **Description** |
| --- | --- | --- | --- | --- | --- | --- |
| ALMV1 | Analog | R%,1 | Integer | 0 | 16 | Alarm Value1 |
| ALMV2 | Analog | R%,2 | Integer | 0 | 16 | Alarm Value2 |
| ISHIFT | Analog | RI,1 | Integer | 0 | 16 | Input Shift Value |
| MV | Analog | RO,1 | integer | 0 | 16 | MV |
| PBAND | Analog | RB,1 | integer | 0 | 16 | Proportional Band |
| PV | Analog | RX,1 | integer | 0 | 16 | PV |
| SP | Analog | RS,1 | integer | 0 | 16 | Set Point |
| SP_HI | Analog | RL,1 | integer | 0 | 16 | Set Point Upper Limit Value |
| SP_LO | Analog | RL,1/2 | integer | 0 | 16 | Set Point Lower Limit Value |
| TB | Analog | RW,1 | integer | 0 | 16 | Tmperature Burnout Dection |
| TD | Analog | RV,1 | integer | 0 | 16 | Derivative Time |
| TI | Analog | RN,1 | integer | 0 | 16 | Integral Time |
| ALM1 | Discrete | RX,1/2 |  | 9 | 1 | Alarm 1 Status |
| ALM2 | Discrete | RX,1/2 |  | 10 | 1 | Alarm 2 Status |



