# 谷歌放大器-图像-灯箱

> 原文:[https://www . geesforgeks . org/Google-amp-amp-image-light box/](https://www.geeksforgeeks.org/google-amp-amp-image-lightbox/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

图片库是网站中的一个流行功能，通过 **amp-image-lightbox** 开发人员可以轻松地将灯箱效果添加到 AMP HTML 页面中，以激活 **amp-image-lightbox** 我们在 amp-image 组件上使用了 **on action** 。

**所需脚本:**将 amp-imag-lightbox 组件导入标题。

## 超文本标记语言

```
<script async custom-element="amp-image-lightbox" src=
"https://cdn.ampproject.org/v0/amp-image-lightbox-0.1.js">
</script>
```

**属性:**

*   **布局:**amp-image-light box 只支持 nodisplay 布局。
*   **id:** 指定灯箱组件的 id。这被 on 操作用作图像的目标。
*   **数据-关闭按钮-咏叹调标签:**用于设置关闭按钮的咏叹调标签。

**示例:**

## 超文本标记语言

```
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-image-lightbox</title>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the amp-image-lightbox 
        component in the header -->
    <script async custom-element="amp-image-lightbox"
src="https://cdn.ampproject.org/v0/amp-image-lightbox-0.1.js">
    </script>

    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-image-lightbox/index.html">

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
</head>

<body>
    <!-- The `amp-image-lightbox` is activated 
        using the `on` action on an `amp-img` 
        element-->
    <div>
        <amp-img on="tap:lightbox1" role="button"
            tabindex="0" src=
"https://pbs.twimg.com/profile_images/1304985167476523008/QNHrwL2q_400x400.jpg"
            layout="responsive"
            width="300" height="246">
        </amp-img>

        <amp-image-lightbox id="lightbox1" 
            layout="nodisplay">
        </amp-image-lightbox>
    </div>

    <!--It is even possible to show different 
        images in the same amp-image-lightbox-->
    <amp-img on="tap:lightbox1" role="button"
        tabindex="0" src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200817185016/gfg_complete_logo_2x-min.png"
        layout="responsive" width="600" 
        height="400">
    </amp-img>

    <!--The amp-image-lightbox also can 
        optionally display a caption for 
        the image at the bottom of the 
        viewport. -->
    <figure>
        <amp-img on="tap:lightbox1" role="button"
            tabindex="0" src=
"https://pbs.twimg.com/profile_images/1304985167476523008/QNHrwL2q_400x400.jpg"
            layout="responsive"
            width="300" height="246">
        </amp-img>

        <figcaption>geeksforgeeks</figcaption>
    </figure>
</body>

</html>
```

**输出:**

![](img/e4434f68beef3e1e85716b46e102062c.png)