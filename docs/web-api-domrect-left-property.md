# 网页 API | DOMRect 左属性

> 原文:[https://www . geesforgeks . org/web-API-DOM rect-left-property/](https://www.geeksforgeeks.org/web-api-domrect-left-property/)

在网络应用编程接口中有一个**多区域**接口，它有一个属性**左**，给我们多区域对象的左边。返回 *x* 坐标值，如果宽度为负，则返回 *x +宽度*。

**语法:**

```html
var recX = DOMRect.left;
```

**返回类型:**

```html
Double value
```

**例 1:** 当宽度为正时

```html
<!DOCTYPE html>
<html>

<head>

    <title>
        DOMRect left property
    </title>

</head>

<body>
    <center>

        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>DOMRect left property</h2>
        <button onclick="getDOMRect ();">
          Get left
      </button>
        <p id='DOMRect'></p>
    </center>

</body>

<script type="text/javascript">
    function getDOMRect() {
        var myDOMRect = new DOMRect(0, 0, 100, 100);
        var recleft = myDOMRect.left;

        document.getElementById(
          'DOMRect').innerHTML = recleft;

    }
</script>

</html>
```

**输出:**
**点击按钮前:**
![](img/59b51b3067d5866024371a6ad21e1213.png)

**点击按钮后:**
![](img/ce4c638a44e3707815e7c3f3103e686c.png)

**例 2:** 当宽度为负时

```html
<!DOCTYPE html>
<html>

<head>

    <title>
        DOMRect left property
    </title>

</head>

<body>
    <center>

        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>DOMRect left property</h2>
        <button onclick="getDOMRect ();">
          Get left
      </button>
        <p id='DOMRect'></p>
    </center>

</body>

<script type="text/javascript">
    function getDOMRect() {
        var myDOMRect = new DOMRect(0, 0, -100, 100);
        var recleft = myDOMRect.left;

        document.getElementById(
          'DOMRect').innerHTML = recleft;

    }
</script>

</html>
```

**输出:**
**点击按钮前:**
![](img/11bd7a4d30ebfada332cb5922c9c8b42.png)

**点击按钮后:**
![](img/593ae97350c7525006a2ce491554f550.png)

**支持的浏览器:****左属性**支持的浏览器如下:

*   谷歌 Chrome
*   Safari 10.1
*   火狐浏览器
*   歌剧