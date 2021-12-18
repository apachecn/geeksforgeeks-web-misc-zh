# 什么是 LEMP 栈？

> 原文:[https://www.geeksforgeeks.org/what-is-lemp-stack/](https://www.geeksforgeeks.org/what-is-lemp-stack/)

在使用互联网时，经常会遇到 MEAN、MERN、LEMP、PERN 等术语。这些是网络栈，由一组软件和框架或库组成，用于构建全栈网络应用程序。堆栈通常由数据库、服务器端和客户端技术、网络服务器和特定的操作系统组成。有时后端技术是跨平台的，因此没有特定的操作系统。

LEMP 是一个用于开发网络应用程序的开源网络应用程序栈。术语“LEMP”是一个首字母缩略词，代表 [Linux 操作系统](https://www.geeksforgeeks.org/linux-operating-system-cli-command-line-interface-and-gui-graphic-user-interface/)、Nginx(发音为 **engine-x** ，因此在首字母缩略词中为 **E** )网络服务器、 **M** 代表 [MySQL 数据库](https://www.geeksforgeeks.org/mysql-common-mysql-queries/)、以及 **P** 代表 [PHP 脚本语言](https://www.geeksforgeeks.org/php-tutorials/)。

**LEMP 代表:**

*   **L-** Linux 操作系统
*   **e-**engine 服务器
*   **M-** MySQL 数据库
*   **P-** PHP

LEMP 享有良好的社区支持，并在世界各地的许多高度规模的网络应用程序中使用。Nginx 是世界上仅次于 Apache 的第二大广泛使用的网络服务器。

### LEMP 堆栈的组件

堆栈的每个组件都相互通信。让我们详细讨论所有的组成部分-

**1。n 代表 Nginx:** 它是一个遵循事件驱动方法的 web 服务器，在一个线程内处理多个请求。Nginx 支持所有类似 Unix 的操作系统，也部分支持 windows。
当网页浏览器请求网页时，该请求由网络服务器处理，这里的网络服务器是 Nginx。然后，网络服务器将该请求传递给 LEMP 堆栈中使用的服务器端技术，例如作为服务器端脚本语言(如 PHP)与服务器和数据库通信。

**为什么要用 Nginx？**

*   简单的安装和配置。
*   负载平衡支持。
*   与 Apache 相比，可以处理更多的并发连接。
*   服务静态文件最快。
*   与常用应用程序兼容。

**2。p 代表 PHP:** 它代表超文本预处理器，是一种脚本语言，在服务器端工作，与数据库 MySQL 通信，完成用户请求的所有操作，如获取数据、添加数据、操作数据或处理数据。

**为什么用 PHP？**

*   大型社区支持。
*   数据库连接的更多选项。
*   廉价的网络托管。
*   开源且免费。
*   最流行的 CMS WordPress 运行在 PHP 上。

**3。m 代表 MySQL:** 它是一个基于 SQL 的开源数据库，用于存储数据和操作数据，同时保持数据的一致性和完整性。它以表格形式在行和列中组织数据。它也符合 ACID 标准。

**为什么用 MySQL？**

*   它是开源的。
*   强大的数据保护。
*   高度可扩展
*   高性能。
*   可扩展性和灵活性

**4。l 代表 Linux:**web 服务器运行在 Linux 操作系统上。它是免费和开源的，众所周知，它高度安全，即使与 Windows 或 macOS 相比，也不太容易受到恶意软件和病毒的攻击。

**为什么要用 Linux？**

*   高度安全。
*   高度稳定。
*   免费开源。
*   强大的社区支持。
*   定制灵活。

**LEMP 优势:**

*   使用 LEMP 的好处之一是它广泛的社区支持。
*   后端的 PHP 和 MySQL 一起非常强大，也有大型社区支持和几个托管提供商的支持。
*   LEMP 是开源的。
*   LEMP 的另一个好处是 Nginx 速度更快，能够处理大量负载。

**LEMP 的劣势:**

*   如果考虑配置，Nginx 不允许额外的配置，这是一个缺点，不像 Apache，因为它在这种情况下更灵活。
*   不够灵活，无法支持动态模块和加载。