此文档介绍Edgelink/VPN功能的使用步骤。



Edgelink VPN管理平台地址：[https://vpn.edgelink.cloud](https://vpn.edgelink.cloud)
## 1 注册用户
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049920127-2bce054c-2708-4ecd-9bd9-dbf5089f01a2.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049920316-c917138d-4d53-4eb3-8497-07ad8aa5d54f.png#)
填写邀请码以及其他带*的必填项，点击保存。（邀请码需要通过业务从产品部获取）
邀请码获取流程如下图：
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049920491-bcceffbf-7bec-4b72-a37f-592448b5dde9.png#)


点击保存后出现的信息即为Edgelink Studio需要的连接字串，**需要将此字串填入EdgelinkStudio中**。
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049920662-77a4ddf9-312d-4f2f-9921-3f947d070526.png#)
注册后会受到一封包含连接字串的邮件，如下图
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049920807-b2feb2bb-8ad4-4abd-b3c0-a6fc94430648.png#)

## 2 用户登录
使用刚才注册的账户登录，用户名为电子邮件地址
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049921032-b3bb3105-6dc0-4acf-ad6c-66ceec7f97aa.png#)
**已注册设备：**填入连接字串并下载此Edgelink工程的网关，会在此处出现。
此时网关还没有vpn分配的ip，确认后，设备会在已组网设备中出现，网关才可以拿到vpn的ip
**已组网设备：**vpn网络中存在的网关设备。
**客户端 (Edgelink Studio主机)**：安装Edgelink Studio的电脑。 

## 3 配置Edgelink Studio
在Edgelink Studio工程中添加连接字串，下载工程
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049921255-51dbd85d-c7ce-4180-99c9-f15d4ee88dd0.png#)
**Device Name：**管理平台中看到的设备名称
**Syslog Level：**打印出的日志等级
**Connect String：**注册用户后拿到的连接字串

## 4 管理平台中确认设备
打开EdgelinkVPN管理平台，可在已注册设备中看到此网关（此时网关没有vpn的ip）
点击确认，设备会移动到已组网设备中，此时网关才会拿到VPN的ip
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049921534-52899b78-0add-44a2-8f86-f580fb2b5707.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049921754-a1a07ea6-4ed9-4220-883b-0617bbca97d8.png#)
## 5 配置Edgelink Studio的电脑需要用的vpn
点击添加客户端，填入带*的必填项后，点击保存
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049921949-d011738a-ada4-4230-ad69-965127652d9a.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049922139-c762d693-fbd3-42ff-95fa-3e0c541fcbd6.png#)
添加客户端后，可下载连接需要使用的ovpn客户端文件
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049922309-51e7c9ec-7c1b-4a5c-a766-9feb14540425.png#)
使用openvpn client工具连接即可。
此例中使用openvpn GUI，将ovpn文件放到\OpenVPN\config目录下，连接即可
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049922509-1573113a-c5fd-4dce-9071-1bb0d249e2e5.png#)
## 6 连接测试
电脑和网关ip互相能ping通即可。
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049922727-1defac79-7889-4d84-ba09-bdac105cd440.png#)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1717049922897-b0ccd2bb-5e27-46b3-81e2-a58c4b452bc0.png#)


配置好以上，就可以使用vpn网络来远程运维网关了。
