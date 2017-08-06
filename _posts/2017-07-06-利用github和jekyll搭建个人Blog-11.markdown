---
layout: post
title:  "10-利用Google Analytics监控你的Jekyll站点"
author: "大漠穷秋"
comments: true
date:   2017-07-06 21:44:06 +0800
category: "文科生都能读懂的Jekyll中文教程"
published: true
excerpt: 利用Google Analytics监控你的站点
---

你的站点上线之后，你一定很想知道这些问题：

- 每天访问量怎么样？

- 用户都分布在哪些城市？

- 哪些文章的点击量比较高？

- 有多少用户是通过移动端设备访问的？

诸如此类的信息对你创作内容都有很好的指导意义，所以，你需要用Google Analytics（简称GA）这样的监控和分析工具来帮忙。

当然，GA强大的功能远不止于此，它还能提供更多商业级的分析报告。

**Jekyll的Google Analytics配置项**

打开你的Jekyll项目，查看_includes下面的head.html，里面有这样一段内容：

<img src="{{ "/assets/img/jekyll-11/ga-1.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

这里看起来像是跟GA有关的东东，而且我们可以猜测到代码的大意，只要jekyll.environment == 'production' 同时 site.google_analytics这个配置项不为空，就会include（引入）google-analytics.html。

那么google-analytics.html这个文件里面的内容是什么呢？

<img src="{{ "/assets/img/jekyll-11/ga-2.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

看起来是在动态向我们的页面上注射一段JS脚本，代码有点小复杂，我们不去追究它。如果你实在压制不住自己的好奇心，可以在部署好页面之后通过chrome的开发者工具查看这段动态注射的JS脚本是什么内容。

现在我们只要知道，如果在_config.yml里面有google_analytics这个配置项，那么Jekyll在编译时就会帮我们注入GA相关的脚本。google_analytics这个配置项实际上是GA生成的一个ID，叫做“跟踪ID”，每一个网站对应一个唯一的“跟踪ID”。所以，你现在需要做的事情是：注册一个Google账号，然后登录到GA的主页上去配置一下你的个人站点，然后才能拿到这个“跟踪ID”，我拿到的“跟踪ID”是这样的：

<img src="{{ "/assets/img/jekyll-11/ga-3.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

**注册Google账号并登录GA**

注意：以下所有内容都需要科学的上网方式。

打开以下链接注册一个Google帐户<a href="https://accounts.google.com/SignUp" target="_blank">注册Google帐户</a>

注册成功之后，打开<a href="http://analytics.google.com/" target="_blank">GA的主页</a>，用你刚才注册的Google帐户登录进去。然后按照以下图示依次操作：

<img src="{{ "/assets/img/jekyll-11/ga-4.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-11/ga-5.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-11/ga-6.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-11/ga-7.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

注意，GA的界面布局会经常改，如果你看到的版本和以上截图不一样，请自己摸索一番，只要能拿到你的站点对应的“跟踪ID”就可以了。

噢对，Google Analytics的界面目前使用的<a href="https://www.angular.io" target="_blank">Angular</a>版本是1.6.4：

<img src="{{ "/assets/img/jekyll-11/ga-8.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

如果你想了解关于Angular相关的技术点，请查看我发布的系列开源项目和免费视频教程：<a href="http://git.oschina.net/mumu-osc/NiceFish" target="_blank">NiceFish</a>

**推送代码到github，然后登录GA查看效果**

在得到了你自己的“跟踪ID”之后，把它配置到_config.yml里面：

<img src="{{ "/assets/img/jekyll-11/ga-3.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

把代码推送到github，刷新你的GA界面，然后你就可以查看各种跟踪数据和图表了。GA是非常强大的网站跟踪和分析工具，里面有好多好玩的功能，你自己去摸索一番吧！

这是我的个人主页上线一周以来的数据图表：

<img src="{{ "/assets/img/jekyll-11/ga-9.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

看起来不太火爆的样子，需要继续加油。

百度也提供了类似的网站跟踪和分析工具，叫做“百度站长工具”，如果你的站点主要面向的是国内用户，可以采用百度的工具来做。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）