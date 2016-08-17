---
title: 记一次在AWS-EC2上部署PPTP-VPN的经历
tags:
  - 备忘
date: 2016-08-12 17:45:05
updated: 2016-08-12 17:45:05
categories: 玩具实验室
---

之前和我一直聊得热乎的妹子回国了，已经习惯于肉身翻墙的她自然到处寻找靠谱的VPN。

在公司里有一个阿里云在香港的Windows主机弄的PPTP-VPN，自己也想买一台，结果发现，太TM的贵了啊——有没有热心的水友告诉我，啥时候阿里云变得这么吃人了，看了一下最低配+按流量收费打了折竟然都要1700+RMB。天了噜，还有没有天理了。国外这样的配置也就$4.99*12吧。

然后妹子用她的信用卡帮我免费申请了一个AWS的账号，可以用一年免费的EC2.

就可以愉快地搭建VPN啦！

<!-- more -->

话说翻墙的技术倒是挺多的，我自己用的GoAgent，当然最靠谱的还是VPN了，稳定、流量大、不用为IP发愁。

## AWS设置

首先是进入AWS的控制台咯。

主要有两点：

1. 选择数据中心，我当时就近选了首尔。
2. 选择镜像、生成pem文件。
3. 绑定弹性IP。
4. 创建安全组，开放TCP的1723端口。

值得一提的是，EC2主机的终止就相当于销毁了。

## 安装PPTP

sudo apt-get install pptpd

sudo vi /etc/pptpd.conf

localip 192.168.0.1
remoteip 192.168.0.234-238,192.168.0.245

sudo vi /etc/ppp/pptpd-options

ms-dns 8.8.4.4
ms-dns 8.8.8.8

/etc/ppp/chap-secrets



---