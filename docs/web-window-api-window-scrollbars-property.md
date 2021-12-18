# 网页窗口 API |窗口滚动条属性

> 原文:[https://www . geesforgeks . org/web-window-API-window-scroll bar-property/](https://www.geeksforgeeks.org/web-window-api-window-scrollbars-property/)

在网络应用编程接口**窗口中，滚动条**属性返回*滚动条*的对象，我们可以检查*的可见性*。

**语法:**

```
objectReference = window.scrollbars
```

**例:检查能见度**

```
<!DOCTYPE html>
<html>

<head>
    <title>
        Window scrollbars property
    </title>

    <style>
        a:focus {
            background-color: magenta;
        }
    </style>

    <script type="text/javascript">
        function getvisibility() {
            document.getElementById('visibility').innerHTML =
              window.scrollbars.visible;
        }
    </script>

</head>

<body>
    <center>

        <h1 style="color:green;">  
                GeeksForGeeks  
            </h1>

        <h2>HTML Window scrollbars property</h2>
        <button onclick="getvisibility ();"
                id="btn">
          Check visibility
      </button>
        <p id='visibility'></p>
    </center>
</body>

</html>
```

**输出:**
**点击按钮:**
![](img/02e158e69c56768ca5b84f1d94f52153.png)

**点击按钮时:**
![](img/0a7add3a8e81876dfdf4f4551539390d.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘 12
*   火狐浏览器
*   旅行队
*   歌剧