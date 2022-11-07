---
title: Setup Ansible Control Node and Configure Ansible
author: frank
date: 2022-11-07 22:51:00 +0800
categories: [Devops,Ansible]
tags: [ansible]     # TAG names should always be lowercase
render_with_liquid: false
---
In this article, I will demonstrate how you can install and configure an Ansible control node on CentOS 7.

A control node is a Linux server that has Ansible installed on it and is used for managing remote hosts or nodes. These remote systems are known as Managed Hosts or Managed nodes.

>Reference link:
[ansible installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## 1.ansible installation
### 1.1 install ansible from epel repository

check available ansible version 

```shell
yum list | grep ansible
```
For the available ansible version is lower than the version we desired,I install epel repo,then we can get lastest stable ansible version.
```shell
yum -y install epel-release
```
check available ansible version again

```shell
yum list | grep ansible
```
install ansible
```shell
yum -y install ansible
```

### 1.2 install ansible using pip
Make sure python is installed in your server.
Use **pip** in your selected Python environment to install the Ansible package of your choice for the current user:

```shell
python3 -m pip install --user ansible
```
### 1.3 verify installation result
```shell
ansible --version
ansible localhost -m ping
```
## 2. ansible.cfg default settings
```shell
#inventory  = /etc/ansible/hosts      #主机列表配置文件
#library    = /usr/share/my_modules   #库文件存放目录
#remote_tmp = $HOME/.ansible/tmp      #临时py命令文件存放在远程主机目录
#local_tmp  = $HOME/.ansible/tmp      #本机的临时命令执行目录
#forks      = 5                       #默认并发数
#sudo_user  = root                    #默认sudo用户
#ask_sudo_pass=True                   #每次执行ansible命令是否询问ssh密码
#ask_pass   = True
#remote_port= 22
#host_key_checking = False            #检查对应服务器的host_key，建议取消注释
#log_path   =/var/log/ansible.log     #日志文件
```

https://docs.ansible.com/ansible/2.4/intro_configuration.html
https://developer.aliyun.com/ask/211236?spm=a2c6h.14164896.0.0.5d632b0fe2VElM