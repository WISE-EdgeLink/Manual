

## Simple MQTT

Simple MQTT provides a simple topic / load scheme in which topics can be defined by the user to test and verify MQTT data communications or to be applied to cloud services that require simple development.
In addition to tag data upload and modification, Simple MQTT also supports the ability of the server to deliver messages of a specific topic to perform the specified commands for special application extensions.

The default simple MQTT publishing data payload format is as follows:

```json
{
    "d":[
        {
            "tag":"AI.0",
            "value":12.00,
            "quality":0
        },
        {
            "tag":"AI.1",
            "value":12.00,
            "quality":0
        }
    ],
    "ts":"2017-12-22T08:05:20+0000"
}
```
- Among them

 - "d" represents an array object that contains all reported tag information. Each tag is represented by an object. Its properties are as follows:

| Attributes |Introductions  |
|--|--|
| tag | tag name |
| value | tag current value |
| Quality | tag current quality value (selectable via parameter switch) |

- "ts" is the timestamp of the message and follows the ISO 8601 standard.

> The data retransmission of the disconnected SimpleMQTT packet is exactly the same as the data packet format of the real-time data.The difference is that the time stamp is obtained from the data record, not the current time.

---
### Parameter settings

![](SimpleMQTT_1.png)

- **Data Topic**: Required fields that specify topics for publishing real-time data. To facilitate parsing of data packets from different devices on the cloud server, it is recommended to add the device unique identifier to the topic when setting this topic.
- **Resume Topic**: Optional, specifies the topic for publishing resuming data. If this field is not set, then the topic specified in `Data Topic` will be used.
- **Command Topic**: Optional, specifies the subject to receive the command. Publishing data from the cloud server to the topic can modify the tag value on the device. The format of the data is the same as the publishing format except that “d” is changed to “w”. There can be no timestamp data in the write packet (that is, ts). If this field is not filled in, the device will not accept the command to modify the value of the cloud service.

   The example of modifying the value of a packet is as follows: The following packet will write the value of AO\_1 as 12.88 and the value of AO\_2 as 18.76.

   ```json
   {
       "w":[
           {
               "tag":"AO_1",
               "value":12.88
           },
           {
               "tag":"AO_2",
               "value":18.76
           }
       ],
       "ts":"2017-12-28T12:22:21+0000"
   }
   ```

- **Payload Type**: This option is used to control the payload format.
   * `Simple`: The default payload type, no quality field in payload
   * `Simple with quality`: The default payload type with quality field in payload
   * `Compact`: The compact payload type as below.
   ```
   {"ts":1451649600512, "values":{"tag1":"value1", "tag2":"value2"}}
   ```
  
- **Compress Payload**: This option controls whether to use GZIP to compress the message payload. By default, the payload is not compressed. If this option is set to GZIP compression, you must make sure that the cloud platform also uses the same GZIP method for decompression. At the same time, the `cmd` payload must also be GZIP compressed message content.


- **QoS**: This option is used to control the quality of service used when publishing messages. The default value is QoS 1.

   * `QoS 0`: Distributed at most once, the distribution of messages depends on the capabilities of the underlying network. The recipient will not send a response and the sender will not retry. The message may or may not be delivered at all.
   * `QoS 1`: Distribute at least once, the quality of service ensures that the message is delivered at least once.
   * `QoS 2`: Distribute only once, which is the highest level of quality of service, and message loss and duplication are unacceptable. There is an additional overhead in using this quality of service level.

- **Timestamp**: This option is used to set the timestamp format in the published message.

   * `UTC Time (ISO-8601)`:  UTC time in ISO-8601 format，such as `2018-01-01T03:30:45+0000`
   * `Local Time (ISO-8601)`: Local time in ISO-8601 format, such as`2018-01-01T11:30:45+0800`
   * `UNIX Time`: UNIX time stamp format, such as `1600058903`
   * `UNIX Time w/ MS`: UNIX time stamp format with millisecond, such as `1600058903001`

- **External Topic**: This option is used to set the topic for external command. If set, the device will subscribe this topic, and will execute the command specified in "External Command" when the message arrived. 

- **External Command**: This option is used combined with the "External Topic", to specify the command line to be executed when message arrived.
For example: `logger %p`, this command will output the message payload to syslog when it is executed。<br>
The command line can have arguments, the following patterns supported in the command line:

	* %t: Topic, this pattern will be substitute by the topic when executing.
	* %p: Payload, this pattern will be substitute by the payload when executing.
	* %pf: Payload file, this pattern will be substitute by a file contains the payload when executing.

	> Note: Don't use `newline` or one of `|, &, ;, <, >, (, ), {, }` in the command string,
	and because of the MQTT application is running as unprivileged user, please don't specify any command needs to run in privileged mode.

### Others

[Tag List](./others/TagList_Setting.html)   

[resume](./others/resume.html)

[export/import](./others/excel.html)