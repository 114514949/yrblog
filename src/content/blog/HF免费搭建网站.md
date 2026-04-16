---
title: 使用HF免费搭建网站
categories: Course
tags:
  - 免费
  - 网站搭建
  - Hugging-Face
id: Hugging-Face-website-builder-for-free
date: 2026-4-16 5:20:00
cover: "https://wkphoto.bj.bcebos.com/d043ad4bd11373f0ea7a2cc6b40f4bfbfbed0425.jpg"
recommend: true # 是否推荐文章
---
### 超级无敌宇宙级免责声明
:::note{type="error"}
HF为“Hugging Face”，这是一个主打ai的国外网站，只是里面有一个功能是“Spaces”，所以就利用这个东西来免费搭建网站。由于免费版限制，每月流量虽无明文规定，不过ai说是每月最多**30G**，多了直接爆炸，所以请勿拿来做**下载站**（下载量比较少是可以的）！！！
:::
### 具体操作
首先需要一个HF账号，注册很简单，首先打开[HF官网](https://huggingface.co)，国内可能访问困难，有条件的可以开个加速器。
进入官网之后，找到注册（这真的是很简单的一步，随便找一找就找到了），然后输入你的电子邮箱，密码，名称，ID，等等，原版是英文，可以翻译一下。注册好账号以后，下滑找到“Spaces”，点击。进入新页面，点击“New Space”，名称自己随便填写，比如想搭建alist就输入alist，介绍那些不填也是可以的。
SDK可以根据自己需求选择，一般都是“Docker”，点一下之后什么都不用管，滑到最下面，点那个按钮。然后跳转页面到你的空间详情，点一下那个三个点，files，里面有一个“DockerFiles”，点一下这个名字，然后点一下那个笔的图标，里面输入框输入，比如你想搭建原版alist，就输入我给的这个代码：
`FROM xhofe/alist:latest
RUN apk add --no-cache socat
EXPOSE 7860
CMD ["/bin/sh", "-c", "/entrypoint.sh & socat TCP-LISTEN:7860,fork,reuseaddr TCP:127.0.0.1:5244"]`

如果你想安装OpenList，就输入这个：
`FROM openlistteam/openlist:v4.1.0
EXPOSE 5244`
然后最下面那个可以点击的按钮，点一下，HF就会提示构建中了，等个几分钟就好了，会给你一个公网地址，如果你没有找到就直接找一个可以打开新页面的东西，长按新页面打开就好了。你如果想安装其他的程序，就问问ai：HF中的docker，我想安装xxx，在dockerfiles里面该输入什么？
### 结尾
你做好上面那些工作，等构建完成就结束了，也有日志，可以复制发给ai。可能教程写的有点不详细，有不懂的可以在论坛私信问我，最近感冒了实在不好受，sorry！