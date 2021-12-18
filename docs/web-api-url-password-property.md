# 网页应用编程接口网址.密码属性

> 原文:[https://www . geesforgeks . org/web-API-URL-password-property/](https://www.geeksforgeeks.org/web-api-url-password-property/)

**网络应用编程接口网址.密码属性**返回一个包含网址域名前指定密码的 USVString。USVString 是 Unicode 标量值的序列。

**语法:**

```html
var str = URL.password
```

**返回值:**该属性返回一个 USVString，包含在 UR L 的域名前指定的密码

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <button onclick="get()" x='15' y='30'>
        Click on Me!
    </button>

    <script type="text/javascript">
        function get() {
            var url = new URL(
'https://password:gfg@www.geeksforgeeks.org/href#ExampleHash');

            console.log("password of current URL is :",
                url.password);
        }
    </script>
</body>

</html>
```

**输出:**

![](img/f3f3a890a2a383ed569378ef7dc81948.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <div id="abc"></div>

    <button onclick="get()" x='15' y='30'>
        Click on Me!
    </button>

    <script type="text/javascript">
        function get() {
            var url = new URL(
'https://password:gfg@www.geeksforgeeks.org/href#ExampleHash');

            a = document.getElementById("abc");
            a.innerHTML = "password of current URL is : "
                + url.password;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/ba042502ea75330ed38974be35194667.png)

**支持的浏览器:**

*   旅行队
*   歌剧
*   铬
*   边缘
*   火狐浏览器