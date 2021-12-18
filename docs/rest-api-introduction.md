# REST API(简介)

> 原文:[https://www.geeksforgeeks.org/rest-api-introduction/](https://www.geeksforgeeks.org/rest-api-introduction/)

**RE** 表示法 **S** 状态**T**transfer(REST)是一种架构风格，定义了一组用于创建 web 服务的约束。 **REST API** 是一种简单灵活的访问 web 服务的方式，无需任何处理。
REST 技术通常比更健壮的简单对象访问协议(SOAP)技术更受青睐，因为 REST 使用的带宽更少，简单灵活，使其更适合互联网使用。它用于从网络服务中获取或给出一些信息。所有通过 REST API 完成的通信都只使用 HTTP 请求。

**<u>工作</u>**

一个请求以网址的形式从客户端发送到服务器，作为 HTTP GET 或 POST 或 PUT 或 DELETE 请求。之后，服务器以资源的形式返回响应，资源可以是任何东西，如 HTML、XML、Image 或 JSON。但是现在 JSON 是网络服务中最流行的格式。

![](img/e4cc8e9d29d9ab28d80f34b4c93caa2d.png)

在 **HTTP** 中，基于 REST 的体系结构通常使用五种方法，即 POST、GET、PUT、PATCH 和 DELETE。这些分别对应于创建、读取、更新和删除(或 CRUD)操作。还有其他不常用的方法，如 OPTIONS 和 HEAD。

1.  **GET:**HTTP GET 方法用于**读取**(或检索)资源的表示。在安全路径中，GET 返回一个 XML 或 JSON 表示形式和一个 HTTP 响应代码 200 (OK)。在错误情况下，它通常会返回 404(未找到)或 400(错误请求)。

2.  **POST:**POST 动词最常用于**创造**新资源。特别是，它用于创建从属资源。也就是说，从属于某个其他(例如父)资源。成功创建后，返回 HTTP 状态 201，返回一个位置头，其中包含指向新创建的 HTTP 状态为 201 的资源的链接。
    **注:** POST 既不安全也不幂等。

3.  **PUT:** 用于**更新**战力。然而，在资源标识由客户端而不是服务器选择的情况下，PUT 也可以用于**创建**资源。换句话说，如果 PUT 指向包含不存在的资源标识值的 URI。成功更新后，从 PUT 返回 200(如果没有返回正文中的任何内容，则返回 204)。如果使用 PUT 进行创建，在成功创建时返回 HTTP 状态 201。PUT 不是安全的操作，但它是幂等的。

4.  **PATCH:** 用于**修改**能力。PATCH 请求只需要包含对资源的更改，而不是完整的资源。这类似于 PUT，但是主体包含一组说明，描述了应该如何修改当前驻留在服务器上的资源以产生新版本。这意味着 PATCH 主体不应该只是资源的修改部分，而应该是某种修补语言，如 JSON Patch 或 XML Patch。PATCH 既不安全也不是幂等的。

5.  **DELETE:** 用于**删除**一个 URI 认定的资源。成功删除后，返回 HTTP 状态 200(确定)以及响应正文。

**幂等:**幂等 HTTP 方法是一种可以多次调用而没有不同结果的 HTTP 方法。如果这个方法只被调用一次，或者十次以上，这并不重要。结果应该是一样的。同样，这仅适用于结果，而不适用于资源本身。例:

## C

```html
1\. a = 4 // It is Idempotence, as final value(a = 4)
        // would not change after executing it multiple
       // times.

2\. a++ // It is not Idempotence because the final value
      // will depend upon the number of times the
     // statement is executed.
```

> RESTful web 服务非常受欢迎，因为它们重量轻、高度可扩展和可维护，并且非常常用于为基于 web 的应用程序创建 API。

**参考文献**:[https://en . Wikipedia . org/wiki/具象 _ state _ transfer](https://en.wikipedia.org/wiki/Representational_state_transfer)T4】