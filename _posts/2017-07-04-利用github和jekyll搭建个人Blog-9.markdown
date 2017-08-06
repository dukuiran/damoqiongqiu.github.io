---
layout: post
title:  "8-修改Jekyll内置的皮肤和默认参数"
author: "大漠穷秋"
comments: true
date:   2017-07-05 09:41:06 +0800
category: "文科生都能读懂的Jekyll中文教程"
published: true
excerpt: 如何修改Jekyll内置的皮肤和一些默认的参数。
---

虽然Github默认能支持好多皮肤，但是它们看起来都很简陋的样子，好些地方都不满足我们强大的审美需求，我们来看看怎么改一改这些皮肤。

我们还是基于Jekyll默认的minima这款皮肤来修改，它看起来比其它皮肤略复杂一些，可以充分描述问题。

首先，打开你的命令行，运行以下命令，找到minima这款皮肤安装的位置：

```ruby
E:\Test\myblog>bundle show minima

D:/Ruby24-x64/lib/ruby/gems/2.4.0/gems/minima-2.1.1
```

可以看到，我本地的皮肤被安装在了D盘里面，在你的系统里面打开上面这个路径，看到如下内容：

<img src="{{ "/assets/img/jekyll-8/minima-dir.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

我们把上面的所有内容都拷贝一份出来，粘贴到myblog这个练习项目的根目录里面去，LICENSE.txt和README.md这两个文件就不要拷贝了：

<img src="{{ "/assets/img/jekyll-9/theme-dir.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

怎么样，这个项目现在看起来比较复杂了对不对？这4个目录里面的内容作用如下：

<img src="{{ "/assets/img/jekyll-9/minima-dir-desc.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

你可以尝试改一改这些文件里面的内容，看看会产生什么效果。你并不需要完全去理解这些文件里面的每一行代码， 你可以一边猜、一边改，多改一些，你就明白它们之间的关系了。就像你可以学会开车，但是你并不需要懂怎么设计制造发动机一样。这种学习方法很酷，对不对？

不过，我还是决定手把手带着你来改一个简单的内容。

Jekyll默认显示的日期格式是英文状态的，就像这样：

Jul 4,2017

这种格式不符合中国人的阅读习惯，我们来把它改成中国人习惯的格式。请分别打开_layouts目录里面的home.html和post.html，然后参照以下图片中的内容进行修改：

<img src="{{ "/assets/img/jekyll-9/date-format-1.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-9/date-format-2.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

改完之后，把你本地的Jekyll运行起来，打开你的浏览器，你会看到：

<img src="{{ "/assets/img/jekyll-9/date-format-result.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

怎么样？6不6？

噢对，有两个配置文件需要改一下，以免后面你手贱运行bundle update的时候出现意外的情况。

请把Gemfile这个文件里的gem "minima", "~> 2.0"这一行给注释掉，同时把_config.yml里面的theme: minima这一行给删掉。

Jekyll还有很多配置项，如果你想探索更多玩法，请参考<a href="http://jekyll.com.cn/docs/configuration/" target="_blank">Jekyll中文网上的这篇教程。</a>

接下来你可以自己自由发挥了，多改一些内容看看会发生什么，我祝你幸福哦！

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）