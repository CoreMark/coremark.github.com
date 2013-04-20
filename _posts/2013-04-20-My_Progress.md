---
layout: post
title: "My progress"
description: ""
category: 
tags: []
---

这一切的源头： 
--> N天前, google search: github
--> 搜到杨志平同志 - 如何高效利用GitHub (非常赞的blog, 对于我们菜鸟来说里面的信息量都足够折腾上一段时间了)
--> 里面的一句： 借助于Jekyllbootstrap，可以在Github上快速搭建一个基于jekyll的博客系统。
--> 顺理成章进入： Zero to Hosted Jekyll Blog in 3 Minutes （http://jekyllbootstrap.com/）

折腾了大半天，大概做了这么些动作。
1. 重新gen了 ～/.ssh/id_rsa.pub, 于github 添加了公钥，从此push/pull畅通无阻了。

#1， 官方教程
https://help.github.com/articles/generating-ssh-keys

#2 不用使用Putty来gen
https://help.github.com/articles/set-up-git
Be warned: Do not use PuTTY if you are given the option. GitHub only provides support for openssh.

#3 其中遇到一个exception： Port 22： bad file mumber
解决方案： 于当前用户 /.ssh 下添加一个config文件
content:
Host github.com
User git
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 443

民间blog: http://rangercyh.blog.51cto.com/1444712/749490
stackoverflow： http://stackoverflow.com/questions/7144811/git-ssh-error-connect-to-host-bad-file-number
官方：Using SSH over the HTTPS port
https://help.github.com/articles/using-ssh-over-the-https-port

至此，github上新建了一个repo并初始化, 不出所料访问验证： http://coremark.github.io/ 

例子是跑通了，也大概知道Jekyll是咋回事了？
Jekyll（发音/'dʒiːk əl/，"杰克尔"）是一个静态站点生成器，它会根据网页源码生成静态文件。

【阮一峰 搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门】
http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html
--> 文章的最后一句，给出了2个link: "进一步的完善，请参考Jekyll创始人的示例库，以及其他用Jekyll搭建的blog。"

时不时的就会搜到此人的blog，犀利啊!

按照例子的操作的话，每次都要push到githug上才能生效（至少完成这个例子的时候，我是这么认为的）。心想这么多牛人用，
不能这么麻烦的啦。
所以接下来就查如何在本地起web服务。进入Jekyll官网 click install 
https://github.com/mojombo/jekyll/wiki/install
神马Debian(Ubuntu),靠，小弟是菜鸟，只能在window下玩！！！
看得一头雾水，当瞄到
“If you encounter errors like Failed to build gem native extension on Windows you may need to install RubyInstaller DevKit.”
时， 果断Google去了。。。

search结果锁定（环境对上号了）： Setting up Jekyll on Windows 7
http://zolomon.com/tutorial/2012/02/23/setting-up-jekyll-on-windows-7/

在安装ruby installer 和 它的开发包 DevKit时，期间遇到一个问题，浪费点时间。
后来发现是自己太冒失了，没瞄一眼ruby 官网的说明。
Please download the right one for your version of Ruby:
Ruby 1.8.6 to 1.9.3: tdm-32-4.5.2 （安装了后者)
Ruby 2.0.0: mingw64-32-4.7.2 (安装了前者)
http://rubyinstaller.org/downloads/

发现这个傻X动作后，果断卸载了ruby 2.0.0, 装上 ruby 1.8.6

由于使用中文，免不了遇到编码的问题。
1.打开浏览器出现GBK编码错误
--> 加环境变量 
$export LC_ALL=en_US.UTF-8
$export LANG=en_US.UTF-8

2.运行jekyll –server时出现的编码问题
找到ruby目录下gems/jekyll-0.11.0/lib/jekyll/convertible.rb
29行修改为下面的内容
self.content = File.read(File.join(base, name), :encoding => "utf-8")

用git和jekyll来发表文章,并同步到github
http://www.cnblogs.com/feiyuliu/archive/2012/12/07/2806431.html

Jekyll 本地调试之若干问题
http://chxt6896.github.io/blog/2012/02/13/blog-jekyll-native.html

至此，本地调式也Okay了。

Apply the twitter Theme

To install, run the following rake task in the root of your Jekyll-Bootstrap directory.
rake theme:install git="https://github.com/jekyllbootstrap/theme-twitter.git"

http://themes.jekyllbootstrap.com/preview/twitter/lessons/2011/12/29/jekyll-introduction/

期间遇到的问题： Rake theme install fails.
call 不到git, 解决办法就是把git设置到环境变量里面。
https://github.com/plusjade/jekyll-bootstrap/issues/38

-------------------------华丽的分隔符-----------------------------------

关于这part,还有option :  Portable Python
[Running Jekyll on Windows]
http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html

而Markdown又是神马东东呢？

很有才的“程序猎人”
http://programus.github.io/

知乎：用 Jekyll 和 Octopress 搭建博客，哪个更合适？
http://www.zhihu.com/question/19996679