## 单设备设置
1. 在EdgeLink Studio使能remote.it

![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136862399-bcb77059-1331-43d3-98ca-9b6817728fac.jpeg#averageHue=%23e9f0ed&id=UOW0H&originHeight=480&originWidth=881&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

2. 登录到 remote.it 

[https://app.remote.it/#/](https://app.remote.it/#/)
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136862587-a24143cb-2667-4cd9-924b-dbe8b3b9ba15.jpeg#averageHue=%23f8f8f8&id=Q4N3s&originHeight=542&originWidth=748&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

3. 添加设备

![image.png](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717137632965-2a2bbe93-5b0e-4891-a830-8ace99377a8a.png#averageHue=%23faf8f8&clientId=udf9b5bc0-0b97-4&from=paste&height=473&id=ub1a3fd05&originHeight=473&originWidth=869&originalType=binary&ratio=1&rotation=0&showTitle=false&size=142248&status=done&style=none&taskId=u6deaab87-b480-4629-92e1-5198a4c43b0&title=&width=869)
      上图中标注2的代码是从Studio中获取
![image.png](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717137735932-81837844-ab52-41a6-8c14-6bcdce9943ef.png#averageHue=%23f4f3ed&clientId=udf9b5bc0-0b97-4&from=paste&height=520&id=u27e1d1f1&originHeight=520&originWidth=870&originalType=binary&ratio=1&rotation=0&showTitle=false&size=169829&status=done&style=none&taskId=u40f29b25-f992-4d49-9d2a-5277ad5856f&title=&width=870)

4. 添加服务（以SSH为例）

![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136863143-3022bcf3-2654-440a-8a9a-af9d2c964c03.jpeg#averageHue=%23f8f4f4&id=U2tUP&originHeight=292&originWidth=838&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136863338-728cf529-7f86-4d0f-b00b-8f2a43969d9c.jpeg#averageHue=%23f9f8f8&id=jkBgB&originHeight=611&originWidth=869&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
**配置完成后需等待一些时间。当显示如下图时，您可以点击“连接”来启用服务。**
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136863543-aed033f7-570d-4195-9e3d-48407c8d53bc.jpeg#averageHue=%23fafaf7&id=mO4gk&originHeight=517&originWidth=869&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
**然后你可以使用它显示的IP和端口在任何地方都可以使用互联网访问SSH到ECU。**
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136863747-e70c0418-dd0c-4e28-b082-bb8c80b94391.jpeg#averageHue=%23ebeaea&id=oQAEb&originHeight=409&originWidth=428&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136864608-b8fb52a1-40b1-4602-9a73-771d423a82ca.jpeg#averageHue=%23292929&id=Y3jU4&originHeight=253&originWidth=870&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
## 批量设备设置
### remote.it网站设置
1. 远程登录。网站[https://app.remote.it/#/](https://app.remote.it/#/)
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136864816-5cd63733-b21a-4663-bd23-277804d67168.jpeg#averageHue=%23f8f8f8&id=jVBPY&originHeight=540&originWidth=748&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
2. 点击【产品】->【创建产品】。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136865047-21ae5411-2c25-497f-b8b8-13f26d1eb6b6.jpeg#averageHue=%23d7d6d3&id=ejpyd&originHeight=528&originWidth=855&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
3. 键入此产品的具体名称(服务集)，选择“ARM Linux”，然后点击【提交】。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136865227-301bd4d5-4c41-4776-95bc-829346bd599a.jpeg#averageHue=%23e4e6e5&id=tDG0C&originHeight=548&originWidth=814&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
4. 点击你现在创建的产品的齿轮图标。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136865440-ebd93079-abc7-406c-b7c2-8edf7debb73e.jpeg#averageHue=%23fbfbfb&id=jMIBL&originHeight=150&originWidth=858&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
 5. 添加您想要制作的服务为预置服务。别忘了在设置服务页面勾选“勾选使服务默认启动”。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136865663-41e7e903-a10d-4872-939e-65334262f4cd.jpeg#averageHue=%23fafaf8&id=bdmkJ&originHeight=301&originWidth=828&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
 6. 添加完所有想要的服务后，勾选“check to lock product and create provisioning files”，点击【提交】按钮。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136865850-9224e5ec-0b24-44a4-8c06-95c6758beff8.jpeg#averageHue=%23f8f8f8&id=TJ4DG&originHeight=537&originWidth=826&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
 7. 点击您创建的产品的信息图标。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136866057-345a02ee-bc7c-4100-a591-04bd870b9e47.jpeg#averageHue=%233b9be0&id=uWc5C&originHeight=38&originWidth=140&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136866246-aa981821-ecba-4930-a890-9b181a5d8c46.jpeg#averageHue=%23f8f8f8&id=Bm9AQ&originHeight=103&originWidth=867&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
  8. 复制批量识别码。我们将在接下来的步骤中使用这个代码。
![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136866497-aea157fc-6013-46b0-8742-cfe2b13734ea.jpeg#averageHue=%23f6f6f6&id=svvvL&originHeight=504&originWidth=679&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### EdgeLink Configuration

1. 打开EdgeLink Studio

![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136866747-35f6f9f3-50b3-43b0-a25c-8669ab96c892.jpeg#averageHue=%23e7eeea&id=cmi4g&originHeight=420&originWidth=870&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

2. 设置注册文件的批量识别码

![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136866995-c39de769-d6f0-450b-ab36-f6172fd371f4.jpeg#averageHue=%23111611&id=HPGHB&originHeight=31&originWidth=864&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

3. 删除自动创建的配置文件

![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1717136867157-b6c0abec-ae97-4aee-97bf-76db8e1ea71a.jpeg#averageHue=%231b201b&id=hsrkE&originHeight=25&originWidth=531&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

4. 重启ECU

一旦联网，它应该会自动注册到你创建产品(服务集)的账号，并开启预设服务。
要批量设置的其他ECU需要执行相同的步骤。
