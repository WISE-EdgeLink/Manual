## Custom MQTT

Custom MQTT provides a customizable topic/payload scheme, where the topic and payload can be defined by the user. This is useful for testing MQTT data communication or for cloud services that require custom payloads.

In addition to tag data upload and modification, Custom MQTT also supports receiving messages from specific topics issued by the server to execute specified commands, allowing for extended use in special applications.

---

### Parameter Settings

<img src="CustomMQTT_1.png" title="" alt="" data-align="center">

- **Gateway Name**:

	Optional. Used in data publishing templates with sub-device models. If the point name cannot be resolved to a sub-device name, this value will be used as the sub-device name. If not specified and needed, `_DEFAULT_DEV_NAME_` will be used.

- **Data Topic**:

	Required. Specifies the topic for publishing real-time data. It's recommended to include a unique device identifier in the topic to aid parsing on the cloud server.

- **Data Payload**:

	Required. Specifies the payload format for publishing real-time data.

	[Payload Configuration Guide](../resume/Libextext.html)

- **Resume Topic**:

	Optional. Specifies the topic for publishing resume (breakpoint continuation) data. If not set, `Data Topic` will be used.

- **Resume Payload**:

	Optional. Specifies the payload format for resume data. If not set, `Data Payload` will be used.

	[Payload Configuration Guide](../resume/Libextext.html)

- **[N].Topic**<br>**[N].Payload**<br>**[N].Topic R**<br>**[N].Payload R**:

	Optional. N ranges from 1 to 25, indicating 25 configurable topic-payload groups:

	- **[N].Topic**: Real-time data topic
	- **[N].Payload**: Real-time data payload format
	- **[N].Topic R**: Resume data topic
	- **[N].Payload R**: Resume data payload format

- **Command Topic**:

	Optional. Topic for receiving commands. The cloud server can send messages to this topic to modify tag point values on the device. Supported message format example:

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

	If this format is not usable, `Write Names Rule` and `Write Values Rule` using [JSONPath](https://www.rfc-editor.org/rfc/rfc9535.html) can be configured.

	For assistance, use [https://jsonpath.com](https://jsonpath.com).

- **Write Names Rule**

	JSONPath rule to extract tag names. Default is `$..tag`. Should return an array of strings. To combine sub-device and tag names: e.g. `$..device;$..name`.

	```json
	[{
		"device": "PLC1",
		"data": [{
			"name": "Status",
			"value": 1
		},{
			"name": "Flags",
			"value": 88
		},{
			"name": "PV",
			"value": 123
		}]
	},{
		"device": "PLC2",
		"data": [{
			"name": "Status",
			"value": 0
		},{
			"name": "PV",
			"value": 456
		}]
	}]
	```

	For keys as device names, use `~` in JSONPath: e.g. `$[*].*~;$..name`

	```json
	[{
		"PLC1": [{
			"name": "Status",
			"value": 1
		},{
			"name": "Flags",
			"value": 88
		},{
			"name": "PV",
			"value": 123
		}]
	},{
		"PLC2": [{
			"name": "Status",
			"value": 0
		},{
			"name": "PV",
			"value": 456
		}]
	}]
	```

- **Write Values Rule**

	JSONPath rule for extracting values. Default is `$..value`. Must produce a flat array of primitive types and match length with tag names.

- **Compress Payload**:

	Enables GZIP compression for payloads. Ensure cloud server also supports GZIP for both sent and received messages.

- **QoS**:

	Controls QoS level (default: 1).

	* QoS 0: At most once. No response or retries.
	* QoS 1: At least once. Ensures delivery.
	* QoS 2: Exactly once. Most reliable but most overhead.

- **External Topic**:

	Topic subscribed to receive external commands.

- **External Command**:

	Command to execute when a message is received on External Topic. E.g., `logger %p` logs payload.

	Wildcards:
	* %t: topic
	* %p: payload string
	* %pf: payload saved to file

	Avoid unsafe characters and commands needing root.

- **Will Topic**:

	Optional. Topic for last will message.

- **Will Message**:

	Optional. Content of last will message.

- **Fault Value**:

	Value to upload when tag quality is bad (default: `*`).

- **RETAIN Flag**:

	Publish RETAIN flag options:

	- None
	- For periodic pub
	- For diff pub
	- For periodic & diff pub

**From version 2.8.4.1, multiple TagLists are supported with individual upload settings.**

- Upload all points after reconnect
- Skip bad quality points
- Upload all points on change

### Other Configuration Guides

[Tag List Configuration](./others/TagList_Setting.html)

[Resume Configuration](./others/resume.html)

[Import/Export Tags](./others/excel.html)
