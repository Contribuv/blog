---
title: 一个python压力测试脚本，请勿拿去攻击
tags:
  - 压力测试脚本
id: '36'
categories:
  - - 主机
date: 2019-03-28 07:41:37
---

建站做好安防是我们必须要掌握的，等着别人攻击，还不如自己通过压力测试，提高自己服务器的防御

此脚本在作者Lee0n123脚本上，增加了对宝塔环境的支持，增加了普通代理IP的支持，修复了Get发送错误

注意使用此脚本务必掌握搭建python3的基本操作，如不会，请严格按照我的教程来

注意：请勿使用此脚本在没有经过站长允许的情况下严禁用于攻击，严禁，严禁，严禁

脚本地址：

```
wget https://www.xxhat.xyz/python/cc.py
```

测试脚本用的代理：（感谢左岸博客提供，此IP无量，仅用于查看服务器日志用）

```
wget https://www.xxhat.xyz/python/socks.txt
```

务必将此代理放入与cc.py同一目录，如没代理ip，可以在脚本里自动获取，或自行购买放入socks.txt文件中

* * *

首先搭建宝塔环境：（如已搭建，请跳过）

```
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && bash install.sh
```

搭建完成后，请严格按照我的要求安装python3

为了让大家测压顺利，我提供一个安装包

```
wget https://www.xxhat.xyz/python/Python-3.6.7.tgz
```

下载到root目录，然后依次执行：

```
tar zxvf Python-3.6.7.tgz 
cd Python-3.6.7 
./configure  
make && make
install
```

这样python3便安装好了，且不影响宝塔以及网站的环境

依次执行，以设置python3位默认python (注意，这一步很关键，别搞错了)

```
rm -f /usr/bin/python
ln -s /usr/local/bin/python3 /usr/bin/python
rm /usr/bin/pip
ln -s /usr/local/bin/pip /usr/local/bin/pip
```

修改yum为python2，不然你的yum命令将会失效

```
vi /usr/bin/yum
```

把#/usr/bin/python 修改为#/usr/bin/python2

修改好后使用

```
yum update -y && python --version &&pip --version
```

如果yum没有出错而且是python3，且pip版本是python3里面的说明环境搭建成功

接下来就是运行我们的压力测试脚本了

在脚本目录执行

```
python3 cc.py
```

得到如图所示的操作界面：

![cc.jpg](https://www.xxhat.xyz/usr/uploads/2019/04/4195640485.jpg#mirages-width=394&mirages-height=192&mirages-cdn-type=3 "cc.jpg")

然后根据提示操作即可

注意，获取代理输入y,本地代理输入n，建议使用本地代理

因为在线代理，因centos镜像原因，你们不一定能成功

![cc3.jpg](https://www.xxhat.xyz/usr/uploads/2019/04/3133908847.jpg#mirages-width=357&mirages-height=336&mirages-cdn-type=3 "cc3.jpg")

* * *

最后，请大家仅用于自己的服务器测试，切勿使用此脚本进行攻击

如果采用付费的IP，威力很大，普通的博客根本吃不消

另外，本博客购买的CC防御，也没能防住，所以各位，不要用于攻击

* * *

关于更多服务器安防的相关资料以及教程，我会一直收集，分享！

* * *