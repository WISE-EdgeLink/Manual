## Overview

Libextext built-in multiple macro function that is used to the system time or tag value are formatted output, the user can use the macro function to prepare the required text template.
This module can be used to output mail and short message content in event management, or for other applications that require forwarding text data, such as MQTT or HTTP forwarding.

###  Overview of macro functions

| function | instructions | parameter | optional parameter |
| ---------------- | ---------------- | ---------------- | ---------------- |
| `$localtime(fmt)`| output local time|fmt:formatting| %F,%T,%H, ……|
| `$gmttime(fmt)` | output GMT time|fmt:formatting| %F,%T,%H, ……|
| `$ctime(fmt)` | output the time stamp|fmt:formatting| s,ms,sms|
| `$tagLocalTime(tag_name,fmt)` | output tag local time|tag_name:tag name<br>fmt:formatting| %F,%T,%H, ……|
| `$tagGmtTime(tag_name,fmt)` | output tag GMT time|tag_name:tag name<br>fmt:formatting| %F,%T,%H, ……|
| `$tagCTime(tag_name,fmt)` | output tag time stamp|tag_name:tag name<br>fmt:formatting| s,ms,sms|
| `$tagName(tag_name)` | output tag name|tag_name:tag name| --- |
| `$tagValue(tag_name,fmt)` | output tag value|tag_name:tag name<br>fmt:formatting|%.1lf,%.2lf,%.3lf,%g |
| `$tagQuality(tag_name)` | output tag quality|tag_name:tag name| --- |
| `$tagValueDescriptor(tag_name)` | output tag description|tag_name:tag name| ---  |

##  Macro function is introduced in detail

###  System time function

`$localtime(fmt)`，`$gmttime(fmt)` and `$ctime(fmt)` The three macro function is used to the current system time formatted as text, its output format by ` fmt ` parameter specifies, supports the following parameters format.


| parameter| instructions| formatting |
| ------------- | ------------- | ------------- |
| %a | Short for day of the week| wed|
| %A | The day of the week in full| Wednesday|
| %b | Short for month| Nov|
| %B | The full name of the month| November|
| %c | Standard date time string| Wed Nov 11<br>13:59:53 2020|
| %C | The first two digits of the year| 20|
| %d | The day of the month in decimal notation| 20|
| %D | Month/day/year| 11/11/20|
| %e | In the two-character field,<br>The day of the month in decimal notation| 20|
| %F | Year - Month - Date|2020-11-11|
| %g | The last two digits of the year,<br>Use a week-based year| 20|
| %G | Year, using a year based on the week| 2020|
| %h | The abbreviated name of the month| Nov|
| %H | Twenty-four hours| 14|
| %I | Twelve hours| 02|
| %j | The day of the year in decimal notation| 316|
| %m | A month in decimal notation| 11|
| %M | The number of minutes in the ten hour system| 12 |
| %n | New line character|--- |
| %p | Local AM or PM equivalent display| AM|
| %r | For 12 hours| 02:05:53 PM|
| %R | Displays hours and minutes：hh:mm| 14:06 |
| %S | The number of seconds in decimal| 39|
| %t | Horizontal tabs|--- |
| %T | Displays minutes and seconds：hh:mm:ss| 14:05:36|
| %u | The day of the week| 5|
| %U | The week of the year,<br> with Sunday as the first day| 46|
| %V | The week of the year,<br> using the week-based year| 47|
| %w | A decimal representation of the day of the week| 3|
| %W | Week of the year, Monday is the first day| 45|
| %x | Standard date string| 11/11/20|
| %X | Standard time series| 14:04:07|
| %y | A decimal year without centuries| 20|
| %Y | Ten years with century section| 2020 |
| %z | Time zone name| +0800|
| %Z | An acronym for a time zone name| CST|
| %% | percent| %|


#### **$localtime(fmt):** Output local time

**`fmt`** :Time output format parameter item, the default output format parameter is: %F %T (year, month, day, hour, minute, second) <br>
**`result`** : Output local time in format<br>
**`The sample`** : 

> `$localtime(%F %T) : 2020-11-10 17:07:15` <br>
> `$localtime(%T) : 17:07:15` <br>

#### **$gmttime(fmt):** Output GMT time

**`fmt`** :Time output format parameter item, the default output format parameter is: %F %T (year, month, day, hour, minute, second)<br>
**`result`**：output GMT time in format <br>
**`The sample`**： 

>`$gmttime(%F %T):2020-11-10 09:07:15` <br>
>`$gmttime(%F):2020-11-10`<br>


#### **$ctime(fmt):**  output the time stamp

**`fmt`**:Time output format parameter item, default output format parameter is sms (seconds and ms)<br>
**`result`**：Output the timestamp by format<br>
**`The sample`**： 

> `$ctime(s):1604999235` <br>
> `$ctime(ms):291` <br>
> `$ctime(sms):1604999235291` <br>

###  The Tag function
#### **$tagName(tag_name):** Output tag name

**`tag_name`**：tag name<br>
**`result`**：Output the tag name<br>
**`The sample`**：

>`$tagName(tag_2):tag_2		      `


#### **$tagValue(tag_name，fmt):** Output tag value

**`tag_name`**：tag name<br>
**`fmt`**：Preserve valid bit parameters, default to 2 decimal digits (%.2lf)<br>
**`separator`**：Parameters are separated by a comma (,)<br>
**`result`**：Output the tag value. Failure returns :0<br>
**`The sample`**：

>`$tagValue(tag_8,%.3lf):7.000        `<br>
>`$tagValue(tag_9,%.9lf):8.000000     `<br>
>`$tagValue(tag_10,%.g):9             `<br>
>`$tagValue(tag_,%.2lf):0.00         `



#### **$tagQuality(tag_name):** output tag quality 

**`tag_name`**：tag name<br>
**`result`**：Output the tag quality. Fail to return :8080<br>
**`The sample`**：

>`$tagQuality(tag_2):0                  `<br>
>`$tagQuality(tag_):8080                `<br>


#### **$tagValueDescriptor(tag_name):** output tag description

**`tag_name`**：tag name<br>
**`result`**：Output the tag description. Failure returns :0.00<br>
**`The sample`**：

>`$tagValueDescriptor(test:D1)：111                     `<br>
>`$tagValueDescriptor(tag_)：0.00                      `<br>

#### **$tagLocalTime(tag_name,fmt）:** output tag local time
**`tag_name`**: tag name<br>
**`fmt`**：Time output format parameter item, default output format %F %T(year, month, day, hour, minute, second)<br>
**`separator`**：The arguments are separated by a comma (,)<br>
**`result`**：Output the tag time according to the format,Failed to output:1970-01-01 08:00:00<br>
**`The sample`**：

>`$tagLocalTime(tag_9,%F %T):2020-11-10 17:07:16    `<br>
>`$tagLocalTime(tag_9,%F):2020-11-10                `<br>
>`$tagLocalTime(tag_,%F)：1970-01-01 08:00:00       `<br>

#### **$tagGmtTime（tag_name，fmt）:** output tag GMT time
**`tag_name`**：tag name<br>
**`fmt`**：Time output format parameter item, default output format %F %T(year, month, day, hour, minute, second)<br>
**`separator`**：The arguments are separated by a comma (,)<br>
**`result`**：Output the tag time according to the format,Failed to output:1970-01-01 08:00:00<br>
**`The sample`**：

>`$tagGmtTime(tag_9,%F %T):2020-11-10 09:07:16  `<br>
>`$tagGmtTime(tag_9,%T):09:07:16                 `<br>
>`$tagGmtTime(tag_,%T): 1970-01-01 00:00:00      `<br>

#### **$tagCTime(tag_name，fmt):** Output tag time stamp


**`tag_name`**：tag name<br>
**`fmt`**：Time stamp output format parameter item, default time format sms (seconds and ms)<br>
**`separator`**：The arguments are separated by a comma (,)<br>
**`result`**：Output the tag  stamp according to the format,Failed to output:0<br>
**`the sample`**：

>`$tagCTime(tag_9,s):1604999236            `<br>
>`$tagCTime(tag_9,ms):211                  `<br>
>`$tagCTime(tag_9,sms):1604999236211       `<br>
>`$tagCTime(tag_,s):0                     `<br>
>`$tagCTime(tag_,sms):000                  `<br>
>`$tagCTime(tag_,sms):0000                 `<br>


### Multi-tag custom template function

`$MulTagBegin(tag_1,tag_2...) `, `template` and `$MulTagEnd(separator)` are composed of three parts, corresponding to the beginning part, template part and end part respectively. Only when the input text successfully matches the beginning part and end part, can the template output defined by multiple tags be realized.

#### **$MulTagBegin(tags) template $MulTagEnd(separator)** 

**`tags`**:Add tag name with a comma (,) as the tag divider<br>
**`the sample`**：$MulTagBegin(tag_1,tag_2,……)<br>

**`template`**:Templates to be output for each tag. Templates are user-defined<br>
**`the sample`**：{" tagname ":$tagname (@)}, the @ character in the template will be replaced by the tag name<br>

**`separator`**:Template delimiter<br>
**`the sample`**:$MultagEnd (,), with the comma (,) as the delimiter between the tag template<br>

**`Multi-tag custom template example`**：

**`input`**：

```
$MulTagBegin(tag_8,tag_2,tag_5)
{
$$gmttime(%F %T):$gmttime(%F %T),
$$tagName(@):$tagName(@)
}
$MulTagEnd(,)
```

**`output`**：

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