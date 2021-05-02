---
layout:       article
title:        从零开始学 docker
key:          2018-09-27
tags:         vps
categories:   system
created_date: 2018-09-27 16:03:03 +08:00:00
date:         2019-08-27 01:13:28
---

搭建服务器，使用 vps，为了方便维护和快速重新搭建，使用 docker 最适合了。

<!--more-->

## 准备工作

关于 docker 的概念，特性，优势等等在此不再叙述。自行百度有很多的。

其实有关 docker 技术的教程也可搜索到很多，作为初学者，刚入坑的为在使用时记不住众多的命令和操作步骤，写篇文章记录一下吧，方便自己日后查询。

参考：https://blog.csdn.net/S_gy_Zetrov/article/details/78161154

### 注册Docker官方账号

<https://cloud.docker.com>

## 基本操作

vps 安装 docker，可看[这里](../notes/vps-init.html#安装-docker)。或者按照官方的指导来操作：<https://docs.docker.com/install/>

```sh
# 查看版本
$ docker version
$ docker -v
# hello world
$ docker run hello-world
# 搜索
$ docker search php
# 查看本地镜像
$ docker images
# 查看当前运行的容器
$ docker ps
# 查看镜像的详细信息
$ docker inspect {IMAGE_ID}
# 删除镜像
$ docker rm {CONTAINER_ID}
$ docker rmi {IMAGE_ID}
# 复制镜像里的文件
$ docker cp {CONTAINER_ID}:/etc/loolwsd/loolwsd.xml loolwsd.xml
# 查看 docker 内的日志
$ docker logs {CONTAINER_ID}
# 进入 docker
$ docker exec -it {CONTAINER_ID} /bin/bash
```

### docker hub 镜像

参考： <https://www.cnblogs.com/wushuaishuai/p/9984228.html>

Docker 镜像 <http://mirrors.ustc.edu.cn/help/dockerhub.html>

Docker 镜像 <https://www.docker-cn.com/registry-mirror>

```sh
nano /etc/docker/daemon.json
# 粘贴以下内容
{
  "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn/"]
}
```

## 推荐阅读

[Docker教程：Docker入门实践（精讲版）](http://c.biancheng.net/docker/)