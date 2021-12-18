# 谷歌 AMP-AMP-video-iframe

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-video-iframe/](https://www.geeksforgeeks.org/google-amp-amp-video-iframe/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

**简介:** iframe 视频是**内嵌框架视频**嵌入在 HTML 页面中但是在 **AMP HTML** 中我们使用了一个名为 **amp-iframe-video** 的组件将视频嵌入到页面中使用 amp-iframe-video 我们可以使用 JavaScript 嵌入一个定制的视频播放器。

**所需脚本:**将 amp-video-iframe 组件导入标题。

```html
<script async custom-element="amp-video-iframe" src=
"https://cdn.ampproject.org/v0/amp-video-iframe-0.1.js">
</script>
```

**属性:**

*   **src:** 指定要嵌入的 iframe 视频的 URL 或路径。
*   **海报:**视频加载时指向一个图片网址。这是必需的属性。
*   **实现媒体会话:**如果 iframe 应该实现媒体会话应用编程接口，那么应该指定这个属性。
*   **实现旋转到全屏:**当 iframe 内部的文档独立实现旋转到全屏时，该属性为 True。
*   **自动播放:**如果设置了该属性，则视频一加载就开始播放。

**示例:**

```html
<!DOCTYPE html>
<html amp>

<head>
    <meta charset="utf-8" />
    <title>GeeksforGeeks amp-video-iframe</title>
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-video-iframe/index.html" />
    <meta name="viewport" content=
        "width=device-width,
        minimum-scale=1,
        initial-scale=1" />

    <!-- Include the `amp-video-iframe` component -->
    <script async custom-element="amp-video-iframe" 
src="https://cdn.ampproject.org/v0/amp-video-iframe-0.1.js">
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
                visibility: hidden;
            }

            to {
                visibility: visible;
            }
        }

        @-moz-keyframes -amp-start {
            from {
                visibility: hidden;
            }

            to {
                visibility: visible;
            }
        }

        @-ms-keyframes -amp-start {
            from {
                visibility: hidden;
            }

            to {
                visibility: visible;
            }
        }

        @-o-keyframes -amp-start {
            from {
                visibility: hidden;
            }

            to {
                visibility: visible;
            }
        }

        @keyframes -amp-start {
            from {
                visibility: hidden;
            }

            to {
                visibility: visible;
            }
        }
    </style>

    <noscript>
        <style amp-boilerplate>
            body {
                -webkit-animation: none;
                -moz-animation: none;
                -ms-animation: none;
                animation: none;
            }
        </style>
    </noscript>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>
</head>

<body>
    <amp-video-iframe id="myVideo" src=
"/static/samples/files/amp-video-iframe-videojs.html" 
        width="6000" height="405"
        layout="responsive" autoplay>

        <amp-img placeholder src=
"/static/samples/img/amp-video-iframe-sample-placeholder.jpg"
        layout="fill">
        </amp-img>
    </amp-video-iframe>
</body>

</html>
```

**输出:**
![](img/59a8e06ba7516907e3699632b508dee6.png)