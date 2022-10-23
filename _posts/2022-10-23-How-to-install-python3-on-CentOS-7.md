---
title: How to install python3 on CentOS 7
author: frank
date: 2022-10-23 15:50:00 +0800
categories: [Tools,Python]
tags: [installation,linux practices]     
render_with_liquid: false
---

Installing Python on your local computer is the first step to becoming a proper Python programmer. While you can use online tools to run Python, most serious developers still rely on a local installation to work on individual and team projects. This tutorial will show the current best practice approach for checking what version of Python, if any, is already on your machine and installing or updating Python for Linux.

## 1.Installing Requirements
Before you begin with this guide, there are a few steps that need to be completed first.

You will need a CentOS 7 server installed. If you haven't done this yet, you can install CentOS7 according my installation [article](https://douer423.github.io/posts/How-to-create-CentOS7-in-VMWare-WorkStation/).

Then, you need to install all required packages for python3 installation on our system using the following command.
```shell
yum -y install libffi-devel zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel gcc make
```
## 2.Install python3
Now, install the latest [stable version](https://www.python.org/downloads/source/) of python3 on your system using the following command. This command will automatically download all required files and install on your system.
```shell
cd /usr/local/src
wget https://www.python.org/ftp/python/3.9.15/Python-3.9.15.tgz
tar -xzvf Python-3.9.15.tgz
cd Python-3.9.15
./configure --prefix=/usr/local/python3
make && make install
```
Using following command you can check the current python3 is used.

```shell
/usr/local/python3/bin/python3 --version
```

## 3.Make soft link to python3

Using following command you can make link for python3.
```shell
ln -s /usr/local/python3/bin/python3 /usr/bin/python3
ln -s /usr/local/python3/bin/pip3 /usr/bin/pip3
```



