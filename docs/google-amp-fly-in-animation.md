# 谷歌 AMP 飞进动画

> 原文:[https://www.geeksforgeeks.org/google-amp-fly-in-animation/](https://www.geeksforgeeks.org/google-amp-fly-in-animation/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

添加视觉效果的 **AMP HTML** 页面使用 **amp-fx-collection** 组件很容易，该组件提供了一系列效果集合，例如背景图像可以从屏幕的任何一侧进入框架的飞入，这是当今网页中非常流行和常见的效果。

**所需脚本:**将**外汇集合**导入表头

## 超文本标记语言

```html
<script async custom-element="amp-fx-collection" src=
"https://cdn.ampproject.org/v0/amp-fx-collection-0.1.js">
</script>
```

**属性:**

1.  **数据-持续时间:**指定动画经过一段时间后变为静态的持续时间。
2.  **数据放松:**在整个持续时间内改变动画速度。
3.  **数据-边距-开始/结束:**指定动画应该从视口边距的多少%开始。
4.  **数据-重复:**滚动后即使满载也要重复动画。
5.  **飞入底部/顶部:**元素从顶部或底部飞入。
6.  **左/右飞入:**元素从右侧或左侧飞入。

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-fx-collection</title>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import `amp-fx-collection` extension in header -->
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

    <!--Scroll triggered fly-in animation 
        with default attributes -->
    <amp-img amp-fx="fly-in-left" 
        width="1600" height="900" 
        layout="responsive" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201016212652/outputonlinepngtools.png">
    </amp-img>

    <!-- Scroll triggered fly-in-bottom animation 
        with default attributes. -->
    <amp-img amp-fx="fly-in-bottom" 
        width="1600" height="900" 
        layout="responsive" src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/xrgwkj7i-Edge-Computing.jpg">
    </amp-img>

    <!--Fly in animation that lasts longer by 
        specifying `data-duration="2000ms"-->
    <amp-img amp-fx="fly-in-left" 
        data-duration="2000ms" 
        width="1280" height="873" 
        layout="responsive" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200825214742/Top7CodeSharingWebsiteForDevelopers.png">
    </amp-img>

    <!-- Animation that takes place over 
        a larger distance by specifying 
        `data-fly-in-distance="50%"`.-->
    <amp-img amp-fx="fly-in-right" 
        data-fly-in-distance="50%" 
        width="1280" height="873" 
        layout="responsive" src=
"https://contribute.geeksforgeeks.org/wp-content/uploads/WorkingWithTextData-min.png">
    </amp-img>
</body>

</html>
```

**输出:**下图为静态。每一个上面都有飞进动画。

![](img/8cfba16d0146366125bdd63c3dbc5743.png)