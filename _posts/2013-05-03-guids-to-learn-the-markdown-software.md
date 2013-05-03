---
layout: post
title: "Guids to learn the Markdown software"
description: ""
category: 
tags: [Markdown]
---
{% include JB/setup %}

## 扫盲：What is Markdown
- 中文维基上记载
> Markdown 是一种轻量级标记语言，创始人为約翰·格魯伯（John Gruber）和亞倫·斯沃茨（Aaron Swartz）
- 官网上介绍
> Markdown is a text-to-HTML conversion tool for web writers. Markdown allows you to write using an easy-to-read, easy-to-write plain text format, then convert it to structurally valid XHTML (or HTML).

> Thus, “Markdown” is two things: (1) a plain text formatting syntax; and (2) a software tool, written in Perl, that converts the plain text formatting to HTML.

> Markdown is free software, available under a BSD-style open source license. 

官网上说的很清楚了，第一它是文本格式的语法，第二它是个用Perl语言写的**工具**，该工具可以把文本格式转换为HTML格式。
它的目的就是**易读，易写**.

`官网 document`的域名并不是传统的`www.markdown.com`, 而是放在`创始人John Gruber`的站点下。
> Daring Fireball is written and produced by John Gruber.

Markdown Project: [http://daringfireball.net/projects/markdown/][1]

[1]: http://daringfireball.net/projects/markdown/

*******
## 入门 : 语法学习
  `Downdown`的语法，很多人均声称10分钟就搞懂。确实，浏览下就知道怎么回事了，但是真正写的时候老是需要回去参照document.
  
  `E文太菜`，吸收比较慢，而好奇心又太强，所以只抢先看Chinese Document Edition。
  
+ John  Gruber - [Markdown syntax][2]
+ 中文简体翻译(_E文菜鸟实现10分钟入门_) 晨旭园 - [Markdown语法][3]
+ 中文繁体翻译 (_http://markdown.tw台湾域名哦_) - [Markdown: Syntax][4]
[2]: http://daringfireball.net/projects/markdown/syntax "John  Gruber - Downdown syntax"
[3]: http://www.mceiba.com/develop/markdown-syntax.html "晨旭园 - Markdown语法"
[4]: http://markdown.tw/ "Markdown: Syntax"

*******
## 工欲善其事，必先利其器 : Markdown 编辑器

老是中英输入法切换，所以使用Markdown的硬伤就是语法只认`E文字符`的。故此，急切需要一个所见的所得编辑器。这样就不用写完一大堆，启动服务器（发布）的时候，发现一大坨都粘到一起去了。

### 在线编辑
- Chrome 插件 : [MaDe Editor][5] (已测试，很好)
> MaDe means MArkDown Editor
>
> MaDe的图标在传统印章样式中使用草书，表达了该APP在方圆之中桀傲不驯的狂野内心。
> 而那个“妈”字，则是表达了对世界上最伟大的爱——母爱——的赞美.

###  线下编辑
- [MarkdownPad][6] (不是很爽的是还要先装`Microsoft .NET 4 Client Profile`)
> You may be prompted to install the Microsoft .NET 4 Client Profile if you do not already have it installed.

[5]: https://chrome.google.com/webstore/detail/made/oknndfeeopgpibecfjljjfanledpbkog/details "MaDe Editor"
[6]: http://markdownpad.com "MarkdownPad"

*********
## Reference
* 阳志平的个人网站::技术 - [Markdown写作浅谈][yangzhiping]
[yangzhiping]: http://www.yangzhiping.com/tech/r-markdown-knitr.html "Markdown写作浅谈"