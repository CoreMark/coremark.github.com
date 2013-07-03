---
layout: post
title: "联想 X230 - wireless radio button is missing"
description: ""
category: 
tags: [Lenovo]
---
{% include JB/setup %}

公司分配的Laptop，上班时default会插网线来连接网络。但是逢开会时，需拔掉网线，带着Laptop进会议室。这个时候无线网络经常连接不上。

这个问题困扰多时，今晚有空就查了查。

一开始以为是无线网卡驱动的问题，但是由于无线连接又时好时坏的，所以断定不是无线网卡驱动的问题。

经Google search：

**The root cause** : AcSvc service was not started, but starting it manually enabled the utility.

通过以下测试，完全resolve this problem.
<!--more-->

* 现象一：
![wireless radio]({{ site.url }}/assets/images/20130703/001.png)

* 现象二：
![wireless radio]({{ site.url }}/assets/images/20130703/002.png)

###### Steps to resolve it.

* Step 1:
![wireless radio]({{ site.url }}/assets/images/20130703/003.png)

* Step 2:
![wireless radio]({{ site.url }}/assets/images/20130703/004.png)

* Step 3:
![wireless radio]({{ site.url }}/assets/images/20130703/005.png)

* Expected result:
![wireless radio]({{ site.url }}/assets/images/20130703/006.png)


------------------EOF------------------
