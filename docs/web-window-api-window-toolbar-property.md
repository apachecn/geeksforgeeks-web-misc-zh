# 网页窗口 API |窗口工具栏属性

> 原文:[https://www . geesforgeks . org/web-window-API-window-toolbar-property/](https://www.geeksforgeeks.org/web-window-api-window-toolbar-property/)

在 HTML 中 **Window.toolbar** 属性返回*工具栏*的对象，可以查看*的可见性*。

**语法:**

```
objectReference = window.toolbar
```

**示例:**检查能见度

```
<!DOCTYPE html>
<html>

<head>

    <title>
        Window toolbar property
    </title>

    <script type="text/javascript">
        function getvisibility() {

            document.getElementById(
                    'visibility').innerHTML =
                window.toolbar.visible;

        }
    </script>

</head>

<body>
    <center>

        <h1 style="color:green;">  
                GeeksForGeeks  
            </h1>

        <h2>Window toolbar property</h2>
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
![](img/de9256e263c5dc6b0311fc0a790b7531.png)

**点击按钮时:**
![](img/4ad231dd6ae083dcc1fae9c288259932.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘 12
*   火狐浏览器
*   旅行队
*   歌剧