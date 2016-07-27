---
title: 「Git Book」读后感（未完成）
tags:
  - 备忘
date: 2016-07-06 18:19:01
updated: 2016-07-06 18:19:01
categories: 读书笔记

---

其实用了Git这么久，从当初比较痛苦的看各种Git Flow入门，再到后来自己亲自尝试发现并没有很复杂——在这个过程中，我对Git的本质的理解都源于自身的实践。但是我感觉这是不对的，还是有必要对Git的实现做一些了解，毕竟自己的大型TODO列表中有一个文档中心的设计，还是需要版本控制系统的支持的。再加上最近了解到Google的巨型版本控制系统，所以对VCS的实现产生了一些兴趣。

于是我就翻出来了这本「Git Book」来看了看。

当然，这本书并没有详细描述Git本身具体是怎么构建的，但介绍了很多重要的概念和原理。在此总结一下，为以后的工作做个铺垫。

<!-- more -->

## 一些概念

### Git模型

* 所有文件都是通过SHA1哈希计算后的40-digit对象名来索引的。
* 对象包括：类型，大小和内容。
* 对象的四种类型： blob，tree，commit，tag。
* blob：文件的全部内容。
* tree：一串条目，表达目录层次。
* commit：指向root of trees，并带有相关的描述信息。
* tag：标签对象包括一个对象名，对象类型，标签名和标签创建人。

### 目录

* Git目录，就是工程文件的根目录下的.git目录。
* Git目录包括HEAD，config，description，hooks，index，logs，objects，refs。
* logs存储各个refs的历史信息。
* objects存储本地仓库的所有对象。
* refs标识项目里每个分支指向了哪个提交。

### 工作目录

* 存储checkout编辑的文件。
* 分支切换时，工作目录文件会经常被替换和删除。
* 历史信息保存在Git目录中。

### Git索引

* 在工作目录和项目仓库之间的暂存区，即staging area。
* 被暂存（位于Git索引中），修改但未暂存，没有跟踪（untracked）。

### 工作流程

1. git add file1 file2 file3
2. git diff (--cached)
3. git status
4. git commit (-a)

### 分支与合并

* git branch experimental
* git branch 
* git checkout experimental
* (edit file)
* git commit -a
* git checkout master
* (edit file)
* git commit -a
* git merge experimental
* git diff
* git branch -d experimental
* git reset --hard HEAD

### 查看历史
* git log v2.5..       			# commits since (not reachable from) v2.5
* git log test..master 			# commits reachable from master but not test
* git log master..test 			# commits reachable from test but not master
* git log master...test			# commits reachable from either test or master, but not both
* git log --since="2 weeks ago"	# commits from the last 2 weeks
* git log Makefile     			# commits that modify Makefile
* git log fs/          			# commits that modify any file under fs/
* git log -S'foo()'    			# commits that add or remove any file data matching the string 'foo()'
* git log --no-merges  			# dont show merge commits


## 一些姿势

* Git会记录每次提交的全部内容，即snapshot。
* 提交本身不会记录修改信息，所有修改都是通过与父修改比较的得知。
* Git不会显式地记录文件的更名操作。
* Commit的注释技巧，标题+正文，中间空行。
* 如果当前分支和另一个分支没有内容上的差异，git会执行fast forward操作，不创建任何commit，只是将当前分支指向合并进来的分支。

## 一些操作

* git show & git ls-tree & git cat-file
* git status：查看索引内容。
* git init & git clone
* git add & git diff & git commit
* git branch & git checkout
* gitk
* git reset --hard HEAD
* git log

---