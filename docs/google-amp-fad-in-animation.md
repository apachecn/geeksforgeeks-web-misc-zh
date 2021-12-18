# 谷歌 AMP 时尚动画

> 原文:[https://www.geeksforgeeks.org/google-amp-fad-in-animation/](https://www.geeksforgeeks.org/google-amp-fad-in-animation/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

在 AMP HTML 页面中，使用 **amp-fx-collection** 组件很容易添加视觉效果，该组件提供了一系列效果集合，例如淡入，其中背景图像的不透明度不断增加，直至可见。

**所需脚本:**将 **amp-fx-collection** 导入表头。

## 超文本标记语言

```html
<script async custom-element="amp-fx-collection" src=
"https://cdn.ampproject.org/v0/amp-fx-collection-0.1.js">
</script>
```

**属性:**

1.  **数据-持续时间:**指定动画经过一段时间后变为静态的持续时间。
2.  **数据放松:**在整个持续时间内改变动画速度。
3.  d **数据边距-开始/结束:**指定动画应该从视图端口的哪个百分比的边距开始。
4.  **数据-重复:**滚动后即使满载也要重复动画。
5.  **淡入滚动:**当图像在视窗内滚动时，改变图像的不透明度。

**例:**

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP fad-in Animation</title>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import `amp-fx-collection` extension -->
    <script async custom-element="amp-fx-collection" 
src="https://cdn.ampproject.org/v0/amp-fx-collection-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-fx-collection/index.html">

    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

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

    <style amp-custom>
        .header {
            position: relative;
            overflow: hidden;
        }

        .header h1 {
            color: white;
            bottom: 10%;
            left: 10px;
            position: absolute;
            z-index: 1;
            font-size: 1.7em;
        }

        .title {
            background-color: black;
            color: white;
        }

        .parallax-image-window {
            overflow: hidden;
        }

        .parallax-image-window amp-img {
            margin-bottom: -20%;
        }
    </style>
</head>

<body>
    <!--fade-in with a duration-->
    <amp-img amp-fx="fade-in" 
        data-duration="2000ms" 
        width="1280" height="873" 
        layout="responsive" src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20201016212652/outputonlinepngtools.png">
    </amp-img>

    <!-- animation starts past 50% 
        of the viewport-->
    <amp-img amp-fx="fade-in" 
        data-margin-start="50%" 
        width="1280" height="873" 
        layout="responsive" src=
    "https://contribute.geeksforgeeks.org/wp-content/uploads/xrgwkj7i-Edge-Computing.jpg">
    </amp-img>

    <!-- Scroll dependent fade-in -->
    <amp-img amp-fx="fade-in-scroll" 
        width="1600" height="900" 
        layout="responsive" src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200825214742/Top7CodeSharingWebsiteForDevelopers.png">
    </amp-img>

    <!--  Custom start/end points -->
    <amp-img amp-fx="fade-in-scroll" 
        data-margin-start="20%" 
        data-margin-end="80%" 
        width="1600" height="900"
        layout="responsive" src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/WorkingWithTextData-min.png">
    </amp-img>
</body>

</html>
```

**输出:**

![](img/7a9fb63631b7f0f3ae1c6dab1864d24a.png)