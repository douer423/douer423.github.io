---
title: How to check your Linux version
author: frank
date: 2022-09-24 23:32:00 +0800
categories: [Linux,Tutorial]
tags: [liunx fundamental]     
render_with_liquid: false
---

When most people think of Linux, an open source operating system that serves as an alternative to Microsoft and Apple comes to mind. But unlike these market leaders that offer commercial operating systems, there is no single Linux operating system.

Instead, there is a whole series of free, open-source operating systems (referred to as “distributions”) that are built based on the Linux kernel. This means that Linux merely serves as the basis for potential operating systems, which are then built from the kernel and other programming elements. While Microsoft and Apple release closed-source, proprietary software products, the Linux kernel is open-source code that any member of the Linux community can use or modify to make their own applications and operating systems.

Since there exist countless Linux versions, it’s of utmost importance to know which version you’re running, especially when you run into technical problems, have questions, or want to do an update. Luckily, it’s very easy to find out. Keep reading for instructions on how tocheck your Linux version.

## 1. Linux version: what do the distribution and version number mean?
As of June 2020, there are now over 500 unique Linux distributions. The best-known are Ubuntu, Debian, Fedora, SUSE, Manjaro, and Linux Mint.

The family tree for Ubuntu alone contains over 65 software applications built on the basis of Ubuntu. The current distribution was released in 2020 with the version number 20.04. The first version of Ubuntu came out in 2004 and was based on the Debian operating system.

The various Linux distributions can be roughly divided into three basic family trees as well as countless other smaller branches and independent versions. For example, the entire Ubuntu family is based on Debian, the distribution Fedora is based on Red Hat Linux, and SUSE used Slackware.

Even though they’re all based on the Linux kernel, the various distributions serve as their own operating systems with different GNU toolchains and graphic interfaces. In order to find your way in the busy Linux landscape, it’s important to know which version of the Linux kernel and which distribution you’re using.
## 2. Checking the Linux version in the terminal

Whether you’re using Linux privately or professionally, it’s always important to know which Linux version and distribution you’re working with. That way you’ll know which package manager you’ll need for downloading new tools and updates, and which Linux forum you should turn to when you have questions or experience problems.

If you’re looking for details about your Linux version, there are two words which will be of particular significance:

* The version number of the distribution
* The version of the Linux kernel

### 2.1 Distribution version number
```shell
cat /etc/*release
```
## 2.2 Linux kernel version number
If you’d like to know which version of the Linux kernel you’re using, type the following command into the terminal and press enter:
```shell
uname -r
```
If you’d like to see more information (about computer architecture for example), you can enter the following command:
```shell
uname -a
```

