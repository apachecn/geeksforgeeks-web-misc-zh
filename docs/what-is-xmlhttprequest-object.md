# 什么是 XMLHTTPRequest 对象？

> 原文:[https://www . geesforgeks . org/what-is-xmlhttprequest-object/](https://www.geeksforgeeks.org/what-is-xmlhttprequest-object/)

XMLHTTPRequest 对象是一个用于从服务器获取数据的应用编程接口。XMLHTTPRequest 基本上用于 Ajax 编程。它检索任何类型的数据，如 json、xml、文本等。它在后台请求数据并更新页面，而无需在客户端重新加载页面。XMLHTTPRequest 的一个对象用于客户端和服务器之间的异步通信。美元。ajax()方法用于创建 XMLHTTPRequest 对象。

美元。ajax()在后台执行以下步骤:

*   从后台发送数据。
*   从服务器接收数据。
*   更新网页而不重新加载页面。

下面我们将看到如何用$创建 XMLHTTPRequest 对象。ajax()方法:

**语法:**

```
var XHR = $.ajax({configs});
```

**示例:**

## Java Script 语言

```
// Example showing how XMLHTTPRequest object created
var XMLO = $.ajax({

    // Our sample URL to make the request
    url: 'https://jsonplaceholder.typicode.com/todos/1',

    // type of Request
    type: "GET"
});
```

现在，我们将看到我们可以从服务器检索的数据类型，以及我们为各自的数据类型准备的预处理器。

**数据类型:**这些是我们可以向服务器请求的数据类型。可用的数据类型有文本、xml、html、脚本、jsonp 和 json。基于这些数据类型，我们在将响应处理到 XMLHTTPRequest 对象的处理程序之前，先指定响应的预处理程序。以下是指定数据类型的预处理程序:

*   **文本:**如果数据类型为文本，则不会对响应应用预处理程序。可以通过 XMLHTTPRquest 对象 responseText 属性来访问。
*   **xml:** 对于 xml，预处理器 jQuery.parseXML 应用于响应，然后作为 XML 文档传递给处理程序。可以通过 XMLRequestHTTPRequest 对象的 responseXML 属性来访问它。
*   **html:** 在 html 数据类型的情况下，我们没有指定任何预处理器来响应。可以使用 responseText 属性访问它。
*   **字符串:**如果是脚本，首先运行脚本，然后以字符串的形式处理给处理程序。
*   **jsonp:** 在请求 jsong 的情况下，我们要指定$的 jsonpCallback 属性。ajax()方法。这将在将 json 对象传递给后续处理程序之前执行。
*   **json:** 在 json 的情况下，在将对象传递给处理程序之前，将响应解析为 jQuery.parseJSON。

**属性:** XMLHTTPRequest 对象有许多有用的类属性，这有助于灵活处理响应。XMLHTTPRequest 对象属性包括:

*   **readyState:** 该属性指示连接的状态。
*   **状态:**包含来自服务器的 http 响应代码。
*   **状态文本:**它包含来自服务器的 http 响应字符串。响应文本:它包含来自服务器的文本格式的响应。
*   **响应 XML:** 它包含来自服务器的响应 XML。
*   **GetalResponseHeaders:**此属性以字符串形式返回所有标题名称。
*   **getResponseHeader:** 取表头名称，返回表头的文本文本值。
*   **setReaquestHeader:** 用于设置请求头的值。
*   **overridemitemtype:**此属性用于设置 mime 类型，该类型用于将响应数据类型视为文本或 XML 类型。

**示例:**

## Java Script 语言

```
// Demonstrating Properties of XMLHTTPRequest object
<script>

var xmlObj = $.ajax({

    // Our sample url to make request
    url: 'https://jsonplaceholder.typicode.com/todos/1',

    // type of Request
    type: "GET"
});

xmlObj.always(function(a, b, c) {
    console.log(" # Status of request is : ", c.status);
    console.log(" # readyState of request is : ", c.readyState);
    console.log(" # statusText of request is : ", c.statusText);
    console.log(" # All Response Headers of request is : ",
           c.getAllResponseHeaders);
 });
</script>
```

**输出:**

```
# Status of request is : 200
# readyState of request is : 4
# statusText of request is : success
# All Response Headers of request is : function(){return h?p:null}
```

下面是 XMLHTTPRequest 对象的一些属性的示例:

**方法:**正如我们所知，XMLHTTPRequest 进行异步通信，结果它返回承诺。我们有许多 jQuery XMLHTTPRequest 对象的承诺方法。可用的承诺方法有:

*   **xmlObject.then():** 这个方法取两个回调函数 func1、func2 作为一个参数。成功解决承诺时调用 func1。请求失败时调用 func2。
*   **xmlObject.always():** 这个方法取单个回调函数。当请求被解析或拒绝时，此方法使处理程序调用。参数函数的调用总是与请求无关。
*   **xmlObject.then():** 这个方法接受单个回调函数。当我们的请求被解决时，这个方法将被调用。参数函数将随着请求的解决而运行。
*   **xmlObject.fail():** 此方法接受单个回调函数。当我们的请求被拒绝时，调用这个方法。在请求回调函数的引用被解析之后。

下面是 XMLHTTPRequest 对象的一些方法的例子:

**示例:**

## Java Script 语言

```
// Example demonstrating methods of XMLHTTPRequest
// object
<script>

var xmlObj = $.ajax({

    // Our sample url to make request
    url: 'https://jsonplaceholder.typicode.com/todos/1',

    // type of Request
    type: "GET",
});

xmlObj.then(function(){
    console.log(" #Then is resolved ");
});

xmlObj.fail(function(){
    console.log(" #Fail is resolved ");
});

xmlObj.always(function(){
    console.log(" #Always is resolved ");
});

xmlObj.done(function(){
    console.log(" #Done is resolved ");
});

</script>
```

**输出:**

```
#Always is resolved 
#Done is resolved 
#Then is resolved
```