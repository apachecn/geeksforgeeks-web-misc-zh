# 【REST API 和 SOAP API 的区别

> 原文:[https://www . geesforgeks . org/rest-API 和-soap-api 的区别/](https://www.geeksforgeeks.org/difference-between-rest-api-and-soap-api/)

SOAP 和 REST APIs 之间没有直接的比较。但是下面列出的几点可以让你在这两种网络服务中做出更好的选择。以下是:

*   肥皂代表 **S** 执行 **O** 对象 **A** 访问 **P** 旋转和休息代表 **RE** 表象 **S** 状态 **T** 转移。
*   Because SOAP is a protocol, it follows a strict standard to allow communication between client and server, while REST is an architectural style that does not follow any strict standards, but follows six constraints defined by Roy Fielding in 2000\. These constraints are-unified interface, client-server, stateless, cacheable, layered system and on-demand coding.
*   SOAP only uses XML to exchange information in its message format, while REST is not limited to which media type XML and its implementers choose to use, such as XML, JSON and plain text. And REST can use SOAP protocol, but SOAP can't use REST.
*   Service interface representing business logic, SOAP uses @WebService, while REST uses URIs like @Path instead of interfaces.
*   SOAP is difficult to implement and needs more bandwidth, while REST is easy to implement and needs less bandwidth, such as smart phones.
*   The advantage of SOAP over REST is that SOAP has ACID compliance transactions. Some applications need transactional capabilities, which are accepted by SOAP, but lacking in REST.
*   On the basis of security, SOAP has SSL ( **s** ecure **s** socket **l** layer) and WS-security, while REST has SSL and HTTPS. If it is a bank account password, card number, etc. SOAP is superior to REST. Security issues are completely related to your application requirements, and you must build your own security. This is about what type of protocol you use.