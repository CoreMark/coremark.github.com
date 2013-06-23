---
layout: page
title: Welcome to my Home
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <li>
    	<span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post。title }}</a>
    	
			<p>{% if post.content contains '<!--more-->' %}
				<div style="border:1px dotted rgb(119, 136, 85); padding:10px;">
					{{ post.content | split:'<!--more-->' | first}}
					<p align="right"><a href="{{post.url}}"> Read more »</a></p>
				</div>
				{% else %}
					<!-- Case for when no excerpt is defined -->
				{% endif %}
			</P>
    	
    </li>
  {% endfor %}
</ul>



