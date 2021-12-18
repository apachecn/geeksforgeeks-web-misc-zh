# 谷歌 AMP |简介

> 原文:[https://www.geeksforgeeks.org/google-amp-introduction/](https://www.geeksforgeeks.org/google-amp-introduction/)

![](img/da896cbc9c91eb6bafeb2ca1d138fca6.png)

**简介:** Google AMP 是一个开源的 HTML 框架，其中 AMP 是 Accelerated Mobile Pages 的缩写。它由谷歌创建，现在由 AMP 开源项目开发。它针对移动网页进行了优化，旨在帮助网页更快地加载。

要使用谷歌放大器，你必须事先了解 HTML，CSS 和 JavaScript。建议在开始学习谷歌 AMP 之前先学习前面提到的话题。

**官网:**[**https://amp.dev/**](https://amp.dev/)

****官方编码地:**[**https://playground.amp.dev/**](https://playground.amp.dev/)**

******为什么要用 AMP？******

****好吧，你网站的任何用户都希望网站加载快，另一方面，希望网站管理网站流量，谷歌放大器解决了这两个问题。它的编程方式不仅可以高速加载网站，还可以管理网站流量。****

******谷歌 AMP 的优势:******

*   ****谷歌 AMP 页面是轻量级的，加载速度也更快。****
*   ****谷歌优先考虑谷歌搜索中的放大器页面，从而获得更多用户。它们以轮播形式列在页面顶部。****
*   ****谷歌 AMP 页面反应灵敏，并能根据浏览器进行调整，因此对移动用户友好。****

******谷歌 AMP 的劣势:**众所周知，没有什么是纯粹的优势，谷歌 AMP 也是如此。它们具有以下缺点****

*   ****出版商必须为他们的页面维护两个版本 amp 和 non amp，这样可以增加存储空间。****
*   ****用户必须付出额外的努力将非 amp 页面转换为 amp。As amp 不支持自定义 JavaScript 或加载外部 JavaScript。****

******基本程序:**要用 AMP 编写程序，您必须在代码中使用< html amp >或< html ⚡ >标签，而不是< html >标签，因为当浏览器读取该标签时，它理解以下是 amp 代码。****

## ****超文本标记语言****

```
**<!-- Doctype declaration is required. -->
<!DOCTYPE html>

<!-- This tells everyone that this is an 
    AMP file, `<html amp>` works too. -->
<html amp>

<head>
    <!-- The charset definition must be the first 
       child of the `<head>` tag. -->
    <meta charset="utf-8">
    <title> Hello World</title>
    <!-- The AMP runtime must be loaded as the
       second child of the `<head>` tag.-->
    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- AMP HTML files require a canonical 
        link pointing to the regular HTML. 
        If no HTML version exists, it 
        should point to itself -->
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/introduction/hello_world/index.html">

    <!-- AMP HTML files require a viewport 
        declaration. It's recommended to 
        include initial-scale=1\. -->
    <meta name="viewport" content=
        "width=device-width,minimum-scale=1,
        initial-scale=1">

    <!-- CSS must be embedded inline. -->
    <style amp-custom>
        h1 {
            color: forestgreen;
        }
    </style>

    <style amp-boilerplate>
        body {
            -webkit-animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;
            -moz-animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;
            -ms-animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;
            animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both
        }

        @-webkit-keyframes -amp-start {
            from {
                visibility: hidden
            }

            to {
                visibility: visible
            }
        }

        @-moz-keyframes -amp-start {
            from {
                visibility: hidden
            }

            to {
                visibility: visible
            }
        }

        @-ms-keyframes -amp-start {
            from {
                visibility: hidden
            }

            to {
                visibility: visible
            }
        }

        @-o-keyframes -amp-start {
            from {
                visibility: hidden
            }

            to {
                visibility: visible
            }
        }

        @keyframes -amp-start {
            from {
                visibility: hidden
            }

            to {
                visibility: visible
            }
        }
    </style>
    <noscript>
        <style amp-boilerplate>
            body {
                -webkit-animation: none;
                -moz-animation: none;
                -ms-animation: none;
                animation: none
            }
        </style>
    </noscript>
</head>

<body>
    <h1>Hello World!</h1>
</body>

</html>**
```

******输出:******

****![](img/bb8723d2df912c1029d6dcd65361f5f0.png)

此输出适用于 iPhone 6/7/8****