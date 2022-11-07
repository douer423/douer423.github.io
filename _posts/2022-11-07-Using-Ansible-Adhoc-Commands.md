---
title: Using Ansible Ad-hoc Commands
author: frank
date: 2022-11-07 22:51:00 +0800
categories: [Devops,Ansible]
tags: [ansible]     # TAG names should always be lowercase
render_with_liquid: false
---

## 1.When to Use Ad-hoc commands
- In an ad-hoc command, Ansible modules are used to perform specific tasks on managed hosts. 
- An ad-hoc commands are perfect for running one task on a managed host.
  * initial host set up for instance
  * checking configuration on hosts
- Also ad-hoc commands are a perfect way to learn how easy Ansible really is. 
- The opposite of the ad-hoc commands is the playbook. The playbook is the way to implement more complex tasks, where dependency relations have to be managed. 

## 2.How to run ansible Ad-hoc commands 
In ad-hoc commands modules are used. An Ansible module is a python script that will be executed on a managed host. And there are over 3000 modules available in Ansible. Modules can be offered as such which was pre Ansible 2.10 or as a part of an Ansible collection, which you will find an Ansible two 2.10 and later. 

you use the Ansible commands to run the ad-hoc commands. 
```shell
ansible -i inventory localhost -m ansible.buildin.ping -a "0.0.0.0"
```
listing modules
```shell
Pre-2.10: ansible-doc -l
2.10 or later: ansible-doc -t module -l
```
With as many as 3,000 different modules having access to the appropriate documentation is very important. The module documentation is in ansible-doc Ansible-doc in fact contains documentation for more than just modules. It has documentation for about everything. 
```shell
ansible-doc modulename
```