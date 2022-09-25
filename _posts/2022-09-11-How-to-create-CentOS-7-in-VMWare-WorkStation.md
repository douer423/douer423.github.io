---
title: How to create CentOS 7 server in VMWARE Workstation
author: frank
date: 2022-09-11 15:11:00 +0800
categories: [Operating System,CentOS]
tags: [installation,linux practices]     
render_with_liquid: false
---

Step-by-step guidance of installing CentOS on VMware
## 1. Requirements
1. Vmware Workstation Pro 12
2. CentOS 7.8.2003 [mirror download](http://mirrors.aliyun.com/centos/7.8.2003/isos/x86_64/)

## 2.Vmware Creation

1. Open VMware Workstation Pro 12,Click **Create New Server**
2. Click **Customer Configuration**
3. Click **Next**
4. Choose **Install Operation Sysytem Later**,Click **Next**
5. Choose **Linux(L)**,Version(V) **CentOS 64 bits**,Click **Next**
6. Name the Server and choose location,Click **Next**
7. Configure process and CPU cores,Click **Next**
8. Configure memory
9. Network configure [Configuring Virtual Network Adapter Settings](https://docs.vmware.com/en/VMware-Workstation-Player-for-Windows/16.0/com.vmware.player.win.using.doc/GUID-C82DCB68-2EFA-460A-A765-37225883337D.html)
10. I/O controller configure,choose **LSI Logic(L)**,Click **Next**
11. Disk Type,choose **SCSI(S)**,Click **Next**
12. Disk Size,fill disk size,Click **Next**
13. Click **Next**
14. Click **Finish**

## 3. Install Linux
1. Vmware configuration-->**CD/DVD(IDE)**-->Choose**Use mirror file**
2. Start VMware server,Choose **Install CentOS 7** in the console page
3. Choose System lauguage **English**
4. Choose DATE&TIME 
5. INSTALLATION DESTINATION,choose **I will configure partitioning.**
6. MANUAL PARTITIONING, / /boot /data swap
7. NETWORK&HOST NAME
8. Start installation



For more details,you may read this [acticle](https://www.cnblogs.com/43945616b/p/13599671.html).




