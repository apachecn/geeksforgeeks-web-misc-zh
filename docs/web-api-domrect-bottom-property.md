# Web API | dorect 底层属性

> 原文:[https://www . geesforgeks . org/web-API-DOM rect-bottom-property/](https://www.geeksforgeeks.org/web-api-domrect-bottom-property/)

在 Web API 中有一个 **DOMRect** 接口，它有一个属性 **bottom** ，这个属性给出了 DOMRect 对象的 bottom。返回 *y +高度*坐标值，如果高度为负，则返回 *y* 。

**语法:**

```htmlhtml
var recX = DOMRect.bottom;
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
        DOMRect bottom property
    </title>

</head>

<body>
    <center>

        <h1 style="color:green;"> 
        GeeksForGeeks 
    </h1>

        <h2>DOMRect bottom property</h2>
        <button onclick="getDOMRect ();">
          Get bottom
      </button>
        <p id='DOMRect'></p>
    </center>

</body>

<script type="text/javascript">
    function getDOMRect() {
        var myDOMRect = new DOMRect(0, 0, 100, 100);
        var recbottom = myDOMRect.bottom;

        document.getElementById(
          'DOMRect').innerHTML = recbottom;

    }
</script>

</html>
```

**输出:**
**点击按钮前:**
![](img/c1bead75bd2f4f6c53c48cc7528ad63d.png)

**点击按钮后:**
![](img/09d89bfaa1e326b72254b08f84a8c79f.png)

**例 2:** 当高度为负时

```htmlhtml
<!DOCTYPE html>
<html>

<head>

    <title>
        DOMRect bottom property
    </title>

</head>

<body>
    <center>

        <h1 style="color:green;"> 
                GeeksForGeeks 
            </h1>

        <h2>DOMRect bottom property</h2>
        <button onclick="getDOMRect ();">Get bottom</button>
        <p id='DOMRect'></p>
    </center>

</body>

<script type="text/javascript">
    function getDOMRect() {
        var myDOMRect = new DOMRect(0, 0, 100, -100);
        var recbottom = myDOMRect.bottom;

        document.getElementById('DOMRect').innerHTML = recbottom;

    }
</script>

</html>
```

**输出:**
**点击按钮前:**
![](img/c1bead75bd2f4f6c53c48cc7528ad63d.png)

**点击按钮后:**
![](img/2ec52c39b5a30a3aef9ae44ddaf131f0.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Safari 10.1
*   火狐浏览器
*   歌剧