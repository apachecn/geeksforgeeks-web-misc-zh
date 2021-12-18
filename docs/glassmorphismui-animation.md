# GlassmorphismUI 动画

> 原文:[https://www.geeksforgeeks.org/glassmorphismui-animation/](https://www.geeksforgeeks.org/glassmorphismui-animation/)

GlassmorphismUI 是一种用于设计网页元素、框架和屏幕的现代软 UI，也是一种相对较新的设计趋势，这几天获得了很大的流行，肯定会成为未来几天的下一个最大趋势。它的美学特征是极简而真实的用户界面，这是旧的新形态用户界面设计趋势的一种再发展。

是什么让它如此特别？

*   Use saturation color to make transparency pop up.
*   Transparent (frosted glass effect)
*   A subtle light border on a transparent object.

**HTML 代码:**以下是实现 Glassmorphism 的 HTML 代码。

## HTML

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>Glassmorphism</title>
    <link rel="stylesheet" href="index.css">
</head>

<body>
    <div class="rings">
        <div class="ring ring1"></div>
        <div class="ring ring2"></div>
    </div>

    <div class="container">
        <div class="card">
            <div class="logo">
                <img src=
"https://write.geeksforgeeks.org/static/media/Group%20210.08204759.svg"
                alt="Visa">
            </div>
            <div class="head">GlassmorphismUI</div>
            <div class="name">RBBANSAL</div>
            <div class="back"></div>
        </div>
    </div>
</body>

</html>
```