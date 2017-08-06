---
layout: post
title:  "9-用Bootstrap完全自己实现外观"
author: "大漠穷秋"
comments: true
date:   2017-07-06 08:28:53 +0800
category: "文科生都能读懂的Jekyll中文教程"
published: true
excerpt: 用Bootstrap完全自己实现外观
---
Jekyll内置的那些皮肤都不怎么好看，我们还是用Bootstrap自己来做吧，而且这样控制权完全在你了，你可以随时随意修改样式风格。

还是以上一节里面最简单的myblog为例子，请跟着我一步一步来改。

<strong>第一步：引入Bootstrap</strong>

请到<a href="https://v4-alpha.getbootstrap.com/" taraget="_blank">Bootstrap官方的站点</a>上把压缩包下载下来，目前最新的版本是4.0.0-alpah.6。下载好之后解压到myblog项目的assets/css目录里面，就像这样：

<img src="{{ "/assets/img/jekyll-10/bootstrap-dir.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

然后打开_includes/head.html，把下面的内容拷贝粘贴进去：

```html
<link rel="stylesheet" href="{{ "/assets/css/bootstrap-4.0.0-alpha.6/css/bootstrap.min.css" | relative_url }}">
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/tether/1.4.0/js/tether.min.js"></script>
<script src="{{ "/assets/css/bootstrap-4.0.0-alpha.6/js/bootstrap.min.js" | relative_url }}"></script>
```

<img src="{{ "/assets/img/jekyll-10/add-bootstrap-link.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

注意：如果你放bootstrap的目录和这里的不一样，请自己做一些调整。当然，也可以从CDN上面引入Bootstrap，你自己去找一个可用的CDN链接吧，我这里直接放本地是为了后面改一些Bootstrap的样式代码。

<strong>第二步：删掉minima相关的样式，开始写自己的样式</strong>

打开assets/main.scss，把里面的内容改成：

```ruby
@import "my.scss";
```

打开项目根目录下的_sass文件夹，把里面的内容<strong>全部删掉</strong>，然后新建一个名为my.scss文件。

Jekyll当前的版本是用Sass来做CSS预编译的，关于Sass的基本概念语法，请点击<a href="http://sass.bootcss.com/" target="_blank">这个中文版教程</a>查看。简而言之，你可以把Sass看成是CSS的增强版超集，也就是说，你在.sass文件里面写基本的CSS都是没问题的。

到这里为止，你就可以完全按照自己的心意来编写CSS了！

当然，强烈推荐利用CSS的模块化机制，按照业务模块来切分和组织CSS代码，就像这样：

<img src="{{ "/assets/img/jekyll-10/my-sass.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

对于码农们来说，这样组织CSS代码是很自然的事情，因为这和写其它代码是类似的，良好的目录和代码结构可以方便人类理解和后期维护，希望看到这篇文章的非码农们也学习一下哦！

<strong>第三步：写2个小例子帮助你入门</strong>

首先，我们来改一下全局字体，请按照以下图示修改你对应的代码：

<img src="{{ "/assets/img/jekyll-10/my-1.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-10/my-2.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

```css
body{
    font-family: "Microsoft Yahei","微软雅黑",SimSun,sans-serif !important; 
    background-color: #F7F7F7;
}
input, label, select, option, textarea, button, fieldset, legend { 
    font-family: "Microsoft Yahei","微软雅黑",SimSun,sans-serif !important;
}
.main-container{
    padding-top: 70px;
    padding-bottom: 30px;
}
```

改完之后启动你本地的Jekyll：

```ruby
bundle exec jekyll serve
```

打开浏览器访问http://localhost:4000

<img src="{{ "/assets/img/jekyll-10/my-3.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

字体被强制改成了你自己定义的内容了对不对？

呃，不过现在好像界面布局乱掉了，那是因为我们把Minima这个皮肤的样式全删掉了，接下来我们会慢慢改好。

既然引入了Bootstrap，那我们就来加一个响应式的导航条试试吧。

请打开你的_includes/header.html，注意，是hearder.html，不是head.html。把header.html里面的内容全部删除，然后把以下内容粘贴进去：

```html
<nav class="navbar navbar-toggleable-md navbar-inverse bg-inverse fixed-top">
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent"
    aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item">
        <a class="nav-link" href="{{"/" | relative_url }}">我的文章</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="{{"/videos/index.html " | relative_url }}">免费视频</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="{{"/projects/index.html " | relative_url }}">开源项目</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="{{"/social/index.html " | relative_url }}">在线交流</a>
      </li>
    </ul>
    <ul class="navbar-nav">
      <li class="nav-item">
        <a class="nav-link" href="{{"/about/index.html " | relative_url }}">关于我</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="{{"/donate/index.html " | relative_url }}">赞助我</a>
      </li>
    </ul>
  </div>
</nav>
```

刷新页面，就可以看到这个很酷的导航条了：
<img src="{{ "/assets/img/jekyll-10/nav-1.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>


最酷的是，这是一个响应式的导航条，当用户通过移动设备打开你的主页的时候，他会看到收缩成汉堡包形式的导航条：
<img src="{{ "/assets/img/jekyll-10/nav-2.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>

这很酷，不是吗？

当然，你需要把里面的链接都改成你自己的。

到此为止，我们已经摆脱了Jekyll默认的那一套丑陋的外观，可以按照自己的心意随意实现外观了！

关于Bootstrap的详细介绍和用法，请点击官方的<a href="https://v4-alpha.getbootstrap.com/" target="_blank">这个链接</a>仔细学习。Bootstrap在Github上的star数量排名已经是第二名，所以还是强烈推荐您抽时间学一下吧，无论就业还是跳槽，遇到Bootstrap的概率是非常高的！

<img src="{{ "/assets/img/jekyll-10/bootstrap-stars.jpg" | relative_url }}" alt="示例" max-width="100%" class="img-thumbnail rounded"/>


（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）