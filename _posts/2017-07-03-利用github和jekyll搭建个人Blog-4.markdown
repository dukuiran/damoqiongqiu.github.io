---
layout: post
title:  "3-注册github账号并创建项目"
author: "大漠穷秋"
comments: true
date:   2017-07-03 08:54:29 +0800
category: "文科生都能读懂的Jekyll中文教程"
excerpt: 如何注册github账号并创建仓库
---

这颗星球上有一个神奇的网站叫<a href="https://github.com/" target="_blank">github</a>，它是男人的乐园，女人的噩梦。这么好的网站，你一定想要一个账号对不对？

<img src="{{ "/assets/img/jekyll-4/github-register.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

注册成功之后Sign in（登录）进去，点击Your profile菜单到你自己的用户资料页去看看都有什么内容：

<img src="{{ "/assets/img/jekyll-4/github-yourprofile.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

我目前的资料页是这样的：

<img src="{{ "/assets/img/jekyll-4/my-profile.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

好了，这一段不重要，只是给你show一下我的资料而已，万一有人想Follow我呢，对吧？

点击New Repository菜单，进入创建仓库界面，**下面的内容请看仔细**：

<img src="{{ "/assets/img/jekyll-4/new-repo.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

<img src="{{ "/assets/img/jekyll-4/repo-config.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

我这里有错误提示，因为我已经创建过同名的仓库啦！

创建完成之后，进入项目主页，就像这样：

<img src="{{ "/assets/img/jekyll-4/my-repo.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

当然，我这儿已经有一些内容了，你的仓库里面这时候应该只有一个README.md文件，其它什么都没有才对。

下一步，把这个项目克隆到你本地去，在项目主页上点这里：

<img src="{{ "/assets/img/jekyll-4/clone-menu.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

**Windows用户**

在你的电脑里面任意选择一个目录，在任意空白处右键，选择"Git clone"：

<img src="{{ "/assets/img/jekyll-4/git-clone.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

看到Success了不？说明克隆成功，这样仓库的内容就到你本地了：

<img src="{{ "/assets/img/jekyll-4/clone-success.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

接下来测试一下commit和push。

用你机器上的任意编辑器打开项目根目录下的README.md，如果没有这个文件，你可以手动创建一个，随意输入一些内容，然后在项目根目录里面任意空白处右键，选择Git commit->"master"这个菜单，弹出以下界面：

<img src="{{ "/assets/img/jekyll-4/git-commit.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

commit完成之后，再次在空白处右键：

<img src="{{ "/assets/img/jekyll-4/git-push.png" | relative_url }}" alt="示例" width="100%" class="img-thumbnail rounded"/>

操作完成之后，你刚才修改的内容就被push到仓库里面去啦！

**MAC或Linux用户**

可以用字符终端来把项目代码克隆到本地：

```ruby
git clone https://github.com/damoqiongqiu/damoqiongqiu.github.io.git
```

注意改成你自己项目的路径。

也可以通过SourceTree的图形界面来克隆代码，看你自己的喜好。当然，commit和push的操作也都是在字符终端下面完成的。如果你还不太熟悉字符终端下面操作git的命令，请查看<a href="http://git.oschina.net/progit/" target="_blank">这篇progit中文教程</a>。

**刷新看效果**

把代码推送到Github之后，去你的项目主页上刷新一下，确认一下刚才的内容有没有进来。

现在，你可以打开你的主页看看有没有内容，http://你刚才注册的名字.github.io

当然，你也可以到项目的Settings菜单里面去设置一个theme（主题），然后刷新看看有没有效果。不过这个不重要，因为紧接下来我们会安装jekyll，到时候有更多样式可以选择。

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）