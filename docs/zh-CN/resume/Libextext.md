##  概述

libextext内置多个宏函数，用于将系统时间或tag值进行格式化输出，用户可使用这些宏函数来编制所需的文本模板。

此模块可用于事件管理中输出邮件和短消息内容，或者用于其他需要转发文本数据的应用，如MQTT或HTTP转发。

###  宏函数总览

<style>
table th:first-of-type {
	width: 100px;
}
</style>

| 功能项 | 功能说明 | 参数说明 | fmt可选项 |
| ------------- | ------------- | ------------- | ------------- |
| `$localtime(fmt)`| 输出本地时间|fmt:输出格式配置| %F,%T,%H, ……|
| `$gmttime(fmt)` | 输出格林尼治时间|fmt:输出格式配置| %F,%T,%H, ……|
| `$ctime(fmt)` | 输出时间戳|fmt:输出格式配置| s,ms,sms|
| `$tagLocalTime(tag_name,fmt)` | 输出tag本地时间|tag_name:tag名字<br>fmt:输出格式配置| %F,%T,%H, ……|
| `$tagGmtTime(tag_name,fmt)` | 输出tag格林尼治时间|tag_name:tag名字<br>fmt:输出格式配置| %F,%T,%H, ……|
| `$tagCTime(tag_name,fmt)` | 输出tag时间戳|tag_name:tag名字<br>fmt:输出格式配置| s,ms,sms|
| `$tagName(tag_name)` | 输出tag 名字|tag_name:tag名字| --- |
| `$tagValue(tag_name,fmt)` | 输出tag 值|tag_name:tag名字<br>fmt:输出格式配置|%.1lf,%.2lf,%.3lf,%g |
| `$tagQuality(tag_name)` | 输出tag 质量|tag_name:tag名字| --- |
| `$tagValueDescriptor(tag_name)` | 输出tag 描述|tag_name:tag名字| ---  |

##  宏函数详细介绍

###  系统时间功能

`$localtime(fmt)`，`$gmttime(fmt)` 和 `$ctime(fmt)` 这三个宏函数用于将当前系统时间格式化为文本，其输出格式由 `fmt` 参数指定，支持以下参数格式。

<style>
table th:first-of-type {
	width: 100px;
}
</style>

| 参数| 格式说明| 输出格式 |
| ------------- | ------------- | ------------- |
| %a | 星期几的简写| wed|
| %A | 星期几的全称| Wednesday|
| %b | 月份的简写| Nov|
| %B | 月份的全称| November|
| %c | 标准的日期的时间串| Wed Nov 11<br>13:59:53 2020|
| %C | 年份的前两位数字| 20|
| %d | 十进制表示的每月的第几天| 20|
| %D | 月/天/年| 11/11/20|
| %e | 在两字符域中，<br>十进制表示的每月的第几天| 20|
| %F | 年-月-日|2020-11-11|
| %g | 年份的后两位数字，<br>使用基于周的年| 20|
| %G | 年份，使用基于周的年| 2020|
| %h | 简写的月份名| Nov|
| %H | 24小时制的小时| 14|
| %I | 12小时制的小时| 02|
| %j | 十进制表示的每年的第几天| 316|
| %m | 十进制表示的月份| 11|
| %M | 十时制表示的分钟数| 12 |
| %n | 新行符|---  |
| %p | 本地的AM或PM的等价显示| AM|
| %r | 12小时的时间| 02:05:53 PM|
| %R | 显示小时和分钟：hh:mm| 14:06 |
| %S | 十进制的秒数| 39|
| %t | 水平制表符|--- |
| %T | 显示时分秒：hh:mm:ss| 14:05:36|
| %u | 每周的第几天| 5|
| %U | 第年的第几周，<br>把星期日作为第一天| 46|
| %V | 每年的第几周，<br>使用基于周的年| 47|
| %w | 十进制表示的星期几| 3|
| %W | 每年第几周，星期一为第一天| 45|
| %x | 标准的日期串| 11/11/20|
| %X | 标准的时间串| 14:04:07|
| %y | 不带世纪的十进制年份| 20|
| %Y | 带世纪部分的十制年份| 2020 |
| %z | 时区名称| +0800|
| %Z | 时区名称首字母简写| CST|
| %% | 百分号| %|


#### **$localtime(fmt):** 输出本地时间

**`fmt`** : 时间输出格式参数项，默认输出格式参数为：%F %T (年月日 时分秒) <br>
**`结果`** : 按格式输出local时间<br>
**`示例`** : 

> `$localtime(%F %T) : 2020-11-10 17:07:15` <br>
> `$localtime(%T) : 17:07:15` <br>

#### **$gmttime(fmt):** 输出格林尼治时间

**`fmt`** :时间输出格式参数项，默认输出格式参数为：%F %T (年月日 时分秒) <br>
**`结果`**：按格式输出GMT时间 <br>
**`示例`**： 

>`$gmttime(%F %T):2020-11-10 09:07:15` <br>
>`$gmttime(%F):2020-11-10`<br>


#### **$ctime(fmt):**  输出时间戳

**`fmt`**:时间输出格式参数项，默认输出格式参数为：sms(秒 和 毫秒)<br>
**`结果`**：按格式输出时间戳<br>
**`示例`**： 

> `$ctime(s):1604999235` <br>
> `$ctime(ms):291` <br>
> `$ctime(sms):1604999235291` <br>

### Tag点功能
#### **$tagName(tag_name):** 输出tag名字

**`tag_name`**：tag名字<br>
**`结果`**：输出tag点名字<br>
**`示例`**：

>`$tagName(tag_2):tag_2		      `


#### **$tagValue(tag_name，fmt):** 输出tag值

**`tag_name`**：tag名字<br>
**`fmt`**：保留有效位，默认保留2位小数（%.2lf）<br>
**`分隔符`**：参数间以逗号（，）作为参数分割符<br>
**`结果`**：输出对应的tag点value值，失败返回:0<br>
**`示例`**：

>`$tagValue(tag_8,%.3lf):7.000        `<br>
>`$tagValue(tag_9,%.9lf):8.000000     `<br>
>`$tagValue(tag_10,%.g):9             `<br>
>`$tagValue(tag_,%.2lf):0.00         `



#### **$tagQuality(tag_name):** 输出tag质量 

**`tag_name`**：tag名字<br>
**`结果`**：输出tag点的质量,失败返回:8080<br>
**`示例`**：

>`$tagQuality(tag_2):0                  `<br>
>`$tagQuality(tag_):8080               `<br>


#### **$tagValueDescriptor(tag_name):** 输出tag描述

**`tag_name`**：tag名字<br>
**`结果`**：输出tag描述信息，失败返回:0<br>
**`示例`**：

>`$tagValueDescriptor(test:D1)：111                     `<br>
>`$tagValueDescriptor(tag_)：0.00                       `<br>

#### **$tagLocalTime(tag_name,fmt）:** 输出tag本地时间

**`tag_name`**：tag名字<br>
**`fmt`**：时间输出格式参数项，默认输出格式%F %T(年月日 时分秒)<br>
**`分隔符`**：参数间以逗号（，）作为参数分隔符<br>
**`结果`**：按格式参数输出tag local时间戳，失败返回:1970-01-01 08:00:00<br>
**`示例`**：

>`$tagLocalTime(tag_9,%F %T):2020-11-10 17:07:16   `<br>
>`$tagLocalTime(tag_9,%F):2020-11-10                `<br>
>`$tagLocalTime(tag_,%F)：1970-01-01 08:00:00       `<br>

#### **$tagGmtTime（tag_name，fmt）:** 输出tag格林尼治时间

**`tag_name`**：tag名字<br>
**`fmt`**：时间输出格式参数项，默认输出格式%F %T(年月日 时分秒)<br>
**`分隔符`**：参数间以逗号（，）作为参数分隔符<br>
**`结果`**：按格式参数输出tag GMT时间戳，失败返回:1970-01-01 00:00:00<br>
**`示例`**：

>`$tagGmtTime(tag_9,%F %T):2020-11-10 09:07:16  `<br>
>`$tagGmtTime(tag_9,%T):09:07:16                 `<br>
>`$tagGmtTime(tag_,%T): 1970-01-01 00:00:00      `<br>

#### **$tagCTime(tag_name，fmt):** 输出tag时间戳

**`tag_name`**：tag名字<br>
**`fmt`**：时间戳输出格式参数项，默认时间格式sms（秒 和 毫秒）<br>
**`分隔符`**：参数间以逗号（，）作为参数分隔符<br>
**`结果`**：按格式参数输出tag 时间戳，失败返回:0<br>
**`示例`**：

>`$tagCTime(tag_9,s):1604999236            `<br>
>`$tagCTime(tag_9,ms):211                 `<br>
>`$tagCTime(tag_9,sms):1604999236211       `<br>
>`$tagCTime(tag_,s):0                      `<br>
>`$tagCTime(tag_,sms):000                  `<br>
>`$tagCTime(tag_,sms):0000                `<br>


### 多Tag点自定义模板功能
本功能由`$MulTagBegin(tag_1,tag_2,……)`、`template`、`$MulTagEnd(separator)`三部分组成，分别对应起始部分、模板部分、结尾部分，仅当输入文本成功匹配起始部分和结尾部分，才能实现多tag定义的模板输出。

#### **$MulTagBegin(tags) template $MulTagEnd(separator)** 

**`tags`**:添加的的tag名字，以逗号（，）作为tag分割符<br>
**`示例`**：$MulTagBegin(tag_1,tag_2,……)<br>

**`template`**:每个tag点要输出的模板，模板由用户自定义<br>
**`示例`**：{“tagname”:$tagName(@)}，模板中@符将由tag名字替换<br>

**`separator`**：模板分隔符。<br>
**`示例`**：$MulTagEnd(,)，以逗号（，）为tag点模板间的分隔符<br>

**`多tag点自定义模板示例`**：

**`输入`**：

```
$MulTagBegin(tag_8,tag_2,tag_5)
{
$$gmttime(%F %T):$gmttime(%F %T),
$$tagName(@):$tagName(@)
}
$MulTagEnd(,)
```

**`输出`**：

```
{
$gmttime(%F %T):2020-11-10 12:13:28,
$tagName(@):tag_8
}
,
{
$gmttime(%F %T):2020-11-10 12:13:28,
$tagName(@):tag_2
}
,
{
$gmttime(%F %T):2020-11-10 12:13:28, 
$tagName(@):tag_5
}
```