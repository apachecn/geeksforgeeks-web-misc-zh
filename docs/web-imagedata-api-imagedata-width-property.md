# Web ImageData API | ImageData . width 属性

> 原文:[https://www . geesforgeks . org/web-imagedata-API-imagedata-width-property/](https://www.geeksforgeeks.org/web-imagedata-api-imagedata-width-property/)

**ImageData.width 属性**用于返回 ImageData 对象的宽度属性。ImageData()用于创建给定大小的对象。

**语法:**

```htmlhtml
imageData.width
```

**示例:**

```htmlhtml
<!DOCTYPE html> 
<html> 

<head>
    <title>
        Web ImageData API | ImageData.width property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
        GeeksForGeeks 
    </h1> 

    <h2>ImageData width property</h2>

    <button onclick="getwidth ();">
        Get width
    </button>

    <p id='width'></p>

    <script type="text/javascript">
        function getwidth () {
        let imageData = new ImageData(100, 100);
            document.getElementById('width').innerHTML
                    = imageData.width;
        }
    </script> 
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/8f89b72f1349b6ec2540bc2cf5793992.png)
*   **点击按钮后:**
    ![](img/baa74771d0d78670b479d418521a0489.png)

**支持的浏览器:**imagedata . width 属性支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 9
*   Firefox 14
*   Safari 3.1
*   歌剧 9