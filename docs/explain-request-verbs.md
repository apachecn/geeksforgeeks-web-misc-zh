# 解释请求动词

> 原文:[https://www.geeksforgeeks.org/explain-request-verbs/](https://www.geeksforgeeks.org/explain-request-verbs/)

HTTP 方法提供了一种方法来指定要在给定资源上执行的所需操作。结果取决于服务器的实现，可以是预先存在的数据，也可以是动态生成的数据。

最常用的 HTTP 方法是 GET、POST、PUT、PATCH 和 DELETE，它们对应于 CRUD(创建、读取、更新、删除)操作。

**请求方式:**

1.  **GET:**GET 方法用于检索请求-URL 标识的信息。它是信息检索的主要方式。它不改变所请求资源的状态，据说是一种安全的方法。如果请求 URL 引用了一个产生数据的过程，产生的数据将作为响应返回，而不是源文本，除非该文本是过程的输出。

2.  **POST:**POST 方法用于将数据作为请求体发送到服务器。此方法指示请求正文中的数据将被接受，并且最有可能存储在服务器中。内容类型头指示请求正文的类型。它主要用于上传文件或提交完整的网络表单。在响应包含适当的缓存控制或过期标头字段之前，对该方法的响应将不可缓存。

3.  **PUT:**PUT 方法用于用请求负载替换资源已经存在的状态，或者在资源不存在(由源服务器决定)的情况下创建资源。

4.  **PATCH:**PATCH 方法用于对资源进行部分更新。它可以被认为是一个指令集，描述对服务器上已经存在的数据的修改，以产生数据的新版本，它不被认为是完整的资源。

5.  **DELETE:**DELETE 方法用于删除源服务器上的指定资源。即使从服务器返回的状态代码表明操作已经执行，客户端也不能确信操作已经执行。

6.  **HEAD:**HEAD 与 GET 请求相同，但是服务器不能发送响应正文，而应该发送与用 GET 方法请求 URI 时相同的头。它可用于获取元数据，而无需从服务器传输响应正文，并且通常用于测试超文本链接的有效性、可访问性和最近的修改。

7.  **CONNECT:**CONNECT 方法用于通过代理服务器建立端到端的 HTTP 隧道。

8.  **OPTIONS:**OPTIONS 方法请求给定资源允许的通信选项。可以发送此请求来找出支持的 HTTP 方法和其他支持的选项，而无需请求资源。

9.  **TRACE:**TRACE 方法请求服务器在响应正文中发送它收到的确切请求。这对诊断很有用。

**一个简单的 JavaScript GET 请求:**

## java 描述语言

```html
// GET request
fetch("https://jsonplaceholder.typicode.com/users/2")

    // Convert response to json
      .then((response) => response.json())

    // Print data to console
      .then((data) => console.log(data));
```