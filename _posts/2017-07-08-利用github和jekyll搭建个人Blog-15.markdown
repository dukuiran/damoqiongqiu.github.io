---
layout: post
title:  "14-利用_data目录存储数据"
author: "大漠穷秋"
comments: true
date:   2017-07-08 15:56:44 +0800
category: "文科生都能读懂的Jekyll中文教程"
published: true
excerpt: 利用_data目录存储数据
---
Jekeyll可以读取_data目录下的数据文件，支持YML、JSON、CSV三种格式，我们来试试最简单的JSON格式。

请在你项目的根目录下建一个_data目录，然后在_data目录里面创建一个文件，名为members.json。把下面的内容拷贝粘贴到members.json里面去：

```json
[
  {"name":"Tom Preston-Werner","github":"mojombo"},
  {"name":"Parker Moore","github":"parkr"},
  {"name":"Liu Fengyun","github":"liufengyun"},
  {"name":"大漠穷秋","github":"damoqiongqiu"}
]
```

在你的项目根目录下创建一个members.md文件，把下面的内容拷贝粘贴进去：

```ruby
{%raw%}

---
layout: page
title: ""
permalink: /members/
---

<ul>
    {% for member in site.data.members %}
    <li>
        <a href="https://github.com/{{ member.github }}" target="_blank">
        {{ member.name }}
        </a>
    </li>
    {% endfor %}
</ul>

{%endraw%}

```

启动你本地的Jekyll，访问<a href="http://127.0.0.1:4000/members/" target="_blank">http://127.0.0.1:4000/members/</a>  ，你也可以点这个链接查看我提交到线上的效果<a href="http://damoqiongqiu.github.io/members/" target="_blank">http://damoqiongqiu.github.io/members/</a>

运行效果如下：

<img src="{{ "/assets/img/jekyll-15/data-1.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

利用_data机制，你可以做很多猥琐的事情了，展开你的想象吧！

如果你想试试YML和CSV格式，请看<a href="https://jekyllrb.com/docs/datafiles/" target="_blank">官方的这篇文档</a>。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）