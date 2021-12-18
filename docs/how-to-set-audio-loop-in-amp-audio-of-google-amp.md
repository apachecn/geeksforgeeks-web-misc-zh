# 如何在谷歌 amp 的 amp-audio 中设置音频循环？

> 原文:[https://www . geesforgeks . org/how-set-audio-in-amp-audio-of-Google-amp/](https://www.geeksforgeeks.org/how-to-set-audio-loop-in-amp-audio-of-google-amp/)

![](img/911091c569b094b6e54a226311a9df7b.png)

自 HTML5 发布以来，音频可以使用“音频”标签添加到网页中。以前，音频只能在网页上使用网页插件(如 Flash)播放。“音频”标签是一个内嵌元素，用于将声音文件嵌入到网页中。如果您想在网页上添加歌曲、采访等音频，这是一个非常有用的标签。要在放大器页面中嵌入音频，您必须使用放大器音频标签。

**设置:**要使用音频放大器，必须将音频放大器组件导入网页头部。

## 超文本标记语言

```
<script async custom-element="amp-audio" src=
"https://cdn.ampproject.org/v0/amp-audio-0.1.js">
</script>
```

为了使音频在音频文件结束时自动开始，我们在 amp-audio 中使用了循环属性。

**示例:**

## 超文本标记语言

```
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-audio</title>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the `amp-audio` component -->
    <script async custom-element="amp-audio" 
src="https://cdn.ampproject.org/v0/amp-audio-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-audio/index.html">

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
        }
    </style>
</head>

<body>
    <center>
        <h1>
            Geeks For Geeks
        </h1>
    </center>

    <amp-audio width="auto" height="50" 
        src="GeeksForGeeks.mp3" controls loop>

        <div fallback>
            Your browser doesn’t 
            support HTML5 audio...
        </div>
    </amp-audio>
</body>

</html>
```

**输出:**

![](img/2a64047a7b446184be291d33d127d5ce.png)