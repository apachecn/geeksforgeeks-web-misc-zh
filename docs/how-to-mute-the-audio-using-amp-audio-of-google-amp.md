# 如何使用谷歌 amp 的 amp-audio 将音频静音？

> 原文:[https://www . geeksforgeeks . org/如何使用谷歌音频放大器静音/](https://www.geeksforgeeks.org/how-to-mute-the-audio-using-amp-audio-of-google-amp/)

![](img/911091c569b094b6e54a226311a9df7b.png)

**简介:**自 HTML5 发布以来，可以使用“音频”标签将音频添加到网页中。以前，音频只能在网页上使用网页插件(如 Flash)播放。“音频”标签是一个内嵌元素，用于将声音文件嵌入到网页中。如果您想在网页上添加歌曲、采访等音频，这是一个非常有用的标签。要在放大器页面中嵌入音频，您必须使用放大器音频标签。

**设置:**要使用音频放大器，必须将音频放大器组件导入网页头部。

```html
<script async custom-element="amp-audio" src=
"https://cdn.ampproject.org/v0/amp-audio-0.1.js">
</script>
```

要使音频文件的音频静音，我们将使用 amp-audio 的**静音**属性。

**示例:**

```html
<!DOCTYPE html>
<html amp>

<head>
    <meta charset="utf-8" />
    <title>GeeksForGeeks | amp-audio</title>

    <script async 
        src="https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the `amp-audio` component -->
    <script async custom-element="amp-audio" 
src="https://cdn.ampproject.org/v0/amp-audio-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-audio/index.html" />

    <meta name="viewport" content="width=device-width,
            minimum-scale=1, initial-scale=1" />

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

    <style amp-custom>
        h1 {
            color: forestgreen;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeks For Geeks</h1>
    </center>

    <!-- The `amp-audio` component loads the
        audio resource specified by its `src` 
        attribute at a time determined by the
        runtime. `amp-audio` doesn't support 
        a responsive layout by default, but 
        you can achieve the same by combining 
        a `fixed` height with `width="auto"`.
        Because of muted audio will be muted 
        by default -->
    <amp-audio width="auto" height="50" 
        src="GeeksForGeeks.mp3" controls muted>

        <!-- This division will be displayed 
            when the file is not supported 
            by the browser -->
        <div fallback>
            Your browser doesn’t 
            support HTML5 audio...
        </div>
    </amp-audio>
</body>

</html>
```

**输出:**
![](img/4f9f0b7fe33f135a7ff10d266d6a3d78.png)