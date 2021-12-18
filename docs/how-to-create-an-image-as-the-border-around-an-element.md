# 如何创建一个图像作为元素周围的边框？

> 原文:[https://www . geeksforgeeks . org/如何围绕元素创建图像边框/](https://www.geeksforgeeks.org/how-to-create-an-image-as-the-border-around-an-element/)

任务是创建一个图像作为元素的边框。本文的方法是将图像创建为元素周围的边框 **[边框-图像源](https://www.geeksforgeeks.org/css-border-image-source-property/?ref=rp)** 属性用于指定要设置为元素边框的图像源。

**语法:**

```
border-image-source: url(image-path.png) | none | initial | inherit;
```

**示例:**

```
<!DOCTYPE html>
<html>
    <head>
        <title>
Create an image as the border around an element
        </title>
        <style>
             body
            {
                text - align : center;
            color:
                green;
            }

            .border1
            {
            border:
                10px solid transparent;
            padding:
                15px;
                border-image-source: url(
https:// media.geeksforgeeks.org/wp-content/uploads/border1-2.png);
                border-image-repeat: round;
                border-image-slice: 50;
                border-image-width: 20px;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>How to create an image 
          as the border around an element?</h2>
        <div class="border1">HeloloGEEKSFORGEEKS</div>
    </body>
</html>
```

**输出:**
![](img/3e6404169d4dfc54cf3617416a22d737.png)

**支持的浏览器如下:**

*   铬合金 15.0
*   Edge 11.0
*   Firefox 15.0
*   Opera 15.0
*   Safari 6.0