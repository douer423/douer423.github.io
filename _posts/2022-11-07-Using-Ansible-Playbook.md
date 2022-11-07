---
title: Using Ansible Playbook
author: frank
date: 2022-11-07 22:51:00 +0800
categories: [Devops,Ansible]
tags: [ansible]     # TAG names should always be lowercase
render_with_liquid: false
---

## 1.Playbook Structure
### 1.1 Understanding playbooks
- Ansible of playbook is used to run multiple tasks in order on multiple hosts. 
- It's an ideal way to define dependency relations between tasks
- Playbooks can also be used to implement conditional structures, where tasks are only executed if specific conditions are true. 

In the playbook, you will find different elements. To start with a playbook has one or multiple plays. Each play has a header. And in the header, you will find different properties including the hosts on which it has to run variables and maybe even more, and in a play one or more tasks are defined. 

### 1.2 Understanding playbook errors
- a play contains a series of tasks
- task dependencies in general are very important
- if a task fails to learn on a specific host, further execution of tasks in the failing play is aborted for that specific host. 
- use ignore_errors: True to continue exection anyway
  
## 2. Working with Variables
 Ansible itself is all about configuration as code. Let's face it. You define your playbooks, in your playbooks, in YAML file you define the configuration that you want to enroll on the managed assets in your environment. And if you are developing flexible code, you should separate site-specific information from the code which will be static.

 If in your playbook, you are too specific then it's not going to work out well. So you need to try to maintain a certain obstruction level in your playbook and to keep out very specific information. If you develop dynamic code where your static code is combined with variables that allows you to use your code on any site reduce some minor modifications in the variables themselves. 

To provide the site-specific information, variables I use. And apart from variables, Ansible provides facts.The only difference is that variables in general are defined by the system administrator and Ansible facts are discovered on the managed machines. So facts are system properties that are dynamically discovered, and you can use them as variables. 

If you want to use them somewhere else, the only thing you need to change is the variables. 

### 2.1 Where to Define Variables
- in the play header using **vars:**
- in the play header using an include with **vars_files:**
- using the **set_fact** module in a play
- on the command line,using the **-e key=value** option
- as inventory variables
- as host or host_group variables
- using **vars_prompt:** to request values from the user while running the playbook
- 
### 2.2 Using Ansible Facts
Ansible facts are system variables that contain information about managed system. And each playbook starts with an implicit task to gather facts unless you specifically disable that.

To use fact gathering from an ad-hoc command use a setup module.If you want to disable fact gathering, use gather_facts: no in the play header. And that might be interesting because gathering facts takes time. And if you don't want to wait the time to gather facts that you are not going to use anyway, just disable them.

Facts are stored in a multi-valued variables with the name **ansible_facts**,which is organized as a dictionary.

To address specific values in this dictionary,two formats can be used,the first one is perferred.
- ansible_facts['default_ipv4']['address']
- ansible_facts.default_ipv4.address
### 2.3 Using register
Register is a nice way to automatically define your variables based on command result. So the thing of Register is that you can use it to store the result of a task in a variable. It provides a very nice way to perform specific tasks only upon success or failure of another task. That means that it'll become really useful once we have talked about conditionals. 

## 3. Manage playbook using Conditions
Ansible supports conditional evaluations before executing a specific task on the target hosts. If the set condition is true, Ansible will go ahead and perform the task. If the condition is not true (unmet), Ansible will skip the specified task.

### 3.1 Handles for Conditional Task Execution
- A handler is a task that is only executed when it is triggered by a task that has changed something
- Handlers are executed after all tasks in a play
- If any task fails after the task that has called the handler, the handler is not executed at all 
- Use **force_handlers** to change that behavior. 

### 3.2 Using When to run Tasks Based on Specific Conditions
- when statements are used to run task conditionally
- Playbook variables, registered variables and facts can be used in conditions and make sure that the tasks only run if specific conditions are true
- For instance,check if a task has run successfully,a certain amount of memory is available, a file exists and more
- Using facts is extremely common in when statements. 
Examples
```list
ansible_machine == "x86_64"
ansible_memfree <= 256
my_variable is defined
``` 
At times you want to execute or skip a task based on the outcome of an earlier task in a playbook. For instance, you might want to configure a service after a previous task upgrade. In that case, use a registered variable. A registered variable allows you to register the outcome of the earlier task as a variable and use it for the next task as an input.

### 3.3 loop to Process a list of items
Ansible uses the following keywords for its loop structures:

* loop
* with_<**lookup**>
* until

As the name suggests, **loop** is the go-to command for implementing loops in blocks of code.

Similar to loop, you have with_<lookup>. This command requires you to provide it with a lookup plugin. It is recommended to use with_* rather than loop when lookup plugins are involved.

**Until** allows you to keep on executing a task till the required condition is met. It is the closest to the **while** condition in the control flow.
