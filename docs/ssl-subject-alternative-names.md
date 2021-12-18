# SSL 主题备选名称

> 原文:[https://www . geesforgeks . org/SSL-subject-alternative-name/](https://www.geeksforgeeks.org/ssl-subject-alternative-names/)

安全套接字层/传输安全层通常称为 SSL/TLS，是一种加密协议，旨在加密超文本传输协议，也称为 HTTP。新设计的 HTTPS 协议已被几乎所有新老网站广泛接受，对于共享和进行机密交易的网站，如银行和金融网站，收集个人身份信息的网站，即使是正常的静态页面，也应该通过 HTTPS 请求，因为几乎所有现代浏览器都将 HTTP 请求标记为安全。

感谢 EFF 和其他支持组织。已经创建了一个免费的证书颁发机构，用于颁发免费的可信和安全的 SSL 证书。LetsEncrypt 项目旨在为每个网站提供免费的 SSL，使网站更加安全。LetsEncrypt 还颁发了 SSL 证书，可以用于我们的 1 级深度的域和子域。

这是 GeeksforGeeks 的 letsencrypt 证书的一个例子

![](img/e7db870fcf2c9bdf51a0b7c9d5ef1ae3.png)

您可以看到证书是与 11 个子域名的 GeeksforGeeks 共享的，使用的是 Subject Alternative 名称，子域名是

*   api.geeksforgeeks.org
*   auth.geeksforgeeks.org
*   authgeeksforgeeks.org
*   cdncontribute.geeksforgeeks.org
*   cdnpractice.geeksforgeeks.org
*   cdnvideos.geeksforgeeks.org
*   media.geeksforgeeks.org
*   practice.geeksforgeeks.org
*   contribute.geeksforgeeks.org
*   ide.geeksforgeeks.org
*   www.geeksforgeeks.org

**SSL 证书中的主题替代名称:**主题替代名称是 X.509 的扩展，它允许使用一个字段将各种值与安全证书相关联，该字段允许您指定其他主机名、站点、IP 地址、常用名称等。受单个 SSL 证书保护，如多域或扩展验证多域证书。在大多数情况下，主机名通配符证书中的所有子域大多使用此扩展进行保护。

新站长了解这一部分的最重要原因是因为许多网络主机，CDN 的，当然还有 Cloudflare 都使用这一技术向他们的客户端颁发 SSL 证书，这些证书不仅由子域共享，而且也与不同的域共享。例如，此 SSL 的典型存储区域网络看起来像–

*   example1.com
*   example2.com
*   *.example3.com
*   *.*.example4.com

解释主题替代名称的主要原因是，许多文章声称，如果发现其中一个域从事恶意和不道德的活动，谷歌将把所有域列入黑名单，这是不真实的。谷歌的一名成员明确表示，他们将只将该域列入黑名单，而不是全部，他们表示，如果证书颁发机构从存储区域网络字段中删除该域及其所有相应的子域，效果会更好。此外，对于“域验证”和“通配符域验证”SSL 证书，一些网络钓鱼邮件可能会以更高的价格出现在您的收件箱中。最好查找发件人的电子邮件，并通过搜索证书颁发机构颁发的 SSL 来验证价格。

您可以通过单击 chrome 中域旁边绿色锁，单击将打开证书查看器证书，来检查您与谁共享您 SSL 证书。您可以看到使用它的证书的完整细节。向下滚动，直到您看到证书主题替代名称，单击它，然后您可以看到哪些域和子域共享 SSL 证书。