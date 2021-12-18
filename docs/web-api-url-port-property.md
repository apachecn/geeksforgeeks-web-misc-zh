# 网络应用编程接口网址.端口属性

> 原文:[https://www.geeksforgeeks.org/web-api-url-port-property/](https://www.geeksforgeeks.org/web-api-url-port-property/)

Web API URL . port 属性用于获取包含 URL 端口号的 USVString。

**语法:**

```html
var str = URL.port

```

**返回值:**这个属性返回一个包含 URL 端口号的 USVString。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <button onclick="get()">
        Click on Me!
    </button>

    <script type="text/javascript">
        function get() {
            var url = new URL(
'https://www.geeksforgeeks.org:123/GeeksforGeeks');

            console.log("port of current URL is :",
                url.port);
        }
    </script>
</body>

</html>
```

**输出:**

![](img/f711d290e9ce964581bac3438532d27b.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <div id="abc"></div>

    <br><br>
    <button onclick="get()">
        Click on Me!
    </button>

    <script type="text/javascript">
        function get() {
            var url = new URL(
'https://www.geeksforgeeks.org:123/GeeksforGeeks');

            a = document.getElementById("abc");

            a.innerHTML = "port of current URL is : " 
                + url.port;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/b7f7ec4aefd6a1b75dc629e6fb3a9017.png)

**支持的浏览器:**

*   旅行队
*   歌剧
*   铬
*   边缘
*   火狐浏览器