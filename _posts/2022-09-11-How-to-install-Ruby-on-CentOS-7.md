---
title: How to intall Ruby on CentOS 7
author: frank
date: 2022-09-11 11:51:00 +0800
categories: [Operating System,CentOS]
tags: [installation,linux practices]     # TAG names should always be lowercase
render_with_liquid: false
---

Ruby is a dynamic, object-oriented programming language focused on simplicity and productivity. `RVM` (Ruby Version Manager) is a tool for installing and managing multiple Ruby versions on single operating systems. This tutorial will help you to install RVM on your system. After that install the latest Ruby on CentOS and RedHat systems using RVM.

## 1.Installing Requirements

Before you begin with this guide, there are a few steps that need to be completed first.

You will need a CentOS 7 server installed. If you haven't done this yet, you can install CentOS7 according my installation [article](https://douer423.github.io/posts/How-to-create-CentOS7-in-VMWare-WorkStation/).

Then, you need to install all required packages for RVM installation on our system using the following command.

```shell
yum install gcc g++ make -y
```
## 2.Install RVM
Now, install the latest stable version of RVM on your system using the following command. This command will automatically download all required files and install on your system.
```shell
cd /usr/local/src/
curl -sSL https://github.com/rvm/rvm/tarball/stable -o rvm-stable.tar.gz
tar -xzvf rvm-stable.tar.gz
mv rvm-rvm-6bfc921/ rvm
rm -f rvm-stable.tar.gz 
cd rvm/
./install --auto-dotfiles
source /usr/local/rvm/scripts/rvm
```
Using following command you can check the current rvm is used.

```shell
rvm -v
```
## 3.Verify Dependencies
Use the following command to verify all dependencies are properly installed. This will install any missing dependencies on your system.
```shell 
rvm requirements
```
## 4.Install Ruby on CentOS
Now, your system is ready for the Ruby installation. You can find the available Ruby version for installation using below command or find the newest version from [Ruby](https://www.ruby-lang.org/en/downloads/).
```shell
rvm list known
```
Then install the required Ruby version on your system. Here, I am installing Ruby 3.1.2 on my CentOS system. You can simply replace the version to below command of your choice and install.
```shell
rvm install 3.1.2
```
## 5.Setup Default Ruby Version
First of all, check the currently installed ruby versions on your system. So that we can find which version is using currently by the system and which is set to default.
```shell
rvm list 
```
After that use rvm command to set up the default ruby version to be used by applications.
```shell
rvm use 3.1.2 --default
```

## 6.Verify Active Ruby Version

Using following command you can check the current ruby and rubygems version is used.
```shell
ruby -v
```
```shell
gem -v
```
