---
title: How to install Git on CentOS 7
author: frank
date: 2022-09-24 23:32:00 +0800
categories: [Devops,Version Control]
tags: [git,linux practices]     
render_with_liquid: false
---

## Introduction
Version control has become an indispensable tool in modern software development. Version control systems allow you to keep track of your software at the source level. You can track changes, revert to previous stages, and branch off from the base code to create alternative versions of files and directories.

One of the most popular version control systems is [git](https://git-scm.com/). Many projects maintain their files in a Git repository, and sites like GitHub and Bitbucket have made sharing and contributing to code with Git easier than ever.

In this guide, we will demonstrate how to install Git on a CentOS 7 server. We will cover how to install the software in a couple of different ways, each with their own benefits, along with how to set up Git so that you can begin collaborating right away.

## Prerequisites
Before you begin with this guide, there are a few steps that need to be completed first.

You will need a CentOS 7 server installed. If you haven't done this yet, you can install CentOS7 according my installation [article](https://douer423.github.io/posts/How-to-create-CentOS7-in-VMWare-WorkStation/).

Once you have your CentOS 7 server, you can use it to SSH into your CentOS server and continue with the installation of Git.

## Install Git
The two most common ways to install Git will be described in this section. Each option has their own advantages and disadvantages, and the choice you make will depend on your own needs. For example, users who want to maintain updates to the Git software will likely want to use yum to install Git, while users who need features presented by a specific version of Git will want to build that version from source.

### Install Git with Yum

The easiest way to install Git and have it ready to use is to use CentOS's default repositories. This is the fastest method, but the Git version that is installed this way may be older than the newest version available. If you need the latest release, consider compiling git from source (the steps for this method can be found further down this tutorial).

Use yum, CentOS's native package manager, to search for and install the latest git package available in CentOS's repositories:
```shell
yum install git
```
If the command completes without error, you will have git downloaded and installed. To double-check that it is working correctly, try running Git's built-in version check:
```shell
git --version
```
If that check produced a Git version number, then you can now move on to Setting up Git, found further down this article.

### Install Git from Source
If you want to download the latest release of Git available, or simply want more flexibility in the installation process, the best method for you is to compile the software from source. This takes longer, and will not be updated and maintained through the yum package manager, but it will allow you to download a newer version than what is available through the CentOS repositories, and will give you some control over the options that you can include.

Before you begin, you'll need to install the software that git depends on. These dependencies are all available in the default CentOS repositories, along with the tools that we need to build a binary from source:

```shell
yum groupinstall -y "Development Tools"
yum install -y gettext-devel openssl-devel perl-CPAN perl-devel zlib-devel
```
After you have installed the necessary dependencies, you can go ahead and look up the version of Git that you want by visiting the project's releases [page](https://github.com/git/git/tags) on GitHub.

The version at the top of the list is the most recent release. If it does not have -rc (short for "Release Candidate") in the name, that means that it is a stable release and is safe for use. Click on the version you want to download to be taken to that version's release page. Then right-click on the Source code (tar.gz)button and copy the link to your clipboard.

Now we are going to use the wget command in our CentOS server to download the source archive from the link that we copied, renaming it to git.tar.gz in the process so that it is easier to work with.

>Note: the URL that you copied may be different from mine, since the release that you download may be different.
{: .prompt-info }

```shell
cd /usr/local/
wget https://www.kernel.org/pub/software/scm/git/v2.37.3.tar.gz
```
Once the download is complete, we can unpack the source archive using tar. We'll need a few extra flags to make sure that the unpacking is done correctly: 

```shell
tar -xzvf v2.37.3.tar.gz -C /usr/local/
```

This will unpack the compressed source to a folder named after the version of Git that we downloaded (in this example, the version is 2.37.3, so the folder is named git-2.1.2). We'll need to move to that folder to begin configuring our build. Instead of bothering with the full version name in the folder, we can use a wildcard (*) to save us some trouble in moving to that folder.

```shell
cd git-*
```
Once we are in the source folder, we can begin the source build process. This starts with some pre-build checks for things like software dependencies and hardware configurations. We can check for everything that we need with the configure script that is generated by make configure. This script will also use a --prefix to declare /usr/local (the default program folder for Linux platforms) as the appropriate destination for the new binary, and will create a Makefile to be used in the following step.

```shell
make configure
./configure --prefix=/usr/local/git
```

Makefiles are scriptable configuration files that are processed by the make utility. Our Makefile will tell makehow to compile a program and link it to our CentOS installation so that we can execute the program properly. With a Makefile in place, we can now execute make install (with sudo privileges) to compile the source code into a working program and install it to our server:

```shell
make install
```

Git should now be built and installed on your CentOS 7 server. To double-check that it is working correctly, try running Git's built-in version check:

```shell
git --version
```
If that check produced a Git version number, then you can now move on to Setting up Git below.

## Set Up Git
Now that you have git installed, you will need to submit some information about yourself so that commit messages will be generated with the correct information attached. To do this, use the git configcommand to provide the name and email address that you would like to have embedded into your commits:

```shell
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

To confirm that these configurations were added successfully, we can see all of the configuration items that have been set by typing:
```shell
git config --list
```
This configuration will save you the trouble of seeing an error message and having to revise commits after you submit them.

To add git command in PATH,we can set by typing:
```shell
echo "export PATH=$PATH:/usr/local/git/bin" >> /etc/profile
```
