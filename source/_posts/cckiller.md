---
title: 推荐一个秒级检查、自动拉黑的CC防御
tags:
  - CCKiller
id: '29'
categories:
  - - 记录
date: 2019-04-09 02:42:00
---

感谢作者提供

项目地址：

[https://github.com/jagerzhang/CCKiller](https://github.com/jagerzhang/CCKiller)

* * *

通过隔壁[左岸博客](https://www.xxhat.xyz/go/aHR0cHM6Ly93d3cuenJhaGguY29tLw==)实测，能防住[孙文博客](https://www.xxhat.xyz/go/LQtr3qj1/)付费IP所压力测试的拦截

安装地址：

```
curl -ko install.sh https://zhang.ge/wp-content/uploads/files/cckiller/install.sh?ver=1.0.7 && sh install.sh -i
```

* * *

如果你是宝塔，请先安装宝塔自带的防御，然后再安装此脚本，不然偶然性会boom.

* * *

食用方法：

安装后，会将 cckiller 注册成系统服务，这时你就可以使用 service 来控制 cckiller 了。

使用标准的 service 定义，支持 start stop restart status 四个参数。所以，你可以使用

service cckiller stop 来停止 cckiller，也可以使用 service cckiller status 来查看状态。

* * *

cckiller帮助命令：

成功安装后，系统还会多出一个 cckiller 的命令，这个命令现有功能如下：

cckiller -h 可以调出帮助信息：

```
 -h  --help: Show       this help screen
 -k  --kill: Block the offending ip making more than N connections
 -s  --show: Show The TOP "N" Connections of System Current
```

如果需要配置出错，可以使用初始配置

执行 ./install.sh -c 进行工具初始化，重新设定所有参数，过程和首次安装时一致

* * *

工具安装时会默认将系统所有 IP 都加入白名单，避免自己把自己给拉黑的尴尬。如果你还有其他要加白的 IP，可以将 IP 加入到 cckiller 安装目录下的 ignore.ip.list 文件中，每行一个。

* * *

卸载工具  
有心的朋友可能注意到了 install.sh 是可以带参数的。

install.sh -U 注意是大写的U，执行后即卸载

* * *