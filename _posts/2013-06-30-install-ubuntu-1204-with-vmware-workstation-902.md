---
layout: post
title: "Install Ubuntu 12.04 with VMware workstation 9.0.2"
description: ""
category: 
tags: []
---
{% include JB/setup %}


一同事问在VMware装完 ubuntu之后，联网不行，咋办。虽然之前折腾过，但这东西怎么可能记得住呢？我想这不是神马稀奇问题，Google下下，应该就能解决了吧。但对方说，已Google过。无法解决～ 故此，趁周末我也来玩玩。

<!--more-->

机子环境：ThinkPad X230 + Win7 OS.

### VMWare workstation: 

----------------------------------------------------

#### wiki扫盲和download

维基百科[wiki](https://zh.wikipedia.org/wiki/VMware_Workstation)
> VMware Workstation是VMware公司推出的一款桌面虚拟计算软件。

> 当前最新的版本是 9.0.2 （2012年8月23日）支持Windows 8宿主机

VMware收费软件来的，需要注册码。怎么做你懂的啦。

下载时，需要注册个帐号先。官方下载地址是：https://my.vmware.com/web/vmware/info/slug/desktop_end_user_computing/vmware_workstation/9_0

>VMware-workstation-full-9.0.2-1031769.exe

>File size: 430M

>File type: exe

>Release Date: 2013-03-07

>Build Number: 1031769

>VMware Workstation for Windows 32-bit and 64-bit with VMware Tools 

>MD5SUM: b4db8858e5dc06e50a800c53c1431963 

>SHA1SUM: 0944bee726e30ea2ad895295fe543f55119c11df

E文再怎么破就不建议使用神马汉化版～

#### 安装

在安装过程中，需要设置HTTPS Port 端口号，default is 443. 由于443已被占用。change to 998.

![Config https port]({{ site.url }}/assets/images/2013_06_29_vmware_https_port.png)

安装完毕！

![VMware workstation界面]({{ site.url }}/assets/images/2013_06_29_vmware_9.png)


### Ubuntu

-------------------------------------
#### wiki扫盲和download

维基百科：[wiki](https://zh.wikipedia.org/zh-cn/Ubuntu)
>Ubuntu是基於Debian發行版和GNOME桌面環境，與Debian的不同在於它每6個月會發佈一個新版本，每2年发布一个LTS长期支持版本。 普通的桌面應用版可以獲得发布后18個月内的支援，標為LTS（长期支持）的桌面應用版可以獲得更長時間的支援。

当前最新版本是13.04， 选择下载12.04 LTS.

Download From:

[ubuntu-12.04.2-desktop-amd64.iso](http://www.mirrorservice.org/sites/releases.ubuntu.com//precise/ubuntu-12.04.2-desktop-amd64.iso)

[ubuntu-12.04.2-desktop-i386.iso](http://releases.ubuntu.com/precise/ubuntu-12.04.2-desktop-i386.iso)

Release note: [12.04](http://releases.ubuntu.com/12.04/)

* MD5 - amd64: b436b6d4c7de064652f30d783bda5b4e
* MD5 - i386: 90a4c7bd3901cd980cd4b48198e84eb1

这年头的神马病毒，木马很常见。下载完后都会对下软件check sum. 
#### 安装

##### 插曲

一开始下载的是64bit ISO，为下面出问题奠定了基础啊。

问题： “Software virtualization is incompatible with long mode on this platform,...”

解决方案： 修改宿主BIOS里面的Intel Virtual Technology From 'Disable' to 'Enable'.

Refers to [排除问题提示“Software virtualization is incompatible with long mode on this platform,...”](http://ihorse.blog.51cto.com/2054092/754112)

##### 图解安装！

[【原创】用VMware 8安装Ubuntu 12.04详细过程（图解）](http://www.cnblogs.com/achillesyang/archive/2012/06/21/2557152.html)

安装这个图解一步步做，想装不成功都难。

装完这个之后还要装VMware Tools 来解决无法全屏的问题。

Google下下就又有图解～

[图解解决不能全屏的问题！Ubuntu 12.04安装虚拟工具VMware Tools](http://www.linuxsight.com/blog/4110)

------------------------------
至此，全部安装完毕。联网也正常。完全没有遇到同事所说的问题～
![Ubuntu 12.04]({{ site.url }}/assets/images/2013-06-29-ubuntu.png)