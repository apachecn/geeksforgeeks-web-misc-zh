# 如何在谷歌 amp 中使用 amp-bind 动态更改/更新图片？

> 原文:[https://www . geesforgeks . org/how-change-update-image-dynamic-using-amp-bind-in-Google-amp/](https://www.geeksforgeeks.org/how-to-change-update-image-dynamically-using-amp-bind-in-google-amp/)

![](img/911091c569b094b6e54a226311a9df7b.png)

有时，您希望为您的放大器页面添加自定义交互性，以使您的页面看起来更加用户友好和用户调用。虽然 AMP 的预建组件有限，所以做 amp-bind 就是为了克服这个问题。它帮助开发人员在不使用 AMP 的预构建组件的情况下为页面添加自定义交互性。您可以使用 amp-bind 在用户与页面交互时动态更改文本。

**设置:**要在页面中使用 amp-bind，您必须在文档的标题中导入其脚本。

## 超文本标记语言

```
<script async custom-element="amp-bind"
    src="https://cdn.ampproject.org/v0/amp-bind-0.1.js">
</script>
```

谷歌放大器的放大器绑定包括三个主要概念:

1.  **状态:**状态变量负责基于用户动作的页面更新。定义一个状态变量是非常重要的。
2.  **表达式:**它们就像是用来指代状态的 JavaScript 表达式。
3.  **绑定:**它们是一种特殊的属性，用于通过表达式将元素的属性链接到状态。

#### 示例:

## 超文本标记语言

```
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
        h1 {
            color: forestgreen;
            text-align: center;
        }

        .gfgNew {
            border: 5px solid crimson;
        }

        .gfgOld {
            border: 5px solid orange;
        }
    </style>
</head>

<body>
    <h1>
        Geeks For Geeks
    </h1>

    <amp-state id="gfg">
        <script type="application/json">
          {
            "new": {
              "imageUrl":
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png",
              "style": "gfgNew"
            },
            "old": {
              "imageUrl":
"https://media.geeksforgeeks.org/wp-content/uploads/20201026154131/logogfg.png",
              "style": "gfgOld"
            }
        }
      </script>
    </amp-state>

    <div style="padding: 1em;">

<p>
            Each logo has different border color...
        </p>

        <h4 ="'This is ' + logo + ' logo...'">
            This is old logo...
        </h4>
        <center>
            <amp-img width="200" height="200" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201026154131/logogfg.png"
                [src]="gfg[logo].imageUrl"
                class="gfgOld"
                [class]="gfg[logo].style">
            </amp-img>
            <br>
            <button on="tap:AMP.setState({logo: 'new'})">
                New Logo
            </button>
            <button on="tap:AMP.setState({logo: 'old'})">
                Old Logo
            </button>
        </center>
    </div>
</body>

</html>
```

#### 输出:

![](img/55a2d7891c08289a465071f106666dfb.png)

当点击“新徽标”按钮时，图像和边框颜色都发生了动态变化。当我们点击旧标志按钮图像和边框颜色改变到以前的组合。