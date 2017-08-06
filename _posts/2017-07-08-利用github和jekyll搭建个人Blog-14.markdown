---
layout: post
title:  "13-Jekyll集成lunr.js进行全文搜索"
author: "大漠穷秋"
comments: true
date:   2017-07-08 07:27:57 +0800
category: "文科生都能读懂的Jekyll中文教程"
published: true
excerpt: Jekyll集成lunr.js进行全文搜索
---

站内搜索也是一个很重要的功能，我是参照<a href="https://learn.cloudcannon.com/jekyll/jekyll-search-using-lunr-js/" target="_blank">这篇文章</a>实现的。

以上文章对应的github代码库在这里https://github.com/CloudCannon/bakery-store-jekyll-template

lunr.js这个工具JS库对应的仓库在这里https://github.com/slashdotdash/jekyll-lunr-js-search

<img src="{{ "/assets/img/jekyll-14/search-1.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-14/search-2.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

核心思路是利用Jekyll内置的API把所有文章遍历一遍，把结果序列化成JSON，存储在window.store这个全局对象里面：

<img src="{{ "/assets/img/jekyll-14/search-3.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

这是一个非常简单的解决方案，有很多缺陷，比如用中文关键词基本上啥都搜不到。后面我再来找一个强一点的工具来试试，如果你知道更好更强的工具，请给我留言。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）