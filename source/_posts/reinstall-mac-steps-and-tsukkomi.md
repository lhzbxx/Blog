---
title: 重新搭建Mac的开发环境及一些吐槽
date: 2016-09-05 16:14:31
updated: 2016-09-05 16:14:31
tags:
  - 备忘
  - 个人经历
categories: 随想录
---

昨天我的MBP突然就血崩了，真的是猝不及防。

症状如下：能够连接到互联网，DNS、HOSTS、VPN、WiFi均没有任何问题，但是就是无法通过任何官方应用程序中连接到苹果服务器，也就是说，App Store、iCloud、Safari、Simulator的联网功能全部挂掉了。

倒腾了大半天时间，改了无数个配置，还原了一些东西，重启了N次，依旧没有解决这个问题，所以我只能动用终极绝招——彻底重装系统。

但是重装以后各种配置都没了啊，各种安装的东西统统消失了啊！

以前一直想记录自己的开发环境的配置，最好写出来一个自动化的脚本出来，但是一直都懒得做。

今天就记录一下自己的开发环境配置。

<!-- more -->

## 吐槽

不管怎么样，我一定要先吐槽一下Mac，或者说是Mac OS X，竟然敢在即将升级到macOS的前两天挂掉！

首先，Mac到底好不好用？

说实话，如果你做iOS开发或者把它当做一个Terminal+Editor，其实Mac还是相当好用的，内存管理的很棒，UI和交互做得非常流畅。

但是。

你不能拿Mac做下面这样的事：

1. 观看通过RMTP+Flash实现的网络直播，它会变得超超超级烫手。
2. 部署大量（>3个）的服务，它真的、真的会变得超卡，UI都会有明显卡顿。
3. 做iOS开发时候插各种iPhone，分分钟吃掉30G+的存储空间。

我还遇到过同样诡异的bug，就是通知消息卡住，而且Fn组合键全都失效。

所以，结论是：MBP对我来说就是一个Terminal+Editor+iOS Develop Environment。

## 开发环境

### 软件

* iTerm2，终端利器，不解释了。
* Xcode，必要的开发环境。
* Chrome，除了Coding另外50%的时间应该在这上面了。
* JetBrains系列，IntelliJ IDEA Ultimate、AppCode和Android Studio。
* Dash，离线查看文档用，虽然我很少用。
* Code Runner，简单的测试代码能否跑通。
* Charles，抓包工具，非常实用！
* 
* Paw3，测试、查看API很有用！
* Sketch，查看设计搞&导出3X图片。
* Sublime Text，编辑器啊！
* 网易云音乐，听歌啊。
* 微信，虽然我不太想用，但周围人都在用。

### CLI

* Git，没有它我活不下去！
* Python3
* NPM
    * Hexo，博客嘛！
    * Ionic
    * React Native
    * Vue
* Composer
* JDK

### 插件

* Xcode插件
* Sublime Text插件
* JetBrains插件
* Android Studio插件
* Paw3插件

### 配置

* Vim
