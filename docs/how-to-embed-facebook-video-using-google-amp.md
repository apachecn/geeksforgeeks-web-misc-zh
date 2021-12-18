# 如何使用谷歌 AMP 嵌入脸书视频？

> 原文:[https://www . geesforgeks . org/如何嵌入-Facebook-video-use-Google-amp/](https://www.geeksforgeeks.org/how-to-embed-facebook-video-using-google-amp/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

在网站上添加脸书**视频和评论**现在是 amp 中一个受欢迎且有吸引力的功能。我们通过使用 **amp-facebook 组件**很容易做到这一点

**必需脚本:**使用以下脚本导入 **amp-facebook** 组件

## 超文本标记语言

```html
<script async custom-element="amp-facebook" src=
"https://cdn.ampproject.org/v0/amp-facebook-0.1.js">
</script>
```

**属性:**

1.  **data-href:** 脸书视频的网址是获取网址点击视频右上角选项点击前进设置并复制网址。
2.  **数据嵌入方式:**视频可以嵌入方式为–
    *   发布(默认)
    *   录像
3.  **数据-包含-评论-父项:**该属性可以设置为真或假默认为假如果设置为真，那么也可以看到评论回复的父项评论。
4.  **data-allowfullscreen:** 它将视频设置为全屏，默认值为无全屏。
5.  **数据区域设置:**默认区域设置为用户系统语言，您可以通过指定区域设置来更改。

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP embed facebook post</title>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the `amp-facebook` component -->
    <script async custom-element="amp-facebook" 
src="https://cdn.ampproject.org/v0/amp-facebook-0.1.js">
    </script>
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-facebook/index.html">

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
    <!--embedding fb video as video-->
    <amp-facebook width="552" height="310" 
        layout="responsive" data-embed-as="video"
        data-href=
"https://www.facebook.com/geeksforgeeks.org/videos/549199759161152/">
    </amp-facebook>
</body>

</html>
```

**输出**

![](img/534568f6561509a52eb980683cfe2a77.png)

如果视频作为**帖子**嵌入，输出将是:

![](img/674f630138c0d81e17bca6ba9298a470.png)