# 跨产地资源共享(CORS)

> 原文:[https://www . geesforgeks . org/cross-origin-resource-sharing-CORS/](https://www.geeksforgeeks.org/cross-origin-resource-sharing-cors/)

CORS(跨来源资源共享)是一种机制，通过这种机制，网站的数据或任何其他资源可以在需要时有意共享给第三方网站。通常，出于安全目的，浏览器客户端会限制对驻留在第三方站点的资源的访问。

进行 HTTP 调用的客户端代码如下所示，

```html
function httpGetAction(urlLink)
{
    var xmlHttp = new XMLHttpRequest();
    xmlHttp.open( "GET", urlLink, false ); 
    xmlHttp.send();
    return xmlHttp.responseText;
}

```

这个原生 JavaScript 方法旨在通过 *GET* 方法对给定的链接 *urlLink* 进行 HTTP 调用，并从第三方资源返回响应文本。

默认情况下，浏览器会阻止对非父域(除您发出呼叫的域之外的域)的请求。如果您尝试这样做，控制台会抛出以下错误。,

```html
Failed to load https://contribute.geeksforgeeks.org/: No 'Access-Control-Allow-Origin' header is present on the requested resource. Origin 'https://www.google.com' is therefore not allowed access.

```

当然，在某些情况下，您需要访问第三方网站，如获取公共图像、进行非状态更改的应用编程接口调用或访问您自己拥有的其他域。必要时，有一些方法可以实现这一点。

人们可以从错误消息中得到一个想法，即请求的资源上不存在*访问控制允许源*头。这仅仅意味着你试图访问其资源的目标网站没有明确允许你从他们的网站获取资源。

这可以通过一个额外的 HTTP 头*访问控制允许源*来完成。此标头可以采用以下值。,

*   **访问-控制-允许-起源:【起源】**
    *示例:访问-控制-允许-起源:https://contribute.geeksforgeeks.org*
    这允许您专门允许一个网站访问您的资源。在这种情况下，https://contribute.geeksforgeeks.org 可以访问您的网络资源，因为它是明确允许的。
    这需要从请求客户端发送一个名为 **ORIGIN** 的附加报头，其中包含其主机名。这个源头与允许的源相匹配，并决定对资源的访问。
*   **访问控制-允许-来源:***
    示例:访问控制-允许-来源:*
    通配符(*)表示任何站点都可以访问您站点中的资源，显然这是不安全的。

    基于请求方法(获取/放入/放入/删除)和请求头,请求被分为两类

    1.  **简单请求**
    2.  **非简单/复杂请求**

        **简单请求**
        对于简单请求，CORS 的工作方式如下:

        1.  通过 **ORIGIN** 标题向第三方网站提出请求。
        2.  在目标位置，将**原点**值与允许的原点进行比较。
        3.  如果源是允许的，那么该资源被授予访问权，否则被拒绝。

        **复杂请求**
        对于复杂请求，CORS 的工作方式如下:

        1.  在发送实际请求之前，会向目标站点发送一个*预飞行*请求。
        2.  该*预飞行*请求通过**选项** HTTP 请求方法发送。
        3.  对飞行前请求的响应将包含允许的方法、允许的关于目标站点的起源细节。
        4.  在根据这个响应决定目标站点是否可以返回请求的信息之后，实际的 GET/POST 请求由浏览器发送。

        每当需要将资源共享给第三方站点时，该站点应特别加入白名单**访问控制允许来源:https://sitename.com**而不是通配符作为安全最佳实践。

        参考文献:https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS