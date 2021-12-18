# 使用 AOS

在鼠标滚动时激活一个 div

> 原文:[https://www . geesforgeks . org/animate-a-div-on-mouse-scroll-using-AOS/](https://www.geeksforgeeks.org/animate-a-div-on-mouse-scroll-using-aos/)

[AOS](https://github.com/michalsnik/aos) 是一个小程序库，当你滚动页面时，它可以为页面上的元素设置动画。

AOS 允许您在向下和向上滚动时制作元素动画。如果您向后滚动到顶部，元素将动画化到其先前的状态，并准备好再次动画化，如果您向下滚动。

**安装:**安装 AOS 很简单:

*   在网页的标题标签中添加下面的标签。

> <link rel="”stylesheet”" href="”https://unpkg.com/aos@next/dist/aos.css”">

*   在关闭标签之前添加脚本，并初始化 AOS:

> <【脚本】>
> 至. init()；
> </脚本>

就是这样，现在你已经成功地在你的 webapp 中安装了 aos。

#### 设置动画使用**数据-aos** 属性:

```htmlhtml
<div data-aos="fade-in"></div>
```

**示例:**下面是演示动画效果的示例。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "https://unpkg.com/aos@next/dist/aos.css" />

    <script src=
        "https://unpkg.com/aos@next/dist/aos.js">
    </script>

    <script>
        AOS.init();
    </script>

    <style>
        body {
            padding: 100vh 0;
        }

        div {
            margin: 0 auto;
            color: #fff;
            padding: 100px;
            font-size: 25px;
            width: 50%;
            background-color: green;
        }
    </style>
</head>

<body>
    <div data-aos="zoom-in">
        Geeks for geeks
    </div>
</body>

</html>
```

**输出:**

![](img/44d863c95b262816954e5047ad70cfc4.png)