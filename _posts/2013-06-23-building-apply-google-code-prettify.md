---
layout: post
title: "[Building] 首页简要和代码高亮"
description: ""
category: 
tags: []
---
{% include JB/setup %}
趁周末有空，为这个blog整点如下这些东东：

* 使用RDiscount 来generate markdown.
* 添加了地址栏和收藏夹的icon
* 首页弄了简要（excerpt）
* 代码高亮：Google Code Prettify.

<!--more-->

#### RDiscount
If you prefer to use RDiscount instead of Maruku for markdown, just make sure you have it installed:

    $ sudo gem install rdiscount

And then specify RDiscount as the Markdown engine in your `_config.yml` file to have Jekyll run with that option.

    # In _config.yml
    markdown: rdiscount 

Generate 文件的速度快了很多。

Refers to : [http://jekyllrb.com/docs/extras/](http://jekyllrb.com/docs/extras/)


#### Add shortcut Icon and Bookmark Icon
到目录`_includes\themes\twitter`下， 修改`default.html`

    <link rel="shortcut icon" href="assets/images/www.ico.la_6_16X16_1371972328.ico">
    <link rel="Bookmark" href="assets/images/www.ico.la_6_16X16_1371972328.ico">

Refers to: [如何添加地址栏和收藏夹的icon图标](http://www.yzznl.cn/archives/212.html)

#### Post Excerpts
To generate automatic excerpts, place this inside your main blog post loop:

    {% if post.content contains '<!--more-->' %}
    	{{ post.content | split:'<!--more-->' | first }}
    {% else %}
    	<!-- Case for when no excerpt is defined -->
	{% endif %}

And in the posts themselves, insert `<!--more--> after the section you want exposed. 

	Excerpt content to appear on both the main blog loop and the individual post.

	<!--more-->

	The rest of the post, as seen only in the single blog post.

Refers to : [Easily create blog post excerpts for Jekyll and Github Pages](https://coderwall.com/p/eazb7w)

#### Jekyll with Google-code-pretify
* Download
下载站点是 [google-code-pretify](http://code.google.com/p/google-code-prettify/downloads/detail?name=prettify-small-4-Mar-2013.tar.bz2&can=2&q=); 并解压至目录：`assets\themes\twitter` 

* 配置使用

1. 打开存放在`_includes\themes\twitter`的`default.html`，引加CSS

    <!-- Google Prettify BEG-->
    link href="{{ ASSET_PATH }}/google-code-prettify/prettify.css" rel="stylesheet" type="text/css" media="all"> 
    <!-- Google Pretty end -->

default只显示5倍数的行号，可以修改该文件里面的
    
    From
    {list-style-type:none}
    To:
    {list-style-type:decimal;}

2. 为了页面能够更快的渲染出来，把JS部分放在body 闭合之前.

    <script type="text/javascript" src="{{ ASSET_PATH }}/js/jquery-2.0.0.min.js"></script>
    <script type="text/javascript" src="{{ ASSET_PATH }}/google-code-prettify/prettify.js"></script>
    <script type="text/javascript">
      $(function(){
        $("pre").addClass("prettyprint linenums");
        prettyPrint();
        $('.entry a').each(function(){
          if($(this).attr("href").indexOf("heiniuhaha") == -1){
            $(this).attr("target", "_blank");
          }
        })
      });
    </script>

#### 遇见的问题与解决方法
* Q: File.read不支持utf-8.
* A:到Ruby的安装目录`\lib\ruby\gems\1.9.1\gems\jekyll-0.11.2\lib\jekyll\`找到`convertible.rb`这个文件,并作如下修改

    From:
    self.content = File.read(File.join(base, name))
    To:
    self.content = File.read(File.join(base, name), :encoding => "utf-8")

如果是`jekyll-0.12.0`版本，另外在此文件也有同样问题：

    \lib\ruby\gems\1.9.1\gems\jekyll-0.12.0\lib\jekyll\tags\include.rb
