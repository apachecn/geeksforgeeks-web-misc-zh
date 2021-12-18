# 如何在谷歌 amp 中使用 amp-bind 动态改变/更新图片大小？

> 原文:[https://www . geesforgeks . org/how-change-update-image-size-dynamic-use-amp-bind-in-Google-amp/](https://www.geeksforgeeks.org/how-to-change-update-image-size-dynamically-using-amp-bind-in-google-amp/)

![](img/911091c569b094b6e54a226311a9df7b.png)

有时，您希望为您的放大器页面添加自定义交互性，以使您的页面看起来更加用户友好和用户调用。虽然 AMP 的预建组件有限，所以做 amp-bind 就是为了克服这个问题。它帮助开发人员在不使用 AMP 的预构建组件的情况下为页面添加自定义交互性。您可以使用 amp-bind 在用户与页面交互时动态更改文本。

**设置:**要在页面中使用 amp-bind，您必须在文档的标题中导入其脚本。

## 超文本标记语言

```html
<script async custom-element="amp-bind" src=
"https://cdn.ampproject.org/v0/amp-bind-0.1.js">
</script>
```

谷歌放大器的放大器绑定包括三个主要概念:

1.  **状态:**状态变量负责基于用户动作的页面更新。定义一个状态变量是非常重要的。
2.  **表达式:**它们就像是用来指代状态的 JavaScript 表达式。
3.  **绑定:**它们是一种特殊的属性，用于通过表达式将元素的属性链接到状态。

为了动态改变图像的大小，我们将使用 AMP.setState()属性。该属性有助于动态更改其他字段的属性。

#### 示例:

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-bind</title>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-bind/index.html">

    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import amp-bind component in header -->
    <script async custom-element="amp-bind" 
src="https://cdn.ampproject.org/v0/amp-bind-0.1.js">
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
        h1 {
            color: forestgreen;
        }
    </style>
</head>

<body>
    <center>
        <h1>
            Geeks For Geeks
        </h1>

        <div style="padding: 1em;">

            <amp-img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png" 
                width="100"
                [width]="update.width" height="100" 
                [height]="update.height">
            </amp-img>
            <br>
            <button on="tap:AMP.setState({
                        update: {
                          width: 200,
                          height: 200
                        }
                      })">
                Change size
            </button>
        </div>
    </center>
</body>

</html>
```

**输出:**

![](img/002457d9f2210a0200b7b7abaa06586d.png)