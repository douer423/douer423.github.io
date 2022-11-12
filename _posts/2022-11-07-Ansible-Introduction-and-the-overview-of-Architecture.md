---
title: Ansible Introduction and the Overview of Architecture
author: frank
date: 2022-11-07 22:51:00 +0800
categories: [Devops,Ansible]
tags: [ansible]     # TAG names should always be lowercase
render_with_liquid: false
---


## 1. What is Ansible?
Ansible is a simple, open-source, IT automation engine that automates cloud provisioning, intra-service orchestration, configuration management, application deployment, and many other IT needs in day to day life in Software engineer.

It is designed for multi-tier deployments. Thereby it aligning with the cloud’s basic structure precisely. Ansible models your IT infrastructure by describing how all of your systems inter-relate, rather than just managing one system at a time.

Automation simplifies complex tasks, not just making developers’ jobs more manageable but allowing them to focus attention on other tasks that add value to an organization. In other words, it frees up time and increases efficiency.

## 2. Why do we like Ansible?
Ansible helps in modeling the cloud IT infrastructure with a description of inter-relation between all systems. Ansible does not implement any agents or additional custom security infrastructure. Furthermore, Ansible also offers flexibility for deployment and uses the simple YAML language in its Playbooks. Therefore, the user could easily describe automation jobs in simple English.

## 3. Advantages of Ansible
* Free: Ansible is an open-source tool.
* Very simple to set up and use: No special coding skills are necessary to use Ansible.
* Powerful: Ansible lets you model even highly complex IT workflows.
* Flexible: You can orchestrate the entire application environment no matter where it’s deployed. You can also customize it based on your needs.
* Agentless: You don’t need to install any other software or firewall ports on the client systems you want to automate. You also don’t have to set up a separate management structure.
* Efficient: Because you don’t need to install any extra software, there’s more room for application resources on your server.

## 4. ansible architecture diagram and components

Looking at the ansible architecture shown in the diagram below and discussing one by one of its components.
![ansible Architecture](https://www.ecanarys.com/Portals/0/xBlog/uploads/2020/5/21/8.jpg)

Ansible compoments：

1. ansible core: a minimalist language and runtime called ansible-core (called ansible-base in version 2.10).
2. Core Modules：Ansible modules, considered to be the main workhorse of Ansible. You use modules to perform various tasks such as installing a package, restarting a service, or copying a configuration file. Ansible modules cater to a wide range of system administration tasks. This list has the categories of the kinds of modules that you can use. There are over 3000 modules. So you may be thinking, who is looking after all of these modules? That’s where collections in the more recent versions of Ansible are doing.
3. Extending Modules：The modules are the scripts ( that are written in Python) that come with packages with Ansible and Perform some action on the managed host. Ansible has an extensive list of modules covering many areas such as networking, cloud computing, server config, containerized, and virtualization. In addition, there are many modules to support the automation requirements you have. If no modules exist, you can create a custom module with the extensive framework of Ansible. So each task is a one-to-one correlation with the module. So, for example, a template task will use the template module.
4. Plugins: Plugins are special types of modules here. These plugins are executed on the nodes before a module gets executed. Plugins are a piece of code which expends Ansible's core functionality. There are plugins that are useful, and you can also write your own. While modules run in separate processes on the target machine (usually that means on a remote node), plugins run on the control node.
5. Playbooks：Playbooks here actually define your workflow because whatever tasks that you write in a playbook, it gets executed in the same order that you have written them. They are written in YAML format, which describes the tasks and executes through the Ansible. Also, you can launch the tasks synchronously and asynchronously with playbooks.An Ansible Playbook can have multiple plays that can exist within an Ansible playbook that can execute on different managed assets. So an Ansible Play is all about **what am I automating**. And then, it connects to the hosts to perform the actions. Each playbook comprises one or more **plays** in a list. The goal of a play is to map a group of hosts to some well-defined roles, represented by things Ansible calls tasks. At a basic level, a task is nothing more than a call to an Ansible module. By composing a playbook of multiple ‘plays’, it is possible to orchestrate multi-machine deployments, running certain steps on all machines in the web servers group. For example, certain steps on the database server group, then more commands back on the web servers group, etc.
6. Connection Plugins：Connection plugins allow Ansible to connect to the target hosts so it can execute tasks on them. Ansible ships with many connection plugins, but only one can be used per host at a time.By default, Ansible ships with several connection plugins. The most commonly used are the paramiko SSH, native ssh (just called ssh), and local connection types. 
7. Inventory：The Ansible inventory is all about telling Ansible about your servers. Ansible can manage only the servers it explicitly knows about. Ansible comes with one default server of the local host, which is the control host. You provide Ansible with information about servers by specifying them in an inventory. We usually create a directory called “inventory” to hold this information. For example, a very simple inventory file might contain a list of hostnames. The Ansible Inventory is the system that a playbook runs against. It is a list of systems in your infrastructure that the automaton is executed against. 
   
    Inventory Highlights:
    These are a collection of hosts that commonly have hosts but can comprise other components such as network devices, storage arrays, and other physical and virtual appliances. It also has useful information that can be used alongside our target using the execution. The Inventory can be simple as a text file or more dynamically where the Inventory is an executable where the data is sourced dynamically. This way, we can store data externally and be used during runtime. So we can have a dynamic inventory via Amazon Web Service or create our dynamic.

## 5. How Ansible Works?
![ansible workflow](https://www.devopsschool.com/blog/wp-content/uploads/2019/07/Understanding-Ansible-playbook-using-diagram.jpg)

Ansible works by connecting to your nodes and pushing out small programs, called **Ansible modules** to them. Ansible then executes these modules (over SSH by default), and removes them when finished. Your library of modules can reside on any machine, and there are no servers, daemons, or databases required.

The management node in the above picture is the controlling node (managing node) which controls the entire execution of the playbook. It is the node from which you are running the installation. The inventory file provides the list of hosts where the Ansible modules needs to be run and the management node does a SSH connection and executes the small modules on the hosts machine and installs the product/software.

## 6. Useful Links
[ansible-terminology-ansible-vs-ansible-core-packages](https://www.ansiblepilot.com/articles/ansible-terminology-ansible-vs-ansible-core-packages/)  
[understanding-ansible-playbook-using-diagram](https://www.devopsschool.com/blog/understanding-ansible-playbook-using-diagram/)
