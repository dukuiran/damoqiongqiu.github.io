---
layout: post
title:  "7-Jekyll换肤"
author: "大漠穷秋"
comments: true
date:   2017-07-04 20:40:57 +0800
category: "Jekyll"
published: true
excerpt: 如何安装、配置Jekyll新的皮肤。
---

<img src="{{ "/assets/img/jekyll-7/article-3.jpg" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

在上一小节里面，我们已经尝试编写了一篇自己的文章。

不过，展示出来的样式有点儿怪怪的，我们来尝试换一种皮肤看看。在动手之前有一些注意点需要知道，要不然没法搞：

- Jekyll的皮肤包是基于gem的一种目录结构，里面的目录名和文件名都是定好的。

- 使用Jekyll自动创建项目的时候，默认使用一种叫做Minima的皮肤。

- 与皮肤有关的这些目录和文件默认不在项目里面，而是在系统里面安装gem包的地方。比如，如果你想知道默认皮肤Minima的目录在哪里，可以通过bundle show minima 来查找，以下是我自己机器上的存储路径：

```ruby
E:\Test\myblog>bundle show minima

D:/Ruby24-x64/lib/ruby/gems/2.4.0/gems/minima-2.1.1
```

打开以上目录，可以看到如下内容：

<img src="{{ "/assets/img/jekyll-8/minima-dir.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

- 用户可以通过覆盖的方式来自定义自己的外观，只要上面这些内容拷贝一份，粘贴到你自己的项目里面就可以了。在编译的时候，Jekyll会优先使用你自己项目目录下的皮肤定义。

- Github不能支持用户发布的所有皮肤包，目前只能支持有限的几种，请点这里查看<a href="https://pages.github.com/themes/" target="_blank">github能支持的Jekyll皮肤包</a>

- 用户也可以制作、发布自己的皮肤包供别人使用，只要遵守Jekyll皮肤包的结构就可以了。（咱还是先把自己的事儿管好，先别想着去拯救世界行不行？）

关于Jekyll的皮肤机制，完整的文档请点这里<a href="https://jekyllrb.com/docs/themes/" target="_blank">Themes</a>

好了，我们来选一种Github能支持的皮肤，换掉默认的Minima，试试手感。就用"Architect"这个皮肤吧，名字看起来吊吊的。还是用上一节里面最简单的myblog这个项目做例子，请按照以下步骤依次操作：

- 第一步，修改配置文件。在你的编辑器中打开项目根目录下的Gemfile文件，参照红框中的内容进行修改：

<img src="{{ "/assets/img/jekyll-8/gemfile.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

再打开_config.yml，同样参照红框中的内容修改：

<img src="{{ "/assets/img/jekyll-8/config.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

- 第二步，用gem安装皮肤。打开命令行，执行以下命令：bundle install

- 第三步：把你项目里面，index.md和about.md，包括_posts目录中的文章头部的layout配置项全部改成default，就像这样：

<img src="{{ "/assets/img/jekyll-8/index.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-8/my-first-blog.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

- 第四步：在命令行里面执行bundle exec jekyll serve启动项目，打开你的浏览器访问http://localhost:4000 ，你会看到以下效果：

<img src="{{ "/assets/img/jekyll-8/new-theme.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

怎么样，换肤成功了吧？

对于其它皮肤，操作的方式是类似的，你有兴趣的话自己试试看吧。

"Architect"这款皮肤是极其简单的一种风格，文件之间的链接都需要你自己去添加。基本上Github支持的那些皮肤用起来都挺蛋疼的，所以，后面我们会尝试完全自己来编写页面，不使用这些默认的皮肤。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）