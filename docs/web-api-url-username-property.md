# 网络应用编程接口网址.用户名属性

> 原文:[https://www . geesforgeks . org/web-API-URL-username-property/](https://www.geeksforgeeks.org/web-api-url-username-property/)

**网络应用编程接口网址.用户名属性**返回一个包含在网址域名之前指定的用户名的字符串

**语法:**

```html
var str = URL.username
```

**返回值:**这个属性返回一个 USVString，包含在 UR L 的域名前指定的用户名

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
'https://username:gfg@www.geeksforgeeks.org/href');

            console.log("username of current URL is :", 
                url.username);
        }
    </script>
</body>

</html>
```

**输出:**

![](img/c73e15100e91ab7cab5615c24c442b51.png)

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
'https://username:gfg@www.geeksforgeeks.org/href');

            a = document.getElementById("abc");

            a.innerHTML = "username of current URL is : "
                + url.username;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/20a4b35aac18cdbf9789942ed567df70.png)

**支持的浏览器:**

*   旅行队
*   歌剧
*   铬
*   边缘
*   火狐浏览器