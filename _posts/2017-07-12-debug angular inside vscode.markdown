---
layout: post
title:  "VS Code 1.14发布，可以直接Debug Angular应用"
author: "大漠穷秋"
comments: true
date:   2017-07-12 21:37:10 +0800
category: "web前端"
published: true
excerpt: VS Code 1.14发布，可以直接Debug Angular应用
---

VS Code发布了1.14版本，可以直接Debug Angular应用了！

<img src="{{ "/assets/img/2017-07-12/vscode-debgu-angular.jpg" | relative_url }}" alt="VS Code直接Debug Angular应用" width="100%" class="img-thumbnail rounded"/>

这篇文章很短，但是非常重要，请仔细看哦！

### 第一步：环境配置

- 确保你的Chrome安装在默认位置

- 确保你的VS Code里面安装了<a href="https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome" target="_blank">Debugger for Chrome</a>这个插件

- 把@angular/cli安装到全局空间npm install -g @angular/cli，国内用户请使用cnpm进行安装。注意，你最好升级到最新版本的@angular/cli，避免版本兼容问题。

- 用@angular/cli创建新项目ng new my-app ，本来就已经用@angular/cli创建的项目请忽略这一步，继续往下走，因为只要是cli创建的项目，后面的步骤都是有效的。

- 用VS Code打开项目，进入项目根目录

### 第二步：配置launch.json

<img src="{{ "/assets/img/2017-07-12/vscode-angular2.jpg" | relative_url }}" alt="VS Code直接Debug Angular应用" width="100%" class="img-thumbnail rounded"/>

请参照以上步骤打开launch.json配置文件。

如果你是Windows用户，那么应该是这样的：

<img src="{{ "/assets/img/2017-07-12/vscode-angular3.jpg" | relative_url }}" alt="VS Code直接Debug Angular应用" width="100%" class="img-thumbnail rounded"/>

请把你本地launch.json文件里面的内容先删光，然后把以下内容贴进去：

```ruby
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "chrome",
            "request": "launch",
            "name": "Chrome",
            "url": "http://localhost:4200",
            "webRoot": "${workspaceRoot}"
        }
    ]
}
```

### 第三步：开始Debug

在你的app.component.ts的构造函数里面打个断点，我本地是这样打断点的：

<img src="{{ "/assets/img/2017-07-12/vscode-angular4.jpg" | relative_url }}" alt="VS Code直接Debug Angular应用" width="100%" class="img-thumbnail rounded"/>

打开终端，进入项目根目录，运行ng serve启动项目，然后从VS Code的debug界面启动Chrome：

<img src="{{ "/assets/img/2017-07-12/vscode-angular6.jpg" | relative_url }}" alt="VS Code直接Debug Angular应用" width="100%" class="img-thumbnail rounded"/>

**请注意，一定要用F5再次刷新一下Chrome才能进入断点！**

<img src="{{ "/assets/img/2017-07-12/vscode-angular5.jpg" | relative_url }}" alt="VS Code直接Debug Angular应用" width="100%" class="img-thumbnail rounded"/>

### 最后：补充说明

VS Code最强的地方在于：单元测试代码也是可以Debug的哦！

国内大多数企业并不做单元测试，我就先不写了吧，如果你想对单元测试代码进行Debug，请参考英文原版https://github.com/weinand/vscode-recipes/tree/master/Angular-CLI ，最后一小节Debug Unit Tests。

本文使用的测试项目代码请到这里下载：
<a href="http://git.oschina.net/mumu-osc/NiceFish" target="_blank">NiceFish</a>

（内容可能会多次修改，欢迎常来刷新。如果您觉得文章有用，请捐助我，让我做得更好<a href="http://damoqiongqiu.github.io/donate/index.html">给大漠捐助</a>）