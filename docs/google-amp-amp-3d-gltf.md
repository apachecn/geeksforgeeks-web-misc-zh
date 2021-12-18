# 谷歌 AMP-AMP-3d-gltf

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-3d-gltf/](https://www.geeksforgeeks.org/google-amp-amp-3d-gltf/)

![](img/da896cbc9c91eb6bafeb2ca1d138fca6.png)

早期我们甚至不能在网页中嵌入图像，但是随着网络开发的发展，我们能够做到这一点。现在有了这种开发流程，我们甚至可以在网站上嵌入 3D 图像。谷歌 amp 的 amp-3d-gltf 组件能够在我们的网站上显示 **glTF 格式**的 3d 模型。必须注意的是，您必须使用支持 **WebGL 的浏览器**来显示 3D 模型。

**设置:**要使用此标签，您必须在标题中导入 amp-3d-gltf 组件。

## 超文本标记语言

```
<script async custom-element="amp-3d-gltf" src=
    "https://cdn.ampproject.org/v0/amp-3d-gltf-0.1.js">
</script>
```

#### 例 1:

## 超文本标记语言

```
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-3d-gltf/index.html">

    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <title>Google AMP amp-3d-gltf</title>

    <!-- Import the `amp-3d-gltf` component
        in the header -->
    <script async custom-element="amp-3d-gltf" src=
"https://cdn.ampproject.org/v0/amp-3d-gltf-0.1.js">
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
            color: green;
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>
        Geeks For Geeks
    </h1>

    <!-- Embed 3d model via the `src`
        attribute. -->
    <amp-3d-gltf layout="fixed"
        width="320" height="240" src=
"https://preview.amp.dev/static/samples/glTF/DamagedHelmet.glb">
    </amp-3d-gltf>
</body>

</html>
```

#### **输出:**

![](img/1367f388a06912f9dad57de1e2bdbd53.png)

此输出适用于 iPhone 6/7/8

### <u>属性</u>:

<figure class="table">

| 

-你好。不，不。

 | 

属性名

 | 

描述

 |
| --- | --- | --- |
| 1. | 科学研究委员会 | 这是一个强制属性，因为它指定了要显示的 gltf 文件的位置。 |
| 2. | 希腊字母的第一个字母 | 这是一个可选属性，用于用布尔值指定画布背景的行为。 |
| 3. | 反混淆 | 它是一个可选属性，用于启用抗锯齿。默认值为假。

 |
| 4. | 清晰颜色 | 它是一个可选属性，用于用 CSS 颜色填充画布上的空闲空间。 |
| 5. | 最大像素比率 | 它是一个可选属性，用于设置像素比率渲染选项的上限。 |
| 6. | 自动旋转 | 它是一个可选属性，用于启用围绕模型中心的自动旋转。 |
| 7. | 启用缩放 | 它是一个可选属性，用于禁用或启用放大和缩小模型。 |

</figure>

#### 例 2:

## 超文本标记语言

```
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-3d-gltf/index.html">

    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <title>Google AMP amp-3d-gltf</title>

    <!-- Import the `amp-3d-gltf` component
        in the header -->
    <script async custom-element="amp-3d-gltf" src=
"https://cdn.ampproject.org/v0/amp-3d-gltf-0.1.js">
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
            color: green;
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>
        Geeks For Geeks
    </h1>

    <amp-3d-gltf layout="fixed" width="320"
        height="240" alpha="true"
        antialiasing="true" autorotate="true"
        enablezoom="false" src=
"https://preview.amp.dev/static/samples/glTF/DamagedHelmet.glb">
    </amp-3d-gltf>
</body>

</html>
```

#### **输出:**

![](img/1367f388a06912f9dad57de1e2bdbd53.png)

此输出适用于 iPhone 6/7/8