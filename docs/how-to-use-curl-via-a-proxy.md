# 如何通过代理使用 cURL？

> 原文:[https://www.geeksforgeeks.org/how-to-use-curl-via-a-proxy/](https://www.geeksforgeeks.org/how-to-use-curl-via-a-proxy/)

本教程将展示在 PHP 的 cURL 函数中使用代理的方法。在本教程中，我们将通过选定的代理 IP 地址和端口发送我们的 HTTP 请求。

**为什么要用代理？**
有各种各样的原因让你可能想要使用一个带有 cURL 的代理:

1.  绕过区域过滤器和国家街区。
2.  使用代理 IP 地址允许您屏蔽或隐藏自己的 IP 地址。
3.  调试网络连接问题。

**使用带有 PHP 的 cURL 函数的代理:**要通过 cURL 向代理进行身份验证并发送 HTTP GET 请求，请按照下面给出的代码进行操作，并阅读注释中指定的说明。

**注意:**所有使用的凭证和链接都是随机的，仅用于演示目的。请使用您自己的代理、凭据和网址。

```html
<?php

// Initialize URL you that want to
// send a cURL proxy request to.
$desturl = 'http://example.net';

// The IP address of the proxy that
// you want to send your request
// through
$proxyipadd = '11.22.33.44';

// The port that the proxy is
// listening on
$proxyport = '1234';

// The username for authenticating
// with the proxy
$proxyuserid = 'testuser';

// The password for authenticating
// with the proxy
$proxypass = 'testpass';

// Initialize curl 
$ci = curl_init($url);

// Set curl attributes
curl_setopt($ci, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ci, CURLOPT_FOLLOWLOCATION, true);
curl_setopt($ci, CURLOPT_HTTPPROXYTUNNEL , 1);

// Set the proxy IP
curl_setopt($ci, CURLOPT_PROXY, $proxyipadd);

// Set the port
curl_setopt($ci, CURLOPT_PROXYPORT, $proxyport);

// Set the username and password
curl_setopt($ci, CURLOPT_PROXYUSERPWD, 
            "$proxyuserid:$proxypass");

// Execute the request
$result = curl_exec($ci);

// Check if any errors
if(curl_errno($ci)){
    throw new Exception(curl_error($ci));
}

// Print the result.
echo $result;
?>
```

在上面的代码中，我们连接到一个代理，该代理在发送一个简单的 GET 请求之前需要进行身份验证。如果代理不需要身份验证，那么您可以从代码中省略 CURLOPT _ PROXYUSERPWD 行。

**使用 curl 时可能会遇到的一些错误:**

*   **“无法连接到 11.22.33.44 端口 1234:超时”**这意味着 cURL 无法连接到所使用的代理 IP 地址和端口。确保 IP 和端口都正确，并检查代理是否正常工作。
*   **“未能连接到 11.22.33.44 端口 1234:连接被拒绝”**一旦您指定了不正确的端口号，即代理的 IP 地址正确，但它没有侦听指定端口上的请求，通常会出现此错误。还有一种可能是服务器启动了，但是运行代理的软件没有运行。
*   **“连接后收到来自代理的 HTTP 代码 407”**您简单使用的 CURLOPT _ PROXYUSERPWD 的用户名和密码组合是错误的。请确保用户名和密码是正确的，并使用冒号:字符分隔用户名和密码。