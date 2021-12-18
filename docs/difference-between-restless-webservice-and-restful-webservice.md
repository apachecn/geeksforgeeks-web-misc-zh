# 不安分的网络服务和安心的网络服务的区别

> 原文:[https://www . geesforgeks . org/不安分的 webservice 和 restful web service 的区别/](https://www.geeksforgeeks.org/difference-between-restless-webservice-and-restful-webservice/)

在这里，这两个术语大多彼此相似，但它们有一些显著的差异。但在此之前，我们需要了解什么是 REST。 [REST](https://www.geeksforgeeks.org/rest-api-introduction/) 代表**代表状态转移。**由 HTTP(超文本传输协议)幕后推手罗伊·菲尔丁介绍。他制作了 REST，这样我们就可以充分利用 HTTP。它使用基于传输协议的执行操作，如 HTTP-post、get、put、delete。

REST 也被称为 web 服务的架构风格，主要有三个组成部分–

*   Data exchange format (JSON colloquially)
*   Transport (HTTP only)
*   Service definition (WADL/ Swagger/...)

Rest Services 也有以下原则:

*   It does not contain any built-in encryption.
*   No session, no status.
*   It uses only one protocol, that is, HTTP.
*   It returns anything as JSON.
*   能够使用超文本传输协议执行 CRUD 操作。

    **不安分的 WebService:** 是不服从 REST 架构的 web 服务。它使用一个 XML 文档发送和接收消息。它还使用代表简单对象访问协议的 SOAP。这项服务对于需要确保安全的应用程序非常有用。构建一个不安分的网络服务很容易。

    **Restfull web service:**它是一个使用 REST 架构的 web 服务。它还使用带有 REST 原则的请求和响应类型请求。该服务对于必须通过 API 调用与不同服务通信的应用程序非常有用。这些应用程序是为执行 CRUD 操作而构建的。使用该服务构建应用程序是一种不太安全的方式。Restful web 服务提供与不同计算机的互连。

    **不安分和 Restlful Web 服务的区别:**

    | Basic terminology | Uneasy Web service | Restful Web Service |
    | --- | --- | --- |
    | Architecture | It is not based on the principle of REST. | Based on the principle of REST architecture, it can be integrated with other computer systems on the network. |
    | REST principle | It does not use the rest principle. | It uses the REST principle. |
    | Communication | It uses SOAP service. | It uses REST service. |
    | Data format | It only supports XML format. | Support JSON, HTML and other formats. |
    | Functions | These services use service interfaces to show business logic. | These services use URLs to show business logic. |
    | Availability and flexibility | For users, its availability and flexibility are poor. | It is easier to use and more flexible for users. |
    | Security | is safer because it has designed its own security layer. | It is not very secure, because it uses the security layer to communicate protocols. |
    | Bandwidth | The bandwidth it uses is very small. | It uses a lot of bandwidth. |