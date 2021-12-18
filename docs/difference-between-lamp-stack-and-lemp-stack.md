# 【LAMP 堆栈与 LEMP 堆栈的区别？

> 原文:[https://www . geesforgeks . org/lamp-stack 和-lemp-stack 的区别/](https://www.geeksforgeeks.org/difference-between-lamp-stack-and-lemp-stack/)

【LAMP 与 LEMP 栈的区别:
Web Stack 或 Web 应用程序栈是指一起用于构建网站或 Web 应用程序的软件的编译。

**构建堆栈的基本要求是:**

*   操作系统
*   web 服务器
*   数据库ˌ资料库
*   脚本解释器

**1。LAMP 栈:**
LAMP 栈是 Linux 操作系统、Apache Server、MySQL 数据库、PHP 的集合。LAMP 基本上是创建动态 web 应用程序所需的软件集合。LAMP 是免费和开源的。

*   **Linux–**
    一个开源的**操作系统**。从 20 世纪 90 年代就有了。它是最安全、最可靠的操作系统之一。
*   **Apache–**
    这是一个免费的、跨平台的、开源的网络服务器。阿帕奇网络服务器在全球范围内发展后，成为最受欢迎的网络服务器。它使用像 **HTTP 或 HTTPS** 这样的协议，这是互联网上服务器和客户端之间最重要的通信协议。
*   **MySQL–**
    MySQL 是一个基于关系模型的 **SQL 数据库**。在关系模型中，数据以**表格形式**存储，非常适合大型或小型应用。您可以使用查询在数据库中创建、修改或维护数据。
*   **PHP–**
    一种与服务器和数据库通信的**服务器端脚本语言**。PHP 和 MySQL 是一个强大的组合。PHP 用于后端网络开发，也用于面向对象编程。

由于 LAMP 是最受欢迎的堆栈，因此 LAMP 最大的优势是其**社区支持**，因此作为开发人员，您可能面临的任何问题都可能已经有人面对过，并且有其解决方案。

**灯组的工作–**

1.  **Apache:Web Server–**
    这是目前世界上使用最多、最成熟的 Web 服务器。它处理用户请求，并用网络资产响应用户。如果请求是针对一个 PHP 文件的，它会将其传递给 PHP。
2.  **PHP:Scripting Language–**
    前面提到的 PHP 是一种服务器端语言，它根据用户请求与数据库进行通信，并向 apache 呈现一个结果，Apache 再根据请求和编写的代码逻辑进行响应。
3.  **MySQL:Database–**
    所有的用户数据都是从这里存储、更新和获取的。Php 与 My SQL 通信，根据用户请求获取或插入数据。
4.  **Linux:操作系统–**
    最安全可靠的操作系统。上面提到的所有体系结构都是可能的，因为操作系统运行在服务器的这个体系结构的基础上。

**2。LEMP 栈:**
LEMP 栈是 Linux OS、Nginx Server、MySQL Database、PHP 的集合。LEMP 也是开源的，用于创建动态网络应用程序。

*   **Linux–**
    一个开源的**操作系统。**网络服务器运行在一个操作系统上，LEMP 的例子是 Linux。
*   **Nginx–**
    发音为**“发动机 X”**。它是 2004 年发布的网络服务器。Nginx 现在比 Apache 更受欢迎(尽管 Apache 在全球范围内使用得更多)。此外，与 apache 相比，它具有更好的安全性和更少的代码库，并且在某些情况下比 Apache 更快。
*   **MySQL–**
    MySQL 是一个基于关系模型的基于 SQL 的数据库。如上所述。
*   **PHP–**
    一种与服务器和数据库通信的服务器端脚本语言。与 LAMP 中的所有其他组件类似。

**LEMP 堆栈的工作–**

1.  **Nginx:Webserver–**
    类似于 Apache 在 LAMP 栈中为 LEMP Nginx 所做的工作，处理用户请求并以合适的输出进行响应。
2.  **PHP:脚本语言–**
    处理请求、与数据库通信、用户认证等。
3.  **MySQL:Database–**
    类似于 LAMP 栈中的工作。
4.  **Linux:操作系统–**
    Linux 在这个栈的底层运行。

**LAMP 与 LEMP 栈的区别:**

<figure class="table">T21

| Sl 否- | **LEMP 栈** | **LAMP 栈** |
| 1。 | Use Nginx as a network server. | Use Apache as the network server. |
| 2。 | Nginx follows an event-driven approach. | Nginx follows a process-driven approach. |
| 3。 | Better handle requests with higher load. | Can slow down under heavy load. |
| 4。 | Nginx processes multiple requests in one thread. | Apache creates a new thread for each request. |
| 5。 | Apache allows additional configuration through the. htaccess file. | Nginx does not allow additional configuration. |
| 6。 | Better use cases for static websites | Better use cases for dynamic websites |
| 7。 | Scalability is user-friendly | Not as scalable as Nginx. |
| 8。 | Faster and lighter | There are more features, functions and more application modules than Nginx. |

</figure>