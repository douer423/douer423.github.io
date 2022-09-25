---
title: Linux history and Distribution Introduction
author: frank
date: 2022-09-24 23:32:00 +0800
categories: [Linux,Tutorial]
tags: [liunx fundamental]     
render_with_liquid: false
---


## 1.History
>An operating system (OS) is system software that manages computer hardware, software resources, and provides common services for computer programs.([Operating system - Wikipedia](https://en.wikipedia.org/wiki/Operating_system))

This repository will record my journey of Linux.

To learn about how Linux came to be, let’s go back to the beginning to 1969 where Ken Thompson and Dennis Ritchie of Bell Laboratories developed the UNIX operating system. It was later rewritten in C to make it more portable and eventually became a widely used operating system.

A decade or so later, Richard Stallman started working on the GNU (GNU is Not UNIX) project, the GNU kernel called Hurd, which unfortunately never came to completion. The GNU General Public License (GPL), a free software license, was also created as a result of this.

The kernel is the most important piece in the operating system. It allows the hardware to talk to the software. It also does a whole lot of other things, but we’ll dig into that in a different course. For now, just know that the kernel controls pretty much everything that happens on your system.

During this time other efforts such as BSD, MINIX, etc were developed to be UNIX like-systems. However, one thing that all these UNIX like-systems had in common was the lack of a unified kernel.

Then in 1991, a young fellow named Linus Torvalds started developing what we now know today as the Linux kernel.

For more details,you may read this [acticle](https://bbs.huaweicloud.com/blogs/312682).

## 2.Linux distributions
Linux is typically packaged in a Linux distribution,a Linux distribution is simply a collection of a specific kernel with specific support programs. Most of the included software is free and open source software. There are many distributions designed for personal computers, but there are also Linux distributions designed for supercomputers or for a specific purpose, e.g. penetration testing (Kali Linux).

There are many distributions available (over six hundred), but two major distributions became the foundation for many other distributions: **Red Hat** and **Debian**.

Some of the more popular Linux distributions beside [Red Hat](https://linuxjourney.com/lesson/red-hat-enterprise-linux) and [Debian](https://linuxjourney.com/lesson/debian) are [Ubuntu](https://linuxjourney.com/lesson/ubuntu), [openSUSE](https://linuxjourney.com/lesson/opensuse), [Fedora](https://linuxjourney.com/lesson/fedora), [Gentoo](https://linuxjourney.com/lesson/gentoo), and [Arch Linux](https://linuxjourney.com/lesson/arch-linux).