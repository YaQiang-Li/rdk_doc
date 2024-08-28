---
sidebar_position: 2
---

# 1.2.2 RDK X5



在使用RDK X5开发板前，需要做下述准备工作。

## 烧录准备

### **供电**

RDK X5开发板通过USB Type C接口供电，需要使用支持**5V/3A**的电源适配器为开发板供电。

:::caution

请不要使用电脑USB接口为开发板供电，否则会因供电不足造成开发板**异常断电、反复重启**等异常情况。

更多问题的处理，可以查阅 [常见问题](../../08_FAQ/01_hardware_and_system.md) 章节。

:::


### **存储** 

RDK X5开发板采用Micro SD存储卡作为系统启动介质，推荐至少8GB容量的存储卡，以便满足Ubuntu系统、应用功能软件对存储空间的需求。


### **显示** 


RDK X5开发板支持HDMI显示接口，通过HDMI线缆连接开发板和显示器，支持图形化桌面显示。



### **网络连接**


RDK X5开发板支持以太网、Wi-Fi两种网络接口，用户可通过任意接口实现网络连接功能。


## 系统烧录


RDK套件目前提供Ubuntu 22.04系统镜像，可支持Desktop桌面图形化交互。

:::info 注意

**RDK X5 Module**出厂已经烧写测试版本系统镜像，为确保使用最新版本的系统，<font color='Red'>建议参考本文档完成最新版本系统镜像的烧写</font>。
:::

### 镜像下载 {#img_download}


点击 [**下载镜像**](https://archive.d-robotics.cc/downloads/os_images)，进入版本选择页面，选择对应版本目录，进入3.0.0版本系统下载页。


下载完成后，解压出Ubuntu系统镜像文件，如`ubuntu-preinstalled-desktop-arm64.img`

**版本说明：**

- 3.0版本：基于RDK Linux开源代码包制作，支持RDK X5派、X3模组等全系列硬件


:::tip

- desktop：带有桌面的Ubuntu系统，可以外接屏幕、鼠标操作
- server：无桌面的Ubuntu系统，可以通过串口、网络远程连接操作
:::



### 系统烧录


:::tip

在烧录Ubuntu系统镜像前，需要做如下准备：
- 准备至少8GB容量的Micro SD卡
- SD 读卡器
- 下载镜像烧录工具balenaEtcher（可[点击此处下载](https://www.balena.io/etcher/)）
:::

balenaEtcher是一款支持Windows/Mac/Linux等多平台的PC端启动盘制作工具，制作SD启动卡流程如下：
1. 打开balenaEtcher工具，点击`Flash frome file`按钮，选择解压出来的`ubuntu-preinstalled-desktop-arm64.img`文件作为烧录镜像 

    ![image-X3-Update-balena1](../../../static/img/01_Quick_start/image/install_os/image-X3-Update-balena1.png)

2. 点击`Select target`按钮，选择对应的Micro SD存储卡作为目标存储设备  

    ![image-X3-Update-balena3](../../../static/img/01_Quick_start/image/install_os/image-X3-Update-balena3.png)

3. 点击`Flash`按钮开始烧录，待工具提示`Flash Complete`时，表示镜像烧录完成，可以关闭balenaEtcher并取出存储卡

    ![image-X3-Update-balena4](../../../static/img/01_Quick_start/image/install_os/image-X3-Update-balena4.png)


### 启动系统


首先保持开发板断电，然后将制作好的存储卡插入开发板的Micro SD卡槽，并通过HDMI线缆连接开发板与显示器，最后给开发板上电。

系统首次启动时会进行默认环境配置，整个过程持续45秒左右，配置结束后会在显示器输出Ubuntu系统桌面。



:::tip 开发板指示灯说明



* **<font color='Green'>绿色</font>** 指示灯：点亮代表硬件上电正常



如果开发板上电后长时间没有显示输出（2分钟以上），说明开发板启动异常。需要通过串口线进行调试，查看开发板是否正常。

:::



Ubuntu Desktop 版本系统启动完成后，会通过 HDMI 接口在显示器上输出系统桌面，如下图：

![image-desktop_display.jpg](../../../static/img/01_Quick_start/image/install_os/image-desktop_display.jpg)

## **常见问题**  

首次使用开发板时的常见问题如下：

- **<font color='Blue'>上电不开机</font>** ：请确保使用[供电](#供电)中推荐的适配器供电；请确保开发板的Micro SD卡已经烧录过Ubuntu系统镜像
- **<font color='Blue'>使用中热插拔存储卡</font>** ：开发板不支持热插拔Micro SD存储卡，如发生误操作请重启开发板



### **注意事项**

- 禁止带电时拔插除 USB、HDMI、网线之外的任何设备
- RDK X5 的 Type C USB 接口仅用作供电 
- 选用正规品牌的USB Type C 口供电线，否则会出现供电异常，导致系统异常断电的问题



:::tip

更多问题的处理，可以查阅 [常见问题](../../08_FAQ/01_hardware_and_system.md) 章节，同时可以访问 [D-Robotics 开发者官方论坛](https://developer.d-robotics.cc/forum) 获得帮助。

:::