# 获取原料药

> 原文:[https://www.geeksforgeeks.org/fetch-api/](https://www.geeksforgeeks.org/fetch-api/)

长久以来 **XMLHttpRequest** 一直被网络开发者信任的“朋友”所使用。XMLHttpRequest 已经启用了 ajax 和一种全新的交互式曝光。
然而，它正慢慢被**获取应用编程接口**所取代。这两者都提供相同的工作，即从不同的网络异步获取数据，但是获取应用编程接口是基于承诺的。这提供了更简洁明了的语法。
Fetch API 提供了在窗口对象上定义的 Fetch()方法。这用于执行请求。该方法返回一个 Promise，该 Promise 可进一步用于检索对请求的响应。
**基本语法:**

```
 fetch(url) //call the fetch function passing the url of the API as a parameter
.then(function(){
  //code for handling data from API
});
.catch(function(){
  //code when the server returns any error
});
```

**注意:**默认情况下，fetch()不会从服务器发送或接收任何 cookies，从而导致未经身份验证的请求。
以下是当我们收到关于我们想要如何处理信息的回复时可以使用的方法列表:

1.  **克隆():**用于创建响应的克隆。
2.  **重定向():**用于创建不同 url 的强响应。
3.  **arrayBuffer():** 我们返回一个用 arrayBuffer 解析的 Promise。
4.  **formData():** 也返回一个 Promise，用 FormDataObject 解析。
5.  **blob():** 与上面相同，只是用 blob 解析。
6.  **text():** 这通过一个字符串来解析。
7.  **json():** 与 [JSON](https://www.geeksforgeeks.org/javascript-json/) 达成承诺。

**请求:**
请求对象表示提取调用的请求部分。通过传递获取请求，您可以提出高级和定制的请求:

1.  **方法:** GET、POST、PUT
2.  **网址:**请求的网址
3.  **标题:**标题对象
4.  **推荐人:**请求的推荐人
5.  **模式:**球茎，无球茎，同源
6.  **凭证:**cookie 应该与请求一起吗？省略，同源
7.  **缓存:**缓存模式(默认，重载，无缓存)

**加载 JSON**
在请求完成之前，我们不能阻塞用户界面。这就是 fetch()方法返回 Promise 的原因。承诺实际上是一个代表未来结果的对象。然后()方法用于等待服务器端的响应，并将其记录到控制台。
下面的代码片段解释了上面的逻辑:

## java 描述语言

```
fetch('https://www.reddit.com/r/javascript/top/.json?limit=5')
.then(res=>res.json())
.then(json=>console.log(json));
```