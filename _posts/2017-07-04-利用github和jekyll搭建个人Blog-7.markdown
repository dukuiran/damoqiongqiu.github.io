---
layout: post
title:  "6-提交第一篇文章"
author: "大漠穷秋"
comments: true
date:   2017-07-04 10:44:24 +0800
category: "Jekyll"
published: true
excerpt: 利用Jekyll编写第一篇文章，并推送到Github。
---

<img src="{{ "/assets/img/jekyll-7/article-1.jpg" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

你可能已经发现了，所有的文章都应该放在_posts这个目录里面，这样Jekyll才会自动帮你把它们编译成html。

Jekyll对项目的目录结构做了规范，我们最好根据它的规范来做，避免出现意外的情况。除了_posts之外，Jekyll还定义了很多其它的目录，你可以把这些目录看成是写死的，而且名字是不能改的，改了Jekyll就不认识了。详细的目录结构定义请看这里：[Jekyll目录结构定义](http://jekyllcn.com/docs/structure/)

对于这些目录的玩法，我会一点一点教会你，现在我们只关注_posts这个目录。

现在，你的_posts目录里面应该只有一份文件"2017-07-04-welcome-to-jekyll.markdown"，这是Jekyll自动生成的欢迎页，我们来尝试创建一份自己的文件。

在_posts目录里面新建一个普通的文件，命名为"2017-07-04-my-article-1.markdown"，你也可以通过拷贝的方式创建。注意文件名，Jekyll对文件名有自己的要求，所以我们必须采用上面这种方式来命名，里面尤其不要带有非英文字符和特殊字符。在你的代码编辑器里面打开新文件，删掉所有内容，然后把以下内容粘贴进去：

```ruby
---
layout: post
title:  "这是我自己的一篇文章"
date:   2017-07-04 10:51:20 +0800
categories: jekyll update
---
```

这个看起来有点儿奇怪的头部内容是一种叫做YAML的格式头，在把你的markdown文件转换成HTML的过程中，Jekyll会检查这个头部的声明，做一些必要的处理。

除了这个头部声明之外，接下来你可以随意编写自己的内容了，遵守Markdown格式的规范即可。忘了Markdown格式应该怎么写了？再打开这篇文档看看<a href="http://www.appinn.com/markdown/" target="_blank">http://www.appinn.com/markdown/</a>

<img src="{{ "/assets/img/jekyll-7/article-2.jpg" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

在写好了你自己的内容之后，先把你本地的Jekyll服务器启动起来看看效果，还记得怎么起吗？打开你的命令行，进入你的工程目录，然后就可以启动了，示例如下：

```ruby
cd myblog

bundle exec jekyll serve
```

起来之后，打开你的浏览器，访问http://localhost:4000，你应该可以看到如下内容：

<img src="{{ "/assets/img/jekyll-7/article-3.jpg" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

OK之后，可以把你的文章push到github上去了，还记得怎么commit和push吧？忘了的话去前面的文章里面看看。

push完之后，打开你在github上的主页 http://你在github上的用户名.github.io ，应该能看到和你本地同样的内容了！

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）