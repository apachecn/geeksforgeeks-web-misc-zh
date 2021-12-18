# 谷歌放大器转盘

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-carousel/](https://www.geeksforgeeks.org/google-amp-amp-carousel/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

**amp-carousel 组件**用于在 **AMP HTML** 中沿水平轴制作图像/内容转盘。旋转木马是一系列图像中的图像幻灯片。

**所需脚本:**导入标题中的**放大器转盘**组件。

## 超文本标记语言

```html
<script async custom-element="amp-carousel" src=
"https://cdn.ampproject.org/v0/amp-carousel-0.1.js">
</script>
```

**属性:**

1.  **类型:**指定转盘的类型。默认情况下，type 设置为 carousel(所有幻灯片水平滚动，幻灯片在这里可以有不同的 CSS)。它也可以设置为幻灯片(一次显示一张幻灯片)。
2.  **控制:显示左右箭头供用户导航。**
3.  **自动播放:**当我们使用这个属性时，它会自己移动转盘。
4.  **循环:**使用循环属性进行循环，即在最后一张幻灯片中有右控制，在第一张幻灯片中有左控制。
5.  **延时:**下一张幻灯片显示时长默认设置为 5000 毫秒，延时不能小于 1000 毫秒。
6.  **幻灯片:**用于指定应该先走哪张幻灯片。

**示例 1:** 使用 type="slides "将图像列表显示为幻灯片。

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>amp-carousel</title>
    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the carousel component in the header. -->
    <script async custom-element="amp-carousel"
        src=
"https://cdn.ampproject.org/v0/amp-carousel-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-carousel/index.html">

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
</head>

<body>
    <amp-carousel width="400" height="300" 
            layout="responsive" type="slides">
        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png"
            width="400" height="300"
            layout="responsive">
        </amp-img>

        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234528/colorize1.png"
            width="400" height="300"
            layout="responsive">
        </amp-img>

        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234815/colorize2.png"
            width="400" height="300"
            layout="responsive">
        </amp-img>
    </amp-carousel>
</body>

</html>
```

**输出:**

![](img/0647a5061fb05a6e289fb49124e8c24b.png)

**例 2:** 使用延迟 3000 毫秒的自动播放属性。

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>amp-carousel</title>
    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the carousel component 
        in the header. -->
    <script async custom-element="amp-carousel"
        src=
"https://cdn.ampproject.org/v0/amp-carousel-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-carousel/index.html">

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
</head>

<body>
    <amp-carousel width="400" height="300"
            layout="responsive" type="slides"
            autoplay delay="3000">
        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png"
            width="400" height="300"
            layout="responsive">
        </amp-img>

        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234528/colorize1.png"
            width="400" height="300"
            layout="responsive">
        </amp-img>

        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234815/colorize2.png"
            width="400" height="300"
            layout="responsive">
        </amp-img>
    </amp-carousel>
</body>

</html>
```

**输出:**

![](img/030eaaf310444ccf7a4fd8489f07d4aa.png)