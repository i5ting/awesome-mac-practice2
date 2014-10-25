# centOS

```
yum -y install gcc
yum -y install gcc-c++ 
yum install make
```

-- 或者

	yum groupinstall "Development Tools"
 
-- 或者

	yum install gcc gcc-c++ kernel-devel


or 

CentOS的软件源未包含有最新的nodejs, 需要手动编译安装。
首先安装依赖的库与工具

```
yum install libtool automake autoconf gcc-c++ openssl-devel  
```

然后下载nodejs的源码包tar, 解压缩后直接三板斧编译安装

```
./configure --prefix=/usr  
make  
make install  
```
 	
最后用 node -v和 npm -v 查看安装的版本
到这里其实还没完， 还需要安装 node-gyp 之类的包 

```
	npm install -g node-gyp  
```

npm的另一种安装方式是

```
wget http://npmjs.org/install.sh  
chmod +x ./install.sh  
./install.sh 
```

## 判断centos是否是64位系统

1.uname -a 查看OS详细信息

2.file /bin/ls 

显示系统程序信息，就能看出多少位

3.获得机器字长

getconf LONG_BIT

4.查看OS版本

	cat /proc/version 

5.查看os详细参数信息

	getconf -a


PC server X86 系列

- I386--I686  都是32位
- x86_64 是 64位





## Failed to load c++ bson extension, using pure JS version

这个主要是通过 npm install mongoose 时，mongoose 并没有编译 bson, 引起的，通过 npm install bson 就会编译它，并个性 mongoose 中对应的引用代码即可。
按上面给出方式修改后就可以了


https://cnodejs.org/topic/53020b75e369e0840e7b060d

## 设置时间

```
date -s 10/18/14
date -s 17:02:50 
```


## nohup not work


    "start": "./node_modules/.bin/supervisor ./bin/www &"
		
		
##  Cannot retrieve repository metadata (repomd.xml) 

```
➜  openssl  yum install -y build-essential libssl-dev libreadline5 libreadline5-dev zlib1g zlib1g-dev


Error: Cannot retrieve repository metadata (repomd.xml) for repository: epel. Please verify its path and try again
```

https://lug.ustc.edu.cn/wiki/mirrors/help/epel

## 安装

	yum -y install mysql-server
	yum intall httpd
	yum -y install php   
	yum -y install php-mysql
	
开机启动
 
	chkconfig mysqld on 
	chkconfig httpd on 
	chkconfig --list mysqld  
	chkconfig --list httpd
	
	  