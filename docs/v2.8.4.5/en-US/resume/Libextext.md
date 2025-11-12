## Overview

libextext has multiple built-in macro functions for formatting and outputting system time or tag values. Users can use these macro functions to format the required text templates.

This module can be used to output email and short message content in event management, or for other applications that need to forward text data, such as MQTT or HTTP forwarding.

### Macro function overview

<style>
table th:first-of-type {
    width: 100px;
}
</style>

| Function item | Function description | Parameter description | fmt options |
| ------------------------------- | ------------------------------ | ---------------------------------------- | -------------------- |
| `$localtime(fmt)` | Output local time | fmt: Output format configuration | %F,%T,%H, …… |
| `$gmttime(fmt)` | Output Greenwich Mean Time | fmt: Output format configuration | %F,%T,%H, …… |
| `$ctime(fmt)` | Output timestamp | fmt: Output format configuration | s,ms,sms |
| `$tagLocalTime(tag_name,fmt)` | Output tag timestamp local time | tag_name:tag name<br>fmt: Output format configuration | %F,%T,%H, …… |
| `$tagGmtTime(tag_name,fmt)` | Output tag timestamp Greenwich Mean Time | tag_name:tag name<br>fmt: output format configuration | %F,%T,%H, …… |
| `$tagCTime(tag_name,fmt)` | Output tag timestamp value | tag_name:tag name<br>fmt: output format configuration | s,ms,sms |
| `$tagName(tag_name)` | Output tag name | tag_name:tag name | --- |
| `$tagValue(tag_name,fmt)` | Output tag value | tag_name:tag name<br>fmt: output format configuration | %.1lf,%.2lf,%.3lf,%g |
| `$tagQuality(tag_name)` | Output tag quality | tag_name:tag name | --- |
| `$tagValueDescriptor(tag_name)` | Output tag value description | tag_name: tag name | --- |
| `$tagDesc(tag_name)` | Output tag description | tag_name: tag name | --- |
| `$MulTagBegin(tag_list)` | Multi-point processing template starting position, no output. | tag_list: a list of tag names separated by commas, leaving it blank means using the entire point table in the project configuration | --- |
| `$MulTagEnd(separator)` | Multi-point processing template end position, output the string specified by separator | separator: separator, used to add to the middle of each tag output text block. | --- |
| `$MulDevBegin(tag_list)` | Multi-device processing module starting position, no output. | tag_list: a list of tag names separated by commas. Leaving it blank means using the entire point list in the project configuration. | --- |
| `$MulDevEnd(separator)` | The end position of the multi-device processing module, outputs the string specified by separator. | separator: a separator, used to be added to the middle of each device output text block. | --- |
| `$MulVarBegin()` | The start position of the multi-variable processing module, no output. | No parameters | --- |
| `$MulVarEnd(separator)` | The end position of the multi-variable processing module, outputs the string specified by separator. | separator: a separator, used to be added to the middle of each device output text block. | --- |
| `$devName()` | Output device name | No parameters | --- |
| `$varName()` | Output variable name | No parameters | --- |
| `$varValue(@,fmt)` | Output variable corresponding to the tag value | fmt: Output format configuration | %.1lf,%.2lf,%.3lf,%g |
| `$varQuality()` | Output variable corresponding to the tag quality | No parameters | --- |
| `$varDesc()` | Output variable corresponding to the tag description | No parameters | --- |
| `$varValueDescriptor()` | Output variable corresponding to the tag value description | No parameters | --- |
| `$varLocalTime(@,fmt)` | Output variable corresponding to the tag timestamp local time | fmt: Output format configuration | %F,%T,%H, …… |
| `$varGmtTime(@,fmt)` | Output variable corresponds to the Greenwich Mean Time of tag timestamp | fmt: Output format configuration | %F,%T,%H, …… |
| `$varCTime(@,fmt)` | Output variable corresponds to the value of tag timestamp | fmt: Output format configuration | s,ms,sms |

## Macro function details

### System time function

`$localtime(fmt)`, `$gmttime(fmt)` and `$ctime(fmt)` are three macro functions used to format the current system time into text. The output format is specified by the `fmt` parameter and supports the following parameter formats.

<style>
table th:first-of-type {
    width: 100px;
}
</style>

| Parameters | Format description | Output format |
| --- | ----------------------- | --------------------------- |
| %a | Abbreviated day of the week | wed |
| %A | Full day of the week | Wednesday |
| %b | Abbreviated month | Nov |
| %B | Full month | November |
| %c | Standard date and time string | Wed Nov 11<br>13:59:53 2020 |
| %C | First two digits of the year | 20 |
| %d | Decimal day of the month | 20 |
| %D | Month/day/year | 11/11/20 |
| %e | In a two-character field, <br>Decimal day of the month | 20 |
| %F | Year-Month-Day | 2020-11-11 |
| %g | Last two digits of the year,<br>using week-based year | 20 |
| %G | Year, using week-based year | 2020 |
| %h | Abbreviated month name | Nov |
| %H | Hour in 24-hour format | 14 |
| %I | Hour in 12-hour format | 02 |
| %j | Decimal day of year | 316 |
| %m | Decimal month | 11 |
| %M | Decimal minute | 12 |
| %n | Newline | --- |
| %p | Local equivalent of AM or PM | AM |
| %r | 12-hour time | 02:05:53 PM |
| %R | Hours and minutes as hh:mm | 14:06 |
| %S | Decimal seconds | 39 |
| %t | Horizontal tab | --- |
| %T | Display hours, minutes, and seconds: hh:mm:ss | 14:05:36 |
| %u | Day of the week | 5 |
| %U | Week of the year, <br>Sunday as first day | 46 |
| %V | Week of the year, <br>using week-based year | 47 |
| %w | Day of the week as decimal | 3 |
| %W | Week of the year, Monday as first day | 45 |
| %x | Standard date string | 11/11/20 |
| %X | Standard time string | 14:04:07 |
| %y | Decimal year without century | 20 |
| %Y | Decimal year with century | 2020 |
| %z | Time zone name | +0800 |
| %Z | Time zone abbreviation | CST |
| %% | Percent sign | % |

#### **\$localtime(fmt):** Output local time

**`fmt`** : Time output format parameter item, the default output format parameter is: %F %T (year month day hour minute second) <br>
**`Result`** : Output local time in format<br>
**`Example`** :

> `$localtime(%F %T) : 2020-11-10 17:07:15` <br>
> `$localtime(%T) : 17:07:15` <br>

#### **\$gmttime(fmt):** Output Greenwich Mean Time

**`fmt`** : Time output format parameter item, the default output format parameter is: %F %T (year month day hour minute second) <br>
**`Result`** : Output GMT time in format <br>
**`Example`**:

> `$gmttime(%F %T):2020-11-10 09:07:15` <br>
> `$gmttime(%F):2020-11-10`<br>

#### **\$ctime(fmt):** Output timestamp

**`fmt`**: Time output format parameter item, the default output format parameter is: sms (seconds and milliseconds)<br>
**`Result`**: Output timestamp in format<br>
**`Example`**:

> `$ctime(s):1604999235` <br>
> `$ctime(ms):291` <br>
> `$ctime(sms):1604999235291` <br>

### Tag function

#### **\$tagName(tag_name):** Output tag name

**`tag_name`**: tag name<br>
**`Result`**: Output tag name<br>
**`Example`**:

> `$tagName(tag_2):tag_2              `

#### **\$tagValue(tag_name，fmt):** Output tag value

**`tag_name`**: tag name<br>
**`fmt`**: retain valid digits, retain 2 decimal places by default (%.2lf)<br>
**`Separator`**: comma (,) is used as parameter separator between parameters<br>
**`Result`**: Output the corresponding tag value, return: 0 if failed<br>
**`Example`**:

> `$tagValue(tag_8,%.3lf):7.000        `<br>
> `$tagValue(tag_9,%.9lf):8.000000     `<br>
> `$tagValue(tag_10,%.g):9             `<br>
> `$tagValue(tag_,%.2lf):0.00         `

#### **\$tagQuality(tag_name):** Output tag quality

**`tag_name`**: tag name<br>
**`Result`**: Output tag quality, return if failed: 8080<br>
**`Example`**:

> `$tagQuality(tag_2):0                  `<br>
> `$tagQuality(tag_):8080               `<br>

#### **\$tagValueDescriptor(tag_name):** Output tag description

**`tag_name`**: tag name<br>
**`Result`**: Output tag description information, return if failed: 0<br>
**`Example`**:

> `$tagValueDescriptor(test:D1):111 `<br>
> `$tagValueDescriptor(tag_): 0.00 `<br>

#### **\$tagLocalTime(tag_name,fmt):** Output tag local time

**`tag_name`**: tag name<br>
**`fmt`**: time output format parameter, default output format %F %T (year-month-day hour-minute-second)<br>
**`delimiter`**: comma (,) is used as parameter delimiter between parameters<br>
**`result`**: output tag local timestamp according to format parameter, return if failed: 1970-01-01 08:00:00<br>
**`example`**:

> `$tagLocalTime(tag_9,%F %T):2020-11-10 17:07:16   `<br>
> `$tagLocalTime(tag_9,%F):2020-11-10                `<br>
> `$tagLocalTime(tag_,%F):1970-01-01 08:00:00       `<br>

#### **\$tagGmtTime（tag_name，fmt）:** Output tag Greenwich Mean Time

**`tag_name`**: tag name<br>
**`fmt`**: time output format parameter, default output format %F %T(year-month-day hour-minute-second)<br>
**`delimiter`**: comma (,) is used as parameter delimiter between parameters<br>
**`result`**: output tag GMT timestamp according to format parameter, return if failed: 1970-01-01 00:00:00<br>
**`example`**:

> `$tagGmtTime(tag_9,%F %T):2020-11-10 09:07:16  `<br>
> `$tagGmtTime(tag_9,%T):09:07:16                 `<br>
> `$tagGmtTime(tag_,%T): 1970-01-01 00:00:00      `<br>

#### **\$tagCTime(tag_name，fmt):** Output tag timestamp

**`tag_name`**: tag name<br>
**`fmt`**: timestamp output format parameter, default time format sms (seconds and milliseconds)<br>
**`delimiter`**: comma (,) is used as parameter delimiter between parameters<br>
**`result`**: output tag timestamp according to format parameter, return: 0 if failed<br>
**`example`**:

> `$tagCTime(tag_9,s):1604999236            `<br>
> `$tagCTime(tag_9,ms):211                 `<br>
> `$tagCTime(tag_9,sms):1604999236211       `<br>
> `$tagCTime(tag_,s):0                      `<br>
> `$tagCTime(tag_,sms):000                  `<br>
> `$tagCTime(tag_,sms):0000                `<br>

### Multi-tag custom template function

This function consists of `$MulTagBegin(tag_1,tag_2,……)`, `template`, `$MulTagEnd(separator)`, which correspond to the starting part, template part, and ending part respectively. Only when the input text successfully matches the starting part and the ending part can the template output defined by multiple tags be realized.

#### **`$MulTagBegin(tags) template $MulTagEnd(separator)`**

**`tags`**: the name of the tag to be added, with comma (,) as the tag separator<br>
**`Example`**: $MulTagBegin(tag_1,tag_2,……)<br>

**`template`**: the template to be output for each tag, the template is customized by the user<br>
**`Example`**: {“tagname”: $tagName(@)}, the @ character in the template will be replaced by the tag name<br>

**`separator`**: template separator. <br>
**`Example`**: $MulTagEnd(,), with comma (,) as the separator between tag templates<br>

**`Multi-tag custom template example`**:

**`Input`**:

```c
$MulTagBegin(tag_8,tag_2,tag_5)
{
$$gmttime(%F %T):$gmttime(%F %T),
$$tagName(@):$tagName(@)
}
$MulTagEnd(,)
```

**`Output`**:

```json
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

### Sub-device model function

The sub-device model is to divide the device name and variable name by `:` in the tag name to organize into structured text data, such as the content in the following format:

```json
{
    "PLC1":{
        "Status":1,
        "PV":123
    },
    "PLC2":{
        "Status":0,
        "PV":456
    }
}
```

It can be composed by parsing the four tags `PLC1:Status`, `PLC1:PV`, `PLC2:Status` and `PLC2:PV`. The parsing rule is to separate the tag names with `:`, the one before `:` is the device name (devName), and the one after `:` is the variable name (varName).

The template used to generate the output of the above example is as follows:

```c
{$MulDevBegin(PLC1:Status,PLC1:PV,PLC2:Status,PLC2:PV)
        "$devName()":{$MulVarBegin()
                "$varName()":$varValue(@,%.0lf)$MulVarEnd(,)
        }$MulDevEnd(,)
}
```

#### **\$devName():** Output device name

This macro function has no parameters and must be parsed normally in a text block that starts with `$MulDevBegin(tag_list)` and ends with `$MulDevEnd(separator)`.

**`Result`**: Output device name<br>
**`Example`**:

> `$devName():PLC1              `

#### **\$varName():** Output variable name

This macro function has no parameters and must be parsed normally in a text block starting with `$MulVarBegin()` and ending with `$MulVarEnd(separator)`.

**`Result`**: Output variable name<br>
**`Example`**:

> `$varName():Status              `

#### **Other macro functions starting with \$var**

The following macro functions starting with \$var are the same as the corresponding macro functions starting with \$tag except that the parameter of `tag_name` must be `@`, so I will not repeat them here.

* `$varValue(@,fmt)`
* `$varQuality()`
* `$varDesc()`
* `$varLocalTime(@,fmt)`
* `$varGmtTime(@,fmt)`
* `$varCTime(@,fmt)`

#### **Sub-device model custom template example**

Let's take the four tags `PLC1:Status`, `PLC1:PV`, `PLC2:Status` and `PLC2:PV` as examples.

##### **Example 1**

Template:

```c
[
    $MulDevBegin(PLC1:Status,PLC1:PV,PLC2:Status,PLC2:PV)
    {
        "$devName()": {$MulVarBegin()
            "$varName()": $varValue(@,%.0lf)$MulVarEnd(,)
        }
    }$MulDevEnd(,)
]
```

Output:

```json
[
    {
        "PLC1": {
            "Status": 1,
            "PV": 123
        }
    },
    {
        "PLC2": {
            "Status": 0,
            "PV": 456
        }
    }
]
```

##### **Example 2**

Template:

```c
[$MulDevBegin(PLC1:Status,PLC1:PV,PLC2:Status,PLC2:PV)
    {$MulVarBegin()
        "$devName()_$varName()": $varValue(@,%.0lf)$MulVarEnd(,)
    }$MulDevEnd(,)
]
```

Output:

```json
[
    {
        "PLC1_Status": 1,
        "PLC1_PV": 1
    },
    {
        "PLC2_Status": 1,
        "PLC2_PV": 1
    }
]
```

##### **Example 3**

Template:

```c
[$MulDevBegin(PLC1:Status,PLC1:PV,PLC2:Status,PLC2:PV)
    {
        "device": "$devName()",
        "data": [$MulVarBegin()
            {
                "name": "$varName()",
                "value": $varValue(@,%.0lf)
            }$MulVarEnd(,)
        ]
    }$MulDevEnd(,)
]
```

Output:

```json
[
    {
        "device": "PLC1",
        "data": [
            {
                "name": "Status",
                "value": 1
            },
            {
                "name": "PV",
                "value": 123
            }
        ]
    },
    {
        "device": "PLC2",
        "data": [
            {
                "name": "Status",
                "value": 0
            },
            {
                "name": "PV",
                "value": 456
            }
        ]
    }
]
```