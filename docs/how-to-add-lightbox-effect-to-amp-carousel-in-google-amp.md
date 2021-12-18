# 如何在谷歌 amp 中给 amp-carousel 添加灯箱效果？

> 原文:[https://www . geeksforgeeks . org/如何将灯箱效果添加到 amp-carousel-in-google-amp/](https://www.geeksforgeeks.org/how-to-add-lightbox-effect-to-amp-carousel-in-google-amp/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

**amp-carousel** 用于在一个 AMP HTML 页面中制作一个图像转盘。在 AMP HTML 中，也可以使用 **amp-lightbox 图库**将**灯箱效果**添加到 amp-carousel 中，因为 amp-carousel 中只包含图像。

**所需脚本:**将放大器转盘组件导入标题。

## 超文本标记语言

```html
<script async custom-element="amp-carousel"
    src="https://cdn.ampproject.org/v0/amp-carousel-0.1.js">
</script>
```

**将 amp-lightbox-gallery 组件导入标题**

## 超文本标记语言

```html
<script async custom-element="amp-lightbox-gallery" 
        src="https://cdn.ampproject.org/v0/amp-lightbox-gallery-0.1.js">
</script>
```

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html ⚡>

<head>
    <meta charset="utf-8">
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-lightbox-gallery/index.html">

    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <script async custom-element="amp-carousel" 
src="https://cdn.ampproject.org/v0/amp-carousel-0.1.js">
    </script>

    <title>Google AMP amp-lightbox-gallery</title>

    <!-- Import the amp-lightbox-gallery 
        component in the header.  -->
    <script async custom-element="amp-lightbox-gallery"
src="https://cdn.ampproject.org/v0/amp-lightbox-gallery-0.1.js">
    </script>

    <style amp-boilerplate>
        body {
            -webkit-animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;

            -moz-animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;

            -ms-animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;

            animation: -amp-start 8s 
                steps(1, end) 0s 1 normal both;
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
        :root {
            --color-primary: #005AF0;
            --color-text-light: #fff;
            --space-1: .5rem;
            --space-2: 1rem;
        }
    </style>
</head>

<body>
    <amp-carousel lightbox width="1600" 
        height="1300" layout="responsive"
        type="slides">
        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201027070147/gg.jpg"
            width="200"
            height="100">
        </amp-img>

        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200817185016/gfg_complete_logo_2x-min.png"
            width="200" height="100">
        </amp-img>

        <amp-img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201027070147/gg.jpg"
            width="200"
            height="100">
        </amp-img>
    </amp-carousel>
</body>

</html>
```

**输出:**

![](img/ae3272ecde9c6785933040d5c657bb31.png)

代码输出

当我们单击图像时，会看到以下视图

![](img/50626dce89e8ab5bff3ad5e4109ff082.png)

当我们单击左上方的图库选项时，会看到以下视图

![](img/ce04cdfa05873b9f3557be2dbac78c87.png)