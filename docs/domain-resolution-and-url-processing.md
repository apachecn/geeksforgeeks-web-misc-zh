# 域名解析和网址处理

> 原文:[https://www . geesforgeks . org/domain-resolution-and-URL-processing/](https://www.geeksforgeeks.org/domain-resolution-and-url-processing/)

A **域名**是用来访问任何网站的地址。域名本质上是独一无二的，非常容易记住。通过输入域名，用户可以到达他想要的任何网站。任何网站的实际地址都是非常复杂的，但是借助于域名，这个复杂的地址可以被转换成一个简单易懂的形式。域名是借助于域名系统的规则和程序形成的。

**为什么域名很重要？**

域名容易记住，但 IP 地址不容易记住。我们举个电话簿的例子，我们不记得人的电话号码，我们只记得人的名字，然后用他们的名字搜索号码，而不是用他们的电话号码。IP 地址可以在后端更改，但域名保持不变。

**历史:**自 ARPANET 时代以来，我们一直使用人类可理解的主机数字地址形式。以前，网络上的每台计算机都用于从 SRI 的计算机中检索主机文件，SRI 用于将计算机主机名映射到数字地址。此后，随着网络开始迅速发展，用传统方法来完成这项任务变得几乎不可能，因此在 1983 年，域名系统被引入阿帕网。

**特点:**

*   The shorter the domain name, the easier it is to remember and understand. The longer the domain name, the harder it is to remember and understand. Therefore, it is advisable to keep the domain name short and clear.
*   The domain name should be easy to spell, because it is too complicated for users to remember clearly.
*   In the domain name **. Com** extension is the most popular, because many people remember the website with this extension and often forget other extensions.
*   Sometimes a domain name doesn't have any meaning, but it becomes so popular that people only need to listen to its name to recognize the domain name, so we can also create a brand, unless and until the domain name becomes a brand, we really don't need any meaning.
*   It's best not to include hyphens and numbers in the domain name, because it's very troublesome to remember.

**域名解析和网址处理步骤:**

当我们在网络浏览器中键入一个网址时，我们的计算机需要将它们转换成一个 IP 地址。这样它就可以联系我们的网络服务器并发送给您。这称为正向查找，因为我们正在将主机名转换为 IP 地址。当我们将一个 IP 地址转换为主机名时，这也被称为反向查找。

*   First, we will enter the name of the website we want to visit. For example-facebook.com.
*   Then the domain names will be mapped to their corresponding IP addresses, and it is the responsibility of the parser to convert the domain names to IP addresses. There is a parser between the request and the root server.
*   The website request first goes to the root server, which can be done by recursive method or iterative method. There are 13 root servers in the world.
*   The parser then gives the parser an IP address of the next level. The next level consists of general servers or national servers.
*   The resolver resolves the domain name from right to left, which means that in our example, it will be resolved first ". com”。 And then ". Com "provides a link to the parser, and then our request will be forwarded to the authoritative server.
*   The authoritative server stores all IP addresses and names. A specific website can have multiple IP addresses. Facebook has more than 70,000 servers, so there can be multiple IP addresses.
*   This IP address is given to the parser, and then the parser gives this IP address to our computer. Then we can access the data in the computer.

这些步骤只在我们第一次访问任何网站时执行。当我们第二次访问该网站时，我们的请求不会被转发到根服务器，因为我们的互联网服务提供商(ISP)缓存了该 IP 地址，因此无论何时您需要访问该网站，它都会轻松提供 IP 地址。

**优势:**

*   Good domain names increase credibility and are also separated from other domain names.
*   Also, domain names give brand awareness and attract many users.
*   Once the domain name becomes popular among netizens, it can increase the ranking of search engines.
*   Domain names have established unique identities in cyberspace.
*   Domain names can be resold, leased and bartered, which is also a great advantage.

**缺点:**

*   DNS registration can only be controlled by ICANN, which is a great challenge, because it is only associated with one country, so it also challenges network neutrality.
*   Only the IP address can be seen on the DNS server, and it can be manipulated by hackers from now on.
*   In addition, the DNS server is based on the slave-master relationship, which is another challenge.
*   If the host starts to fail, it is difficult to access the web page.
*   In many cases, hackers target server machines and redirect users to another web page, which leads to phishing.