---
title: Get Start With DBeaver
author: frank
date: 2022-11-20 22:53:00 +0800
categories: [Database,Mysql]
tags: [tools]     
render_with_liquid: false
---

If you're a database developer, you know that you need different SQL statements for creating schemas, ad-hoc querying, initiating backups, or troubleshooting. For these scenarios, finding the right graphical tool can speed up these tasks and make you more productive. 

This post will show you how to work with database using popular GUI tools.

## 1. What is DBeaver?

[DBeaver](https://dbeaver.io/) is a free multi-platform database management tool for developers, SQL programmers, DBAs, and analysts. It is written in Java, and supports a variety of databases including MySQL, PostgreSQL, MariaDB, and even YugabyteDB! In addition to the databases mentioned, there are plugins and extensions for many other data products that support the JDBC driver.

In a nutshell, DBeaver gives you all the must-have features you'd expect from any database GUI tool including:

* A connection and metadata browser
* SQL query editor and executor
* A rich in-line data editor
* Entity relationship (ER) diagrams
  
DBeaver is intuitive and there are a lot of helpful tips that can aid you in configuring and exploring your database seamlessly.

Please note that for the purposes of this blog post we'll be focused on getting up and running on a Windows, but DBeaver supports all the major operating platforms.

## 2. Installing DBeaver

1. Navigate to: https://dbeaver.io/files/dbeaver-ce-latest-x86_64-setup.exe
2. Download the dbeaver-ce-x.y.z-x86_64-setup.exe to a folder created at (D:\Downloads)
3. Right-Clicking the exe file and select Run as Administrator
4. Change the default installation directory to (D:\Program Files\DBeaver)
5. Press Finish
   
## 3. Working with DBeaver
### 3.1 Create a connection in DBeaver
Click the **New Database Connection** button and then select e.g. MySQL as the database.

In the **Connection settings** window, enter the host, port, username, and password. You can test the connection before it's created:

You can also set a name for your driver, which is helpful when you need to manage multiple databases in DBeaver. In the “Connection settings” window, click the **General** tab and set a name for the connection.

### 3.2 Set SQL Editor Formatting

One of the most charming features of DBeaver is code-autocompletion, auto-case conversion, and syntax highlighting. This is extremely handy because SQL queries are very flexible. You can write your queries in any style and they will always work. However, when it comes to readability, it's another story. The auto-completion and auto-formatting feature of DBeaver can let you write clean, beautiful, and readable SQL queries very conveniently.

We can set SQL Editor Formatting for a single connection. However, it's better to set the formatting style globally so it applies to all connections.

Select the **Window** menu and then the **Preferences** submenu. In the **Preferences** window opened, select **Editors** => **SQL Editor** => **Formatting**. For the formatting, it's recommended to set the configurations as follows:

![DBeaver SQL Editor Formatiing](https://miro.medium.com/max/1100/1*xPV_zR93TS63eLErzgya8Q.webp)
With these settings, your SQL queries will be formatted accordingly if you select your SQL queries and press **CTRL + SHIFT + F** to automatically format them.

### 3.3 Enable keyword auto case conversion
Another handy feature I enjoy a lot is keyword auto case conversion, namely after a SQL keyword is typed, it will be automatically converted to the corresponding case, which is the upper case as set in the above step. To enable keyword auto case conversion, select **Editors** => **SQL Editor** => **Code Editor** in the **Preferences** window opened above, then enable **Convert keyword case**. You can also enable other code conversions that you like:
![keyword auto case convert](https://miro.medium.com/max/828/1*T4zFvAMPVRadC-srHL02_g.webp)

### 3.4 Write and execute SQL queries in DBeaver
You can right-click on your database connection on the left navigation bar, then select **SQL Editor** => **New SQL script**. A new SQL script editor will be opened for you. Now you can start to enjoy writing SQL queries in DBeaver, especially keyword auto case conversion and code auto-completion :)

## 4. Reference links
[dbeaver official document](https://github.com/dbeaver/dbeaver/wiki/)   
[dbeaver essential training](https://www.linkedin.com/learning/dbeaver-essential-training)   
[some tips for using dbeaver](https://towardsdatascience.com/some-tips-for-using-dbeaver-a-univeral-database-tool-94af18d50671)