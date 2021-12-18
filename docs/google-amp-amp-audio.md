# 谷歌放大器音频

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-audio/](https://www.geeksforgeeks.org/google-amp-amp-audio/)

![](img/911091c569b094b6e54a226311a9df7b.png)

作为开发者，我们很多时候都想在网页中添加音频文件。以前，音频只能在网页上使用网页插件(如 Flash)播放。“音频”标签是一个内嵌元素，用于将声音文件嵌入到网页中。如果您想在网页上添加歌曲、采访等音频，这是一个非常有用的标签。要在放大器页面中嵌入音频，您必须使用放大器音频标签。

**设置:**要使用音频放大器，必须将音频放大器组件导入网页头部。

## 超文本标记语言

```html
<script async custom-element="amp-audio" 
    src="https://cdn.ampproject.org/v0/amp-audio-0.1.js">
</script>
```

**属性:**

1.  **宽度:**定义音频分割的宽度。
2.  **高度:**定义音频分割的高度。
3.  **src:** 定义要播放的音频文件的来源。
4.  **预加载:**设置 HTML 音频标签的预加载属性。
5.  **自动播放:**如果存在，加载页面时自动开始音频。
6.  **静音:**如果存在，默认将音量设置为 0。
7.  **循环:**如果存在，从开始到结束自动重复音频。

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-audio</title>

    <!-- Import the mandatory script -->
    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <script async custom-element="amp-audio" 
src="https://cdn.ampproject.org/v0/amp-audio-0.1.js">
    </script>

    <link rel="canonical" href="geeksforgeeks.html">

    <!-- It is mandatory meta tag. -->
    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <!-- Add the following boilerplate 
        tag as it is. -->
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

    <!-- This is custom amp-style -->
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

    <amp-audio width="auto" height="50" 
        src="GeeksForGeeks.mp3">

        <div fallback>
            Your browser doesn’t 
            support HTML5 audio
        </div>
    </amp-audio>
</body>

</html>
```

**输出:**

![](img/fd0bbdc9dd817dde5ae6bb0934543199.png)