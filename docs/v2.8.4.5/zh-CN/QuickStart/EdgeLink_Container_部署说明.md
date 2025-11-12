![](https://cdn.nlark.com/yuque/0/2024/jpeg/43815434/1714962374482-dff5e362-b9d5-4f75-88f7-0d566bfe02d2.jpeg#)





































**Revision History**

| Date | Version | Author | Reviewer | Description |
| --- | --- | --- | --- | --- |
| Jan. 26,2022 | 1.0 | Lili.Zheng | Greta Lieske-Dumelle | Initial Release |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |





























**taBLE OF cONTENTS**
[Container版EdgeLink	4](#_Toc119435463)
[1.1	组成	4](#_Toc119435464)
[1.2	宿主机端口占用说明	4](#_Toc119435465)
[1.3	使用方法	5](#_Toc119435466)
## 

## Container版EdgeLink
### 0.1 组成
| 	安装包名称 | 内容 | 作用 |
| --- | --- | --- |
| CONTAINER-edgelink-docker-
2.8.x-xxxxxxxx-amd64.deb
（从研华官网获取） | Agent | 负责EdgeLink Studio工程下载以及EdgeLink Container版本的启动 |
| edgelink_container_2.8.x_Release
_xxxxxxxx.tar.gz（从docker hub获取） | EdgeLink Runtime | 负责EdgeLink Runtime的运行 |


**建议使用环境：**docker环境（支持Ubuntu 18.04 i386版本）
**说明：**默认Container版EdgeLink可以添加最多100点，试用2个小时
**激活方式：**不支持在虚拟机中激活，需要在物理机上进行Container版EdgeLink激活，具体激活方式请联系研华工作人员
### 0.1.1 宿主机端口占用说明
| 端口类型 | 端口号 | 应用程序 | 状态 |
| --- | --- | --- | --- |
| UDP | 6513 | Agent | 安装Agent deb包之后默认占用 |
| TCP | 6001 | Agent | 安装Agent deb包之后默认占用 |
| TCP | 502 | Modbus Server | 在工程中启用Modbus Server时默认占用此端口 |
| TCP | 2404 | IEC104 Channel 1 | 在工程中启用IEC104 Server(channel 1)时默认占用此端口 |
| UDP | 47808 | BACnet Server | 在工程中启用BACnet Server时默认占用此端口 |
| TCP | 504 | WASCADA | 在工程中启用WASCADA时默认占用此端口 |
| TCP | 51210 | OPC UA | 在工程中启用OPC UA Server时默认占用此端口 |
| TCP | 443 | WebService | HTTPS占用此端口 |
| TCP | 41100 | eclr | 在工程中启用eclr时默认占用此端口 |


### 0.1.2 使用方法

1. **为EdgeLink Runtime搭建docker环境**

1. **在 Ubuntu 系统中安装 Docker**

**参考链接 **[https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
_  _

1. **安装EdgeLink Runtime docker image**

**步骤1：下载 edgelink-docker Agent（下载最新版本）**
[https://www.advantech.com.cn/zh-cn/support/details/firmware?id=1-28S1J4D](https://www.advantech.com.cn/zh-cn/support/details/firmware?id=1-28S1J4D)
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962374749-7e46819a-4f88-4517-8f19-11d0dcc8087c.png#)
**步骤2：安装Agent安装包**
 _ __apt install ./CONTAINER-edgelink-docker-2.8.0-202112290544-amd64.deb_
_  __Note: CONTAINER-edgelink-docker-2.8.0-202112290544-amd64.deb 改成实际下载的版本名._
_![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962374887-a96d8c95-1913-4d57-8b32-44a11334242d.png#)_
**特别说明：**
如遇到错误，请按照提示进行依赖包安装后，执行sudo apt --fix-broken install进行deb包的修复安装
**步骤3： 设置串口软链接**
_EdgeLink中, COM1对应/dev/ttyAP0, COM2对应/dev/ttyAP1 依次类推. _
用户需要根据自己本机系统上串口的设备文件进行相应的软链接才可以正确使用串口采集功能
举例说明： 设备实际串口为 /dev/ttyS0 to 对应到EdgeLink COM1.需要执行“_sudo ln -s /dev/ttyS0 /dev/ttyAP0_” 来设置软链接. 注意，绑定前请先确认/dev/ttyAP0没有被其他端口绑定

1. **通过 EdgeLink Studio 下载工程文件**

1. 创建工程，工程节点类型为Container.

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962375091-675c871f-12f8-4914-b73d-053e6232ccbc.png#)
IP地址为运行docker环境的Ubuntu操作系统IP
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962375352-282f1f2c-6c83-4c7d-a56b-16e8ceabf730.png#)

1. 在工程中配置需要的任何功能（可以参考工程部署章节）

这里以采集Modbus TCP设备的数据为例。
在PC上用Modsim模拟一个Modbus TCP设备，通过Container版EdgeLink进行数据采集

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962375588-451a6437-8d64-43e9-a560-8bde0a3d9282.png#)

1. 工程配置完毕后，下载工程.

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962375853-688b6e94-0351-4a5b-ad2d-2eea089567e0.png#)

1. **查看结果**

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962376104-b0fab929-bcbf-468e-85c4-9fbac83f3290.png#)


1. **常用命令**
2. 停止edgelink-docker

_systemctl stop edgelink-docker_

1. 启动 edgelink-docker

_systemctl start edgelink-docker_

1. 重启edgelink-docker

_systemctl restart edgelink-docker_

1. 开机禁用edgelink-docker

_systemctl disable edgelink-docker_

1. 开机启用edgelink-docker

_systemctl enable edgelink-docker_

1. 检查Container 状态

_docker ps_

1. 从宿主机进入到Container

_docker exec -it edgelink /bin/bash_
_![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962376368-6f4e9983-e735-4569-96b8-0c9a2bb73061.png#)_

1. 从Container退回宿主机

![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962376660-bb245993-c8f7-442e-9b0e-e1e6575037c2.png#)

1. 查看Container版log信息（需先从宿主机登入到Container）

_tail -F /var/log/syslog_
![](https://cdn.nlark.com/yuque/0/2024/png/43815434/1714962376838-41587636-2e17-47a6-be6a-dc36f14d4230.png#)

