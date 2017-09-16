---
layout: post
title:  "12-为你的Jekyll站点添加分类"
author: "大漠穷秋"
comments: true
date:   2017-07-07 22:51:57 +0800
category: "Jekyll"
published: true
excerpt: 为你的Jekyll站点添加分类
---

随着时间的推移，你写的文章会越来越多，这时候你可能希望能够分类展示，就像这样：

<img src="{{ "/assets/img/jekyll-13/category-1.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

Jekyll有category插件可以实现这一点，https://jekyllrb.com/docs/plugins/ 。这些插件看起来挺繁琐的，所以我们来挑战一下难度，尝试自己写代码来实现。

首先，在你的_layouts目录里面新建一个名为category.html的文件，然后把如下代码拷贝粘贴进去：

```ruby
{% raw  %}
--- 
layout: default 
---
{% assign rawcats = "" %}
{% for post in site.posts %}
  {% assign tcats = post.category | join:'|' | append:'|' %}
  {% assign rawcats = rawcats | append:tcats %}
{% endfor %}

{% assign rawcats = rawcats | split:'|' | sort %}
{% assign cats = "" %}
{% for cat in rawcats %}
  {% if cat != "" %}
  {% if cats == "" %}
    {% assign cats = cat | split:'|' %}
  {% endif %}
  {% unless cats contains cat %}
    {% assign cats = cats | join:'|' | append:'|' | append:cat | split:'|' %}
  {% endunless %}
  {% endif %}
{% endfor %}

<div class="row">
  <div class="col-md-9">
    <div class="list-group">
        {% assign date_format = site.minima.date_format | default: "%Y-%m-%d %H:%M:%S" %}
        {% for ct in cats %}
            <li class="list-group-item list-group-item-info" id="{{ ct | slugify }}"><strong>{{ ct }}</strong></li>
            {% for post in site.posts %}
                {% if post.category contains ct %}
                  <a href="{{ post.url | relative_url }}" class="list-group-item list-group-item-action flex-column align-items-start">
                    <div class="d-flex w-100 justify-content-between">
                      <h5 class="mb-1">{{ post.title | escape }}</h5>
                      <small>{{ post.date | date: date_format }}</small>
                    </div>
                  </a>
                {% endif %}
            {% endfor %}
        {% endfor %}
    </div>
  </div>
  <div class="col-md-3">
  </div>
</div>
{% endraw %}
```

然后，修改你的index.md，改成layout: category 。

接着，给你的每一篇文章头部加一个category配置项，就像这样：

<img src="{{ "/assets/img/jekyll-13/category-2.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

这样就OK啦，启动你本地的Jekyll看看效果吧！

噢对，你想问那些代码是什么意思对吧？抱歉，我也不太熟悉Ruby，是对着<a href="https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/" target="_blank">这篇文章</a>一边猜一边改写的。如果你想深入学习Ruby的话，去它的官方网站看看，有中文版哦。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）