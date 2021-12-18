# 网络服务和网络应用编程接口的区别

> 原文:[https://www . geesforgeks . org/web 服务和 web API 之间的差异/](https://www.geeksforgeeks.org/differences-between-web-services-and-web-api/)

**网络服务:**一个**网络服务**是任何一种可以通过互联网访问并通过 XML 编码使其对应关系正常化的服务。客户通过发送一个请求(大部分是一个 XML 消息)来调用 web 服务，服务会发回一个 XML 响应。Web 服务通过网络进行通信，HTTP 是两个框架之间最广泛认可的网络方法。Web 服务相当于 SOA(面向服务的体系结构)，基本上依赖于度量，例如，XML-RPC 和 SOAP(简单对象访问协议)。

**组件:**所有标准 web 服务都使用以下组件工作。

*   SOAP (Simple Object Access Protocol)
*   UDDI (Universal Description, Discovery and Integration)
*   WSDL (Web service description language)

**Web API:****API**代表**应用编程接口**。它是各种程序用来在它们之间进行通信的通信约定和子程序的集合。开发人员可以利用不同的应用编程接口装置，使其程序更简单、更不复杂。同样，应用编程接口鼓励开发人员用熟练的方法构建他们的产品程序。因此，简单地说，应用编程接口决定了程序段应该如何相互关联。它是一组协议和时间表，其反应在数据中以 JSON 或 XML 的形式返回。API 可以利用任何类型的通信约定，并且不像 web 服务那样受到类似的限制。

**Web 服务与 API 的区别:**

| Web service | Web API |
| --- | --- |
| A web service is an API that can only be accessed through a network connection. | API is an application program interface, which means that one application program can communicate with another application program in a standardized way. |
| Web services are used for REST, and SOAP and XML-RPC are used for communication. | API is used for any style of communication. |
| All Web services are APIs. | API is not a web service. |
| It has no lightweight design and needs a SOAP protocol to send or receive data through the system. | It has a lightweight architecture. In addition, it is very useful for gadgets with limited transmission capacity like smart phones. |
| It only supports the HTTP protocol. | Provides support for HTTP/s protocol: URL request/response header and so on. |
| It is not open source, but it can be swallowed up by any customer who understands xml. | It is an open source code, and also comes with NET framework. |
| Web services only support XML. | The API supports XML and JSON. |
| Web services can be hosted on IIS. | Web API can only be hosted on IIS and self. |