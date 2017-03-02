---
title: 「Redefined」搭建与部署
date: 2016-06-10 01:51:51
updated: 2016-06-10 17:30:27
categories: 开发手札
tags:
  - 备忘
  - Hexo
  
---

关于开发那些事儿，其实蛮多想说的。自己也总结了一些干货，涉及到各个方面，虽然大多数来自前人的经验，但也有一些自己的东西。

不过从哪开始呢，还真是有点纠结。

虽然看过很多大牛的分享，但自己着实写的比较少。那就先从构建和部署本博客开始吧，从简单的写起练练手，同时也算作一个备忘。

<!-- more -->

## 准备

### 依赖

Redefined是基于Hexo，并使用第三方主题NexT构建的。

这里就不再赘述Hexo+NexT的优点了。

很久之前我是想自己手动搭建博客的，不过实在太费事了，人生苦短，没必要什么都自己来。况且Hexo这个轮子本身质量还是不错的，起码有完整的社区和足够的开发人员，就易用性和简洁度来说，自己做的还真比不上它。

在你搭建之前，需要准备两个东西。

* Git
* Node.js

Hexo是基于Node构建的，使用NPM进行包管理，理论上来说你只需要一个「package.json」就OK啦。

### 初始化

``` bash
$ npm install hexo-cli -g
$ hexo init blog
```

### 工作流

我一直挺喜欢「Workflow」这个词，觉得它挺酷的。就像是在玩Minecraft一样，那种从无到有、慢慢地、有序地创造一个世界的感觉，非常美妙。

稍微扯远了。

就简单说一下博客到底怎么运行的——我是这么做的：

1. 创建一篇新的文章

	``` bash
	$ hexo new post xxx
	```
2. 编辑文字

	``` bash
	$ vim xxx
	```
3. （可选）本地测试

	``` bash
	$ hexo server
	```
4. 生成静态文件

	``` bash
	$ hexo generate
	```
5. 发布到远程服务器

	``` bash
	$ hexo deploy
	```

当然，这是把配置都抛到了一边，从本质上来说，你只需要两步就可以完成。

第一步，用Markdown编辑好一篇文章，放在/source/_post目录下。

第二步，双击piu.sh.

其中「piu.sh」是blog目录下的文件。

{% codeblock %}
hexo generate --deploy
{% endcodeblock %}

就是这么简单。

## 运行

### 配置

这一块其实是内容最多的，我花了蛮久的时间在配置项上。

不过这真的只是纯粹的体力活，按照文档说明，是没有任何问题的，除非你看走眼了……

我个人用的第三方服务有：

* 多说
* 百度统计
* Swiftype

### 服务器

命令：

``` bash
$ hexo server
```

默认会在 http://localhost:4000 下预览。

### 静态文件

命令：

``` bash
$ hexo generate
```

Hexo生成的静态文件全都放在/public目录下。

最粗暴的部署方式就是直接把下面的文件拿出来，丢在服务器上，然后用Nginx服务器处理请求。

### 部署

命令：

``` bash
$ hexo deploy
```
这个部署还是要提前设置的。

我个人使用了两种部署，一是Git，二是rsync。

有一些工作需要提前做好，比如说在远程服务器上部署SSH访问。

按照文档，把所有该填的东西都填好，没有什么问题。

可能还有一个小坑吧，起码在目前（2016-06-10）没有修复的bug，就是rsync的配置一定要填全，最好不要遗漏，否则提示同步成功却实际上屁事没干。

## 常见问题

### 报错

我遇见过的错误除却端口被占用这样很明显的错误外，还有一种比较常见，不过不是很好定位的问题。

「JS-YAML: can not read a block mapping entry;」

这种错误有两种可能：

1. _config.yml有问题，仔细检查一下，可能是一项配置了两次或拼写问题。
2. 新建的page或post有问题，查看是否符合格式要求，可以和默认的对比一下，一般都能发现问题所在。

### 分类和标签

删掉分类和标签的话，会出现分类和标签统计错误的情况。

很好解决，直接重新生成即可。

``` bash
$ hexo clean
$ hexo generate
```

### 更多

详细的配置和说明需要查看：[Hexo](https://hexo.io/zh-cn/docs/)和[Next](http://theme-next.iissnan.com/).

---