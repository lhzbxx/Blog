---
title: build-ubuntu-server-log
tags:
  - null
date: 2016-11-28 23:34:07
updated: 2016-11-28 23:34:07
categories:
---

（未完成）

「」

sudo vi /etc/systemd/logind.conf
#HandleLidSwitch=suspend => HandleLidSwitch=ignore
sudo service systemd-logind restart

sudo rm /etc/apt/sources.list
sudo vi /etc/apt/sources.list
deb http://mirrors.163.com/ubuntu/ xenial main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ xenial-security main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ xenial-updates main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ xenial-proposed main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ xenial-backports main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ xenial main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ xenial-security main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ xenial-updates main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ xenial-proposed main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ xenial-backports main restricted universe multiverse

sudo apt-get update && apt-get upgrade

sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual
curl -sSL https://get.daocloud.io/docker | sh
curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://f72c0be0.m.daocloud.io
sudo service docker start
sudo usermod -aG docker lhzbxx

mkdir .ssh
cd .ssh
vi authorized_keys
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDZ2wA3BaoBbqoRVgo6S3QXcUGSiZ43xtFHlRiXPgdddQv8/XFvparDUKl0KVmyeERQVgEmYhRmek+r5rfbNpvV7S0oU/B5q+9VD5enqoZYeXUTss4bNqOet4As8xtISEIzsKCIOzRvz/HpvyHSsAar6g0P0Z1VD6bq9RaNiIiokQRmui+ba/AnhkIQAielpfcbGW2oT46JjpIQqi2LUbXtzvkG8jgL6g9ZHuxgjHnmhBZAJMB5G7NanxkV5sfZXu/TiFZ13xNXSdBLLPOadlGn1yQCQYYP75z3dnq0Ph++1XNwOXB8CH4dYNW1jr0tpE26UHIBGMkm6UavwjAnHTzd lhzbxx@lhzbxx-MBP.local

docker pull gitlab/gitlab-ce

sudo curl -L "https://github.com/docker/compose/releases/download/1.8.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

sudo apt-get install samba
sudo vi /etc/samba/smb.conf
[share]
   path = /mnt/share
   browseable = yes
   writable = yes
   public = yes

<!-- more -->

---
