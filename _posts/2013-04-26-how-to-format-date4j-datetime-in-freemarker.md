---
layout: post
title: "How to format Date4J datetime in Freemarker"
description: ""
category: 
tags: []
---
{% include JB/setup %}

## Requirement
Freemarktr 里面 date, datetime 等的format是为java.util.Date服务的，而本人并没有使用java.util.date而是使用Date4J里面的datetime。
故此就无法使用 [Built-ins for dates][1] 的一些语法了。
例如： 
    	
    ${lastUpdated?string("yyyy-MM-dd HH:mm:ss zzzz")}
    ${nextDiscountDay?string.medium}
    ${nextDiscountDay?string.long}

## Strategy to implement
* 重写Freemarker里面的相关的类/方法， 实现自己的 `${nextDiscountDay?date4JString.long}`
* 要么就把传进来的date4J datetime当作字符串处理， 这样也能整出自己想要的格式（[The string converted to a date value. ][2]）
    
    `<#assign modifiedDate = "${modifiedDate}"?date("yyyy-MM-dd")>`
    `${modifiedDate}`


[1]: http://freemarker.sourceforge.net/docs/ref_builtins_date.html
[2]: http://freemarker.sourceforge.net/docs/ref_builtins_string.html

## 悲剧的example
刚开始在网上搜了下 freemarker example， 于是找到一个Hellow world的例子。 
点击[FreeMarker (FTL) Hello World Tutorial with Example][3]， 进入copy了那段code。然后跑起来 
狂报`找不到template文件的错误`, 可能是本人使用的版本比较高（**2.3.8**)， 而例子里面使用的是版本(**2.2.8**)比较低。

不敢确定**2.2.8**是否是真的跑得起来的。

借助Google之力，很快便resolved掉了。
>FreeMarker template paths are resolved by a `TemplateLoader` object, which you should specify in the `Configuration` object. The path that you specify as the template path is interpreted by the `TemplateLoader`, and is usually relative to some kind of base directory (even if it starts with `/`), that's also called the template root directory for this reason. In your example, you haven't specified any `TemplateLoader`, so you are using the default `TemplateLoader`, which is only there for backward-compatibility, and is nearly useless (and also dangerous). So, do something like this:
    
    config.setDirectoryForTemplateLoading(new File("C:/Users/Jay/workspace/WebService/templates"));

_相关链接_ : [FileNotFoundException when loading freemarker template in java][6]

## Reference
* E文弱的可以快速扫盲by ：[Java模板引擎 FreeMarker][4] 
* 官方地址[http://freemarker.sourceforge.net/][5]
    
    FreeMarker is Free, with BSD-style license.    
    
    

[3]:http://viralpatel.net/blogs/freemaker-template-hello-world-tutorial/
[4]:http://www.oschina.net/p/freemarker
[5]:http://freemarker.sourceforge.net/
[6]:http://stackoverflow.com/questions/14749623/filenotfoundexception-when-loading-freemarker-template-in-java
