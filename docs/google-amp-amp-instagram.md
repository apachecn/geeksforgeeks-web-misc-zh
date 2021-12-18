# 谷歌 AMP-AMP-insta gram

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-instagram/](https://www.geeksforgeeks.org/google-amp-amp-instagram/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

添加社交媒体帖子、评论是开发者倾向于添加的网站中有吸引力的功能，Instagram 是 2020 年流行的社交媒体网络之一，嵌入 Instagram 帖子在吸引观众时会派上用场。在 AMP HTML 中，我们可以通过使用 amp-instagram 来做到这一点。

**必需脚本:**将 amp-instagram 头导入到头中。

## 超文本标记语言

```
<script async custom-element="amp-instagram" 
    src="https://cdn.ampproject.org/v0/amp-instagram-0.1.js">
</script>
```

**属性:**

*   **数据-短码:**在每个 Instagram 照片 URL 中找到。以下链接中带下划线的粗体部分示例 https://www.instagram.com/p/**<u>cezqc-osEP</u>**/
*   **数据标题:**将调整到包括标题在内的原始高度。

**示例:**

## 超文本标记语言

```
<!doctype html>
<html ⚡>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-instagram</title>

    <script async src="https://cdn.ampproject.org/v0.js"></script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-instagram/index.html">

    <!-- Import the amp-instagram component 
        in the header -->    
    <script async custom-element="amp-instagram" 
src="https://cdn.ampproject.org/v0/amp-instagram-0.1.js">
    </script>

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
    <amp-instagram data-shortcode="CEZCQC-osEP" 
        width="1" height="1" layout="responsive">
    </amp-instagram>

    <!-- You can include captions with the 
        `data-captioned` attribute -->
    <amp-instagram data-shortcode="CEQ17teInqd"
        data-captioned width="1" height="1" 
        layout="responsive">
    </amp-instagram>
</body>

</html>
```

### 输出:

![](img/bc9db42e31d1aa531ef994ca472bc06e.png) ![](img/4b9c031a45871a01974fa40be34a8603.png)