
# Agora-LinuxServer-Recording

*Read this in other languages: [English](README.md)*

## 准备工作

请确保满足以下操作系统要求:
- Ubuntu 12.04 x64 或更高版本
- CentOS 6.5 x64 或更高版本
- gcc 4.4 或更高版本。
- 与公网互通，并能够访问`qos.agoralab.co`
- 每一个录制频道至少1MB+的带宽

## 快速开始

### 创建Agora账号并获取App ID
- 在[Agora开发者中心](https://dashboard.agora.io/cn/signup/) 注册账号
- 在[我的主页]-->[项目管理]创建自己的项目，获取到 AppID
- 该AppID用于运行Agora应用程序
 
 **Note：** 该AppID用于运行你的Agora项目，请妥善保存，勿外泄。

### 下载Agora Recording SDK
- 下载[录制SDK](https://docs.agora.io/cn/Agora%20Platform/downloads)
- 解压下载的SDK包

### 运行

1. 确保以下的UDP端口是打开的(这些端口用来与Agora服务器之间通信)
 - 4001
 - 4030
 - 1080
 - 8000
 - 25000
 
 2. 确保本地端口没有被防火墙禁掉。如果启用了防火墙，则需要放开Agora录制SDK设定的端口范围。你可以为多个录制进程统一配置较大的端口范围（Agora 建议 40000 ~ 41000 或更大）。此时，录制 SDK 会在指定范围内分配录制端口。设置端口范围，你需要配置参数 lowUdpPort 和highUdpPort。
	
	端口类型|范围
	----|----
	接收码流端口|40000 - 41000
	Low UDP Port|40000
	High UDP Port|41000
	
3. 进入`samples/cpp/release/bin`目录下，你可以看到`recorder`可执行程序

4. 运行`./recorder`，即可看到相关用法，填上相应的参数即可进行录制
	```
	./recorder --appId APPID --uid 0 --channel mychannel --appliteDir PATH-TO-PROJECT/bin/AgoraCoreService
	```

## 快速通道
**当前sample**
 - 进入`samples`,执行`make`编译，然后运行编译生成的`./recorder`, 即可看到相关用法

## 联系我们

- 详细信息请参考 [录制快速入门](https://docs.agora.io/cn/Recording/product_recording?platform=All%20Platforms)
- 完整的 API 文档见 [文档中心](https://docs.agora.io/cn/)
- 如果在集成中遇到问题, 你可以到 [开发者社区](https://dev.agora.io/cn/) 提问
- 如果有售前咨询问题, 可以拨打 400 632 6626，或加入官方Q群 12742516 提问
- 如果需要售后技术支持, 你可以在 [Agora Dashboard](https://dashboard.agora.io) 提交工单
