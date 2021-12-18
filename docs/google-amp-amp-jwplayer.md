# 谷歌 AMP amp-jwplayer

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-jwplayer/](https://www.geeksforgeeks.org/google-amp-amp-jwplayer/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

要在 **AMP HTML** 中嵌入 jwplayer，有一个名为 **amp-jwplayer** 的组件，它显示一个云托管的 jwplayer。

**必需脚本:**将 amp-jwplayer 组件导入标题

## 超文本标记语言

```
<script async custom-element="amp-jwplayer" 
    src="https://cdn.ampproject.org/v0/amp-jwplayer-0.1.js">
</script>
```

**属性:**

*   **数据-玩家 id:** 在 JW 玩家的玩家区找到的字母数字 id。
*   **数据-播放列表-id/数据-媒体-id:** 在 JW 播放器的内容部分找到的字母数字播放列表-id 需要指定任何播放列表-ID 或媒体-ID。
*   **自动播放:**如果指定，视频一加载就开始播放。

**示例:**

## 超文本标记语言

```
<!doctype html>
<html ⚡>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-jwplayer</title>
    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Import the `amp-jwplayer` 
        component in the header.-->
    <script async custom-element="amp-jwplayer" 
src="https://cdn.ampproject.org/v0/amp-jwplayer-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-jwplayer/index.html">

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
</head>

<body>
    <amp-jwplayer data-media-id="BZ6tc0gy" 
        data-player-id="uoIbMPm3" 
        layout="responsive" width="16" 
        height="9">
    </amp-jwplayer>
</body>

</html>
```

**输出:**

![](img/d7ff3105e081d4c985be6e39d3e6f0cb.png)