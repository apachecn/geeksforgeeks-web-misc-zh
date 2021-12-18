# 如何在谷歌 amp 中用 amp-audio 设置自定义媒体通知？

> 原文:[https://www . geesforgeks . org/how-set-custom-media-notification-with-amp-audio-in-Google-amp/](https://www.geeksforgeeks.org/how-to-set-custom-media-notification-with-amp-audio-in-google-amp/)

![](img/911091c569b094b6e54a226311a9df7b.png)

自 HTML5 发布以来，音频可以使用“音频”标签添加到网页中。以前，音频只能在网页上使用网页插件(如 Flash)播放。“音频”标签是一个内嵌元素，用于将声音文件嵌入到网页中。如果您想在网页上添加歌曲、采访等音频，这是一个非常有用的标签。要在放大器页面中嵌入音频，您必须使用放大器音频标签。

**设置:**要使用音频放大器，必须将音频放大器组件导入网页头部。

## 超文本标记语言

```
<script async custom-element="amp-audio" src=
"https://cdn.ampproject.org/v0/amp-audio-0.1.js">
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

除了这些属性，还有一些可选属性可用于设置自定义媒体通知。

1.  **图稿:**用于设置音频文件的缩略图。
2.  **标题:**用于设置音频文件的标题。
3.  **相册:**用于设置相册的名称。
4.  **艺人:**用于设置艺人名称。

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

    <!--Import the `amp-audio` component-->
    <script async custom-element=
        "amp-audio" src=
"https://cdn.ampproject.org/v0/amp-audio-0.1.js">
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
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>
        Geeks For Geeks
    </h1>

    <amp-audio width="auto" height="50" 
        src="GeeksForGeeks.mp3" 
        artwork="gfg.png" 
        title="GeeksForGeeks"
        album="GeeksForGeeks" 
        artist="GeeksForGeeks" controls>

        <!-- It will display when the file 
         is not supported by the browser. -->
        <div fallback>
            Your browser doesn’t 
            support HTML5 audio...
        </div>
    </amp-audio>
</body>

</html>
```

**输出:**

![](img/afe956c2e405e79903c6d20eccf5f926.png)