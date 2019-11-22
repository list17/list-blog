---
title: Python3.7 手动安装记录
date: 2019-11-9 18:38:45
mp3: http://domain.com/awesome.mp3
cover: ../img/image1.jpg
---
第一次手动编译python安装记录。
## Step 1
在安装python之前首先安装一些必要的前提
```bash
sudo apt-get install build-essential checkinstall
sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev \
    libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev
```
## Step 2
下载python源码，这里样例为python3.7的源码，需要其他版本可以去python官网下载。
```bash
sudo wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz

sudo tar -xzf Python-3.7.4.tgz
```
## Step 3 - Compile 
```bash
cd Python-3.7.4
export LD_RUN_PATH=/usr/local/bin/python3.7/lib
sudo ./configure --prefix="/usr/local/bin/python3.7" --enable-shared --enable-optimizations
sudo make altinstall
```
如果参数中没有
```bash
--enable-shared
```
这一参数，不再执行上述的步骤。执行下面的步骤，并且step4及之后都不需要在执行。
```bash
cd Python-3.7.4
sudo ./configure --enable-optimizations
sudo make altinstall
```

## Step 4 
由于自己用的zsh，所以直接修改了~/.zshrc这一文件  
在最后加上
```bash
export LD_LIBRARY_PATH="/usr/local/bin/python3.7/lib"
```
之后在修改软连接即可
```bash
sudo ln -sf /usr/local/bin/python3.7/bin/python3.7 /usr/bin/python
```

## Q&A 
1. 为什么要加
```bash
--enable-shared
```
这一参数。
在安装一个vim插件时需要执行一个install.py报出如下错误
```python
error while loading shared libraries
```

2. 有没有简单的安装方法
使用apt安装，参照
https://linuxize.com/post/how-to-install-python-3-7-on-ubuntu-18-04/


好像还有什么问题，想起来再写
