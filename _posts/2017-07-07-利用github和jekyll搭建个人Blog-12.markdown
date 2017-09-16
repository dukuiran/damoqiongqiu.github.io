---
layout: post
title:  "11-Jekyll集成Disqus评论模块"
author: "大漠穷秋"
comments: true
date:   2017-07-07 10:49:03 +0800
category: "Jekyll"
published: true
excerpt: Jekyll集成Disqus评论模块
---

你可能会希望跟你的用户进行一些互动，但是，你并不想自己来开发评论模块（当然也有一些人根本不会写代码^_^），这时候Disqus就可以派上用场了。

**Jekyll的Disqus配置项**

打开_layouts/post.html，你会在里面看到这样的内容：

<img src="{{ "/assets/img/jekyll-12/disqus-1.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

这块代码的意思是说，如果你的_config.yml里面出现了site.disqus.shortname这个配置项，那么就把disqus_comments.html包含进来，从文件名猜测，disqus_comments.html就是用来集成disqus的代码了。

OK，那我们要做的第一件事情，就是拿到这个shortname。

**注册Disqus并拿到你的shortname**

<a href="https://disqus.com/" target="_blank">点击这里</a>注册disqus账号，请按照以下图示一步一步操作：

<img src="{{ "/assets/img/jekyll-12/disqus-2.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-12/disqus-3.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-12/disqus-4.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-12/disqus-5.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

注意上图里面的Website Name，这个名字就是等会要用到的shortname，所以请不要乱起名字啊，起个好点儿的名字，最好带点儿艺术气息？

<img src="{{ "/assets/img/jekyll-12/disqus-6.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

当然是选择免费的啊，个人站点而已，谁想交钱。再说咱是中国人啊，并没有付费的习惯。

<img src="{{ "/assets/img/jekyll-12/disqus-7.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-12/disqus-8.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

注意，这里要填写完整的域名，http:// 头也不能省略的！

<img src="{{ "/assets/img/jekyll-12/disqus-9.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-12/disqus-10.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

怎么样，看到shortname了不？激动不？

**修改配置项，测试disqus能不能用**

打开你的_config.yml，把你刚刚拿到的shortname配置进去：

<img src="{{ "/assets/img/jekyll-12/disqus-11.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

然后打开_includes/disqus_comments.html，为了保证Disqus在你本地和推送到Github之后都能使用，需要修改两个地方：

<img src="{{ "/assets/img/jekyll-12/disqus-12.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

注意，别傻傻就照着图片抄，你得改成你自己的域名啊喂ヽ(●-`Д´-)ノ

好了，到此为止就做完了，启动你本地的Jekyll，刷新页面看看效果吧：

<img src="{{ "/assets/img/jekyll-12/disqus-13.png" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

Disqus还有很多配置项，你自己到它的Admin页面上去随意改改，看看都有些什么效果。

如果你的内容专门针对国内用户，可以尝试一些Disqus的替代品，比如“多说”。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）