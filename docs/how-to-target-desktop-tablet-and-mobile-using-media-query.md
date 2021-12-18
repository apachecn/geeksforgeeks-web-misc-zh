# 如何使用 Media Query 定位桌面、平板和移动？

> 原文:[https://www . geeksforgeeks . org/如何瞄准桌面-平板电脑-移动-使用媒体-查询/](https://www.geeksforgeeks.org/how-to-target-desktop-tablet-and-mobile-using-media-query/)

媒体查询是一种流行的技术，能够将样式表分别传递给具有不同屏幕大小和分辨率的不同设备。它们用于在多个设备上自定义网站的外观。媒体查询由媒体类型组成，该媒体类型可以包含一个或多个表达式，这些表达式可以是真也可以是假。如果指定的媒体与显示文档的设备类型匹配，则查询结果为真。如果媒体查询为真，则应用样式表。
不同设备的屏幕分辨率如下:

*   手机(智能手机)最大宽度:480 像素
*   低分辨率平板电脑和 ipads 最大宽度:767 像素
*   平板电脑 Ipads 纵向模式最大宽度:1024px
*   桌面最大宽度:1280 像素
*   大尺寸(更大的屏幕)最大宽度:1281 像素或更大

**语法:**

```html
@media( media feature ) {
    // CSS Property
}
```

当某个条件为真时，它使用@media 规则来包含一个 CSS 属性块。某些媒体功能包括宽度(最大宽度和最小宽度)、纵横比、分辨率、方向等。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Media Query</title>

    <style>

        /* Media Query for Mobile Devices */
        @media (max-width: 480px) {
            body {
                background-color: red;
            }
        }

        /* Media Query for low resolution  Tablets, Ipads */
        @media (min-width: 481px) and (max-width: 767px) {
            body {
                background-color: yellow;
            }
        }

        /* Media Query for Tablets Ipads portrait mode */
        @media (min-width: 768px) and (max-width: 1024px){
            body {
                background-color: blue;
            }
        }

        /* Media Query for Laptops and Desktops */
        @media (min-width: 1025px) and (max-width: 1280px){
            body {
                background-color: green;
            }
        }

        /* Media Query for Large screens */
        @media (min-width: 1281px) {
            body {
                background-color: white;
            }
        }
    </style>
</head>

<body style = "text-align:center;">
    <h1>GeeksforGeeks</h1>
    <h2>Media Query</h2>
</body>

</html>                   
```

**输出:**

*   **移动设备上的输出:**

![](img/9c14d20fdd5b3bc17220196425c731b3.png)

*   **在低分辨率平板电脑、Ipads 上输出:**

![](img/d2526108556312d2c9a4ac16dfd44292.png)

*   **平板电脑 Ipads 人像模式输出:**

![](img/f0174e497e453986452ab59729cacc8c.png)

*   **笔记本电脑和台式机上的输出:**

![](img/7327aaa214b187f124f878f306228f87.png)

*   **大屏幕输出:**

![](img/8df092fb78860d165ef628f1a1ed51d8.png)

**注意:**更改屏幕大小，查看媒体查询效果。
**支持的浏览器:**媒体查询支持的浏览器如下:

*   谷歌 Chrome 21.0
*   Internet Explorer 9.0
*   Mozilla Firefox 3.5
*   Safari 4.0
*   Opera 9.0