---
layout: post
title: 使用 Jekyll 搭建自己的 Github Pages
key: 2017-10-30
date: 2017-10-30 16:46:38
categories: notes
tags: jekyll 
modify_date: 2017-11-25 20:21:19
---

记录一下本人第一次搭建git pages的过程。谨以此文记录自己的操作过程。

<!--more-->


想要操作高级玩法，一定要仔细阅读[官方文档](http://jekyll.com.cn/docs/home/)。了解`liquid`语法，`yaml`语法，`jekyll`架构。以及相关的HTML，css，javascript基础。

因为需要使用ruby语言，本人之前从未接触过它，对此有很大的抵触。网上找了很多教程都是基于MAC或者Linux系统的，本人使用win10，很怕弄不会又没有相关资料，于是还特意折腾了虚拟机安装了centos。按照教程一步步来，结果实际情况还是和各种教程的描述不一致。搞得本人头很大。后来耐心的查阅了很多资料，对github pages、jekyll及其相关工具有了更深的认识，于是照猫画虎的搭建成功了。接下来打算慢慢的修改成自己想要的样子。


## jekyll 相关链接

[Liquid 模板语言 wiki](https://github.com/Shopify/liquid/wiki)

[Xianda选的模板](https://github.com/kitian616/jekyll-TeXt-theme)

[使用Jekyll搭建自己的博客-全教程-简书](http://www.jianshu.com/p/c04475ba80e4)

[搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)

[jekyll-now](https://github.com/barryclark/jekyll-now)

[使用 GitHub, Jekyll 打造自己的免费独立博客](http://blog.csdn.net/on_1y/article/details/19259435)

[Jekyll搭建写作环境问题集锦](http://www.jianshu.com/p/12e7e1f8007e)

[Windows安装Jekll](https://segmentfault.com/a/1190000010195733)


## windows上使用jekyll

[windows 使用 ruby、jekyll 搭建 github pages](http://blog.csdn.net/u013009839/article/details/43742901)

> makefile的使用

### 安装Ruby

在[官网](https://rubyinstaller.org)下载ruby，windows系统推荐使用[RubyInstaller](https://rubyinstaller.org/downloads/)。本人下载了`.exe`安装，会自动添加路径到path变量中。

安装完毕可以输入`ruby -v`验证。

### 安装RubyGems

1. 官网下载[RubyGems](https://rubygems.org/pages/download)的zip包
2. 解压zip文件并在命令行（cmd/git bash均可）cd到该目录
3. 输入`ruby setup.rb`（管理员权限）

安装完毕可以输入`gem -v`验证。

其他操作：

~~~shell
查看通过gem已安装插件：gem list
查看gem的源：gem sources list
可以添加源：gem sources -a http://ruby.taobao.org/
删除源：gem sources --remove https://rubygems.org/
~~~

### 安装Jekyll

执行`gem install jekyll`即可自动安装jekyll的所以依赖包。也许或弹出防火墙提示，允许即可。依赖包数量比较多安装过程会慢，耐心等待安装完毕即可。

安装完毕输入`jekyll -v`验证。

### Jekyll 操作教程


```shell
$ jekyll build
# => 当前文件夹中的内容将会生成到 ./_site 文件夹中。

$ jekyll build --destination <destination>
# => 当前文件夹中的内容将会生成到目标文件夹<destination>中。

$ jekyll build --source <source> --destination <destination>
# => 指定源文件夹<source>中的内容将会生成到目标文件夹<destination>中。

$ jekyll build --watch

# => 当前文件夹中的内容将会生成到 ./_site 文件夹中，
# 查看改变，并且自动再生成。
```

### 搭建环境问题处理

搭建后执行jekyll命令如果出现报错，多为配置环境的问题。通常根据报错信息安装对应的依赖包即可，如：

````sh
gem install tzinfo-data
````

或者在根目录下的`Gemfile`文件里输入：

```ruby
gem 'tzinfo-data'
```

###　.svg 文件转 .png 和 .ico 文件工具

首先需要nodejs环境，官网下载即可。然后需要使用npm下载，npm服务器下载比较慢，可以选择淘宝镜像，具体操作见：<https://npm.taobao.org/>

```bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

可参考：[网站图标生成](https://github.com/kitian616/jekyll-TeXt-theme#%E7%BD%91%E7%AB%99%E5%9B%BE%E6%A0%87)  。





## 拓展阅读

### 基于php的markdown博客搭建工具-gitblog

[gitblog官网](http://www.gitblog.cn/)， [github地址](https://github.com/jockchou/gitblog)

### 基于NodeJs的markdown博客搭建工具-hexo

[hexo官网](https://hexo.io/)，[github地址](https://github.com/hexojs/hexo)

### 基于NodeJs的jekyll翻版工具-darko

[github地址](https://github.com/dotnil/darko)

> <https://github.com/thx/thx.github.io/blob/master/README.md>













## CentOS上使用jekyll（未完待续）

本人安装的是`CentOS-7-x86_64-DVD-1708.iso`镜像，提前安装好 VMWare Workstation。安装时软件选择->基本环境选的`GNOME桌面`，语言`中文简体`。然后点击`开始安装`，安装时设置好root账户密码。等待安装时过程中可以设置一个非root账户，结束后需要重启。然后进入 centos，右键打开终端，开始安装 jekyll 。

> 如果不是root账户，安装过程中也许会提示权限不足，请在执行的命令前加上`sudo `，本人以下操作均是在root账户下操作。

### 参考：

[Ruby on Rails 入门之：(1) Ruby, Rails, gem, bundler相关软件的安装](http://blog.csdn.net/watkinsong/article/details/8012742)

### 安装 rvm

```shell
curl -sSL https://get.rvm.io | bash -s stable
```

等待安装完毕，载入RVM环境（或者重新打开终端会自动载入）：

```shell
source ~/.rvm/scripts/rvm
```

修改 RVM 下载 Ruby 的源，到 Ruby China 的镜像:

```shell
echo "ruby_url=https://cache.ruby-china.org/pub/ruby" > ~/.rvm/user/db
```

### 用 RVM 安装 Ruby 环境

检查一下rvm是否安装正确

```shell
rvm -v
rvm 1.29.3 (latest) by Michal Papis, Piotr Kuczynski, Wayne E. Seguin [https://rvm.io]
```

```shell
rvm requirements	//检查先决条件并安装
rvm list known		//写出已知的ruby版本
```

根据显示的版本信息，我选择了个当前最新版本：（`ruby-head`为dev版本）

```shell
rvm install ruby-2.4.1
```
等待安装结束，

```shell
vim Gemfile
```

按`I`键，进入编辑模式，输入：

```shell
gem 'execjs'
gem 'therubyracer'
```

然后按`ESC`，输入`:wq`保存退出，然后

 ```shell
bundle install
 ```

### 教程未完，本人放弃了centos，回归熟悉的windows

