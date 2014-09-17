awesome-mac-practice
====================

## 开启root用户

http://support.apple.com/kb/HT1528?viewlocale=zh_CN&locale=zh_CN

OS X Lion (10.7) 和更高版本

1. 从 Apple 菜单中选取系统偏好设置...。
1. 从显示菜单中选取用户与群组。
1. 点按锁图标并使用管理员帐户进行鉴定。
1. 点按“登录选项...”。
1. 点按右下方的“编辑...”或“加入...”按钮。
1. 点按“打开目录实用工具...”按钮。
1. 点按“目录实用工具”窗口中的锁图标。
1. 输入管理员帐户名称和密码，然后点按“好”。
1. 从编辑菜单中选取启用 Root 用户。
1. 在“密码”和“验证”字段中输入您想要使用的 root 密码，然后点按“好”。

## 清理docker

留5个左右，不要放太多，其他都移除

## 隐藏docker

奇数次隐藏

	option + command + d
	
偶数次即显示

## 启用fn功能键

![](img/fn.png)

## Trackpad

开启全部手势

## 触发角 

system preferences -> mission controll -> hot corners

![](img/hotcorners.png)

- 左上：mission controll
- 左下：application windows
- 右上：desktop
- 右下：start screen saver

## 安装腾讯电脑管家

http://pc.qq.com/mac.html

[QQMacMgr_1.3.1 download](http://dlied6.qq.com/invc/xfspeed/mac/verupdate/QQMacMgr_1.3.1.dmg)

## 安装cinch

全屏窗口


## 安装quicksilver

Quicksilver is a fast and free Mac OS X productivity application that gives you the power to control your Mac quickly and elegantly. Quicksilver learns your habits, making your everyday chores simple and efficient.

http://qsapp.com/download.php

[10.9 quicksilver download](http://qs0.qsapp.com/plugins/download.php)

另一个选择是使用QQ内置的swiftly（按2此commmand键）

## 安装输入法

搜狗

## 安装VPN

云梯，一键安装

## 安装brew

The missing package manager for OS X. 

http://brew.sh


安装

	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

测试

	brew install wget
	brew install openssl

## 安装commandline和xcode

## 安装git


## 配置ssh


生产ssh秘钥

```
➜  docker  ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/sang/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/sang/.ssh/id_rsa.
Your public key has been saved in /Users/sang/.ssh/id_rsa.pub.
The key fingerprint is:
3c:b6:58:24:23:68:bf:33:f2:70:e2:71:e6:77:1f:c4 sang@sangalfreds-MacBook-Pro.local
The key's randomart image is:
+--[ RSA 2048]----+
|                 |
|   .             |
|  o . o .        |
| . . . = .       |
|    .   S E      |
|     . + +       |
|  = B . . .      |
| . @ o. .  .     |
|  . o. . ..      |
+-----------------+
```

查看

``` 
➜  docker  cat ~/.ssh/id_rsa.pub 
ssh-rsa ANzaC1yc2EAAAADAQABAAABAQC9A3e1i1vZj2SHX4KZAgQffrEj7N0/ZUuB6ZKGdWe8eVV08cv3rZlDHhEKtOI+JfFiR5TepvSax59LrxVDKniq7swSITNnXFL3KczFew9HUoHzZOZGg36bsFAzl372DkrHQZTExQaOFidQacWVWjhQwincRwJRkLMe596JkO8ZCqzUJgp0ax3mDNX1W3MIG1mrYFMQAQp6BpGlzvIy3PHqJDu/ibYzLCnbwVq2uL2q+gw6tqGyl9nibpfxa5qUSl4ZpZTfOCzqw9K+I3GqMO63XgTv6fkV9CsmkGWkv/jsDqbtyLt8JzychFPF3M4fD1JE/FWAb+xS+pWTgrrJx9hN sang@sangalfreds-MacBook-Pro.local
```

更新到github上

![](img/git_ssh_key.png)

## 安装oh-zsh


## 安装vim

https://github.com/carlhuda/janus

安装命令

	curl -Lo- https://bit.ly/janus-bootstrap | bash

## language

### node

### ruby

#### 安装rvm
#### 安装ruby2.1


### python

### go

打开http://golang.org/doc/install下载pkg的安装包

`go1.3.1.darwin-amd64-osx10.8.pkg`


安装后需要做如下操作

打开`vi ~/.zshrc`，增加

	export PATH=/usr/local/go/bin:$PATH
	
生效

	source ~/.zshrc

测试

	> go version
	> go version go1.3.1 darwin/amd64
	
	