---
layout: post
title:  "4-安装配置Jekyll"
author: "大漠穷秋"
comments: true
date:   2017-07-03 09:26:33 +0800
category: "文科生都能读懂的Jekyll中文教程"
published: true
excerpt: 如何安装Jekyll并进行基本的配置
---

**非常重要：如果您是开发者，或者英文水平尚可，强烈推荐您阅读官方的原版文档：**

- <a href="https://jekyllrb.com/" target="_blank">Jekyll官方主页（英文版）</a>

- <a href="http://jekyllcn.com/" target="_blank">Jekyll中文网</a>

- <a href="https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/" target="_blank">github官方的帮助文档</a>

### **什么是Jekyll？**

<img src="{{ "/assets/img/jekyll-5/jekyll-github.jpg" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

简而言之，Jekyll是一款静态网页生成器，它是基于Ruby开发的。

Jekyll，注意发音['dʒekil; 'dʒi:kil]，这个名字貌似来自《变身怪医》（Jekyll），这是一部英国电视剧，由哈斯伍德电影公司和Stagescreen制作公司为英国广播公司第一台制作。

Jekyll最初是由Github的联合创始人Tom Preson Warner开发的，我猜这就是为什么Github要内置对Jekyll的支持的原因。Jekyll本身也是一个开源项目，它的github主页在这里<a href="https://github.com/jekyll/jekyll" target="_blank">Jekyll</a>，目前已经有近800个贡献者和3万多个star。

### **用Jekyll有什么好处？**

- Github内置了对Jekyll的支持，你负责编写并提交内容，github会自动帮你构建

- Jekyll很简单，没有数据库，也不需要CMS系统

- Jekyll+Github的方案是免费的

- Jekyll有很多高级的玩法，你可以慢慢探索前进

### **有哪些流弊的项目用了Jekyll？**

大量的Github项目都在使用Jekyll作为文档生成器，例如著名的Bootstrap和React，以下是更多列表：
<a href="https://github.com/showcases/github-pages-examples" target="_blank"> GitHub Pages examples</a>

### **安装并配置运行环境**
Jekyll是基于Ruby开发的，所以你需要先把Ruby和RubyGems装好。请分别点以下两个链接，根据你的操作系统类型，选择下载并安装：

- <a href="https://www.ruby-lang.org/zh_cn/downloads/" target="_blank">Ruby官方下载页</a>

- <a href="https://rubygems.org/pages/download/" target="_blank">RubyGems下载页</a>

安装完成之后，打开终端测试一下有没有装成功。

<img src="{{ "/assets/img/jekyll-5/install-ruby.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

如果没有报错，说明Ruby环境OK。

### **用Jekyll创建第一个项目**
在终端依次执行以下命令：

```ruby
gem install jekyll bundler

jekyll new myblog

cd myblog

bundle exec jekyll serve
```
打开你的浏览器，访问http://127.0.0.1:4000/ ，看到以下页面说明一切都OK：

<img src="{{ "/assets/img/jekyll-5/jekyll-welcome.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

在你关机之后，下次需要再次启动jekyll继续编写文章的时候，请这样做：

```ruby
cd myblog

bundle exec jekyll serve
```

### **把代码提交到你的github主页上去**

你本地的环境已经OK了，来尝试一下把内容推送到github上去吧。

在上一篇<a href="http://damoqiongqiu.github.io/jekyll/2017/07/03/%E5%88%A9%E7%94%A8github%E5%92%8Cjekyll%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BABlog-4.html">3-注册github账号并创建项目</a>中，你已经在github上创建了项目，并且克隆到了本地。那么，请把myblog目录里面Jekyll自动生成的所有内容全部复制一份，粘贴过去吧！

<img src="{{ "/assets/img/jekyll-5/jekyll-github-repo.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

注意，把.sass-cache和_site这两个目录添加到.gitignore文件里面去，目的是告诉git不要把这两个目录里面的内容推送到github上去，这是你本地用的，github不需要这些。如果你把_site目录推送到github仓库，github就不会自动帮你构建了。

我本地的.gitigore文件里面内容如下，你可以拷贝粘贴到你的.gitignore文件里面去：

_site

.sass-cache

.jekyll-metadata

好了，到这里为止，你可以把代码推送到github仓库去了，还记得怎么commit和push吧？忘了的话请参考下图：

<img src="{{ "/assets/img/jekyll-4/git-commit.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-4/git-push.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

OK，等传输完成之后，去你的github仓库看看文件是不是都已经提交上来了。接下来打开你自己的个人首页，刷新看看有没有内容  http://你刚才注册的名字.github.io

注意，如果你是第一次push，github可能会等10分钟之后才会帮你构建，后续的所有push都会立即构建，所以如果现在没有内容的话，等10分钟再来刷新一下吧。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）