# 网络应用编程接口|多区域顶级属性

> 原文:[https://www.geeksforgeeks.org/web-api-domrect-top-property/](https://www.geeksforgeeks.org/web-api-domrect-top-property/)

在网络应用编程接口中有一个**多区域**接口，它有一个属性 **top** ，这个属性给了我们多区域对象的顶部。返回 *y* 坐标值，如果高度为负，则返回 *y +高度*。

**语法:**

```htmlhtml
var recX = DOMRect.top;
```

**返回类型:**

```htmlhtml
Double value
```

**例 1:** 当高度为正时

```htmlhtml
<!DOCTYPE html>
<html>

<head>

    <title>
        DOMRect top property
    </title>

</head>

<body>
    <center>

        <h1 style="color:green;"> 
        GeeksForGeeks 
        </h1>

        <h2>DOMRect top property</h2>
        <button onclick="getDOMRect ();">
          Get top
      </button>
        <p id='DOMRect'></p>
    </center>

</body>

<script type="text/javascript">
    function getDOMRect() {
        var myDOMRect = new DOMRect(0, 0, 100, 100);
        var rectop = myDOMRect.top;

        document.getElementById(
          'DOMRect').innerHTML = rectop;

    }
</script>

</html>
```

**输出:**
**点击按钮前:**
![](img/d9720a70a4586ee4c15f79b6c8fa4fd4.png)

**点击按钮后:**
![](img/279b9dec6d11ed19aae56866ba76c0a2.png)

**例 2:** 当高度为负时

```htmlhtml
<!DOCTYPE html>
<html>

<head>

    <title>
        DOMRect top property
    </title>

</head>

<body>
    <center>

        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>DOMRect top property</h2>
        <button onclick="getDOMRect ();">
          Get top
      </button>
        <p id='DOMRect'></p>
    </center>

</body>

<script type="text/javascript">
    function getDOMRect() {
        var myDOMRect = new DOMRect(0, 0, 100, -100);
        var rectop = myDOMRect.top;

        document.getElementById('DOMRect').innerHTML = rectop;

    }
</script>

</html>
```

**输出:**
**点击按钮前:**
![](img/d9720a70a4586ee4c15f79b6c8fa4fd4.png)

**点击按钮后:**
![](img/ef562b6694d974b71f16362ff7455360.png)

**支持的浏览器:****顶级属性**支持的浏览器如下:

*   谷歌 Chrome
*   Safari 10.1
*   火狐浏览器
*   歌剧