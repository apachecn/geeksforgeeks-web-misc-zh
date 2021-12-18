# 谷歌 AMP 字体

> 原文:[https://www.geeksforgeeks.org/google-amp-amp-font/](https://www.geeksforgeeks.org/google-amp-amp-font/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

**amp-font** 用于检查字体是否加载到 **AMP HTML** 页面中。

**必需脚本:**将 amp-font 导入标题。

## 超文本标记语言

```
<script async custom-element="amp-font"
    src="https://cdn.ampproject.org/v0/amp-font-0.1.js">
</script>
```

如果字体不可用，我们使用以下样式以红色显示字体。

## 超文本标记语言

```
<style amp-custom>
    :root {
        --color-error: #B00020;
        --color-primary: #005AF0;
    }

    @font-face {
        font-family: 'UnavailableFont';
        font-style: normal;
        font-weight: 400;
        src: url(fonts/UnavailableFont.ttf) format('truetype');
    }

    @font-face {
        font-family: 'Comic AMP';
        font-style: normal;
        font-weight: 400;
        src: local('Comic AMP'),
            url(/static/samples/fonts/ComicAMP.ttf) 
            format('truetype');
    }

    @font-face {
        font-family: 'Comic AMP 2';
        font-style: normal;
        font-weight: 400;
        src: local('Comic AMP'), 
            url(/static/samples/fonts/ComicAMP2.ttf) 
            format('truetype');
    }

    .unavailable-font-loaded .unavailable-font {
        font-family: 'UnavailableFont';
    }

    .comicamp-loaded .comicamp {
        font-family: 'Comic AMP';
    }

    .comicamp2-loaded .comicamp2 {
        font-family: 'Comic AMP 2';
    }

    .comicamp-loading .comicamp,
    .comicamp2-loading .comicamp2,
    .unavailable-font-loading .unavailable-font {
        color: var(--color-primary);
    }

    .comicamp-missing .comicamp,
    .comicamp2-missing .comicamp2,
    .unavailable-font-missing .unavailable-font {
        color: var(--color-error);
    }
</style>
```

### 属性:

1.  **字体-家族:**指定家族的字体示例:futura、georgia 等。
2.  **布局:**定义特定布局此属性必须设置为 nodisplay。

**示例:**这里，第二个字体系列被设置为 abc，因为名称 abc 没有系列，所以它以红色显示。

## 超文本标记语言

```
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-font</title>

    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <script async custom-element="amp-font" 
src="https://cdn.ampproject.org/v0/amp-font-0.1.js">
    </script>

    <link rel="canonical" href=
"https://amp.dev/documentation/examples/components/amp-font/index.html">

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
        :root {
            --color-error: #B00020;
            --color-primary: #005AF0;
        }

        @font-face {
            font-family: 'UnavailableFont';
            font-style: normal;
            font-weight: 400;
            src: url(fonts/UnavailableFont.ttf) 
                    format('truetype');
        }

        @font-face {
            font-family: 'Comic AMP';
            font-style: normal;
            font-weight: 400;
            src: local('Comic AMP'), 
                url(/static/samples/fonts/ComicAMP.ttf) 
                format('truetype');
        }

        @font-face {
            font-family: 'Comic AMP 2';
            font-style: normal;
            font-weight: 400;
            src: local('Comic AMP'), 
                url(/static/samples/fonts/ComicAMP2.ttf)
                format('truetype');
        }

        .unavailable-font-loaded .unavailable-font {
            font-family: 'UnavailableFont';
        }

        .comicamp-loaded .comicamp {
            font-family: 'Comic AMP';
        }

        .comicamp2-loaded .comicamp2 {
            font-family: 'Comic AMP 2';
        }

        .comicamp-loading .comicamp,
        .comicamp2-loading .comicamp2,
        .unavailable-font-loading .unavailable-font {
            color: var(--color-primary);
        }

        .comicamp-missing .comicamp,
        .comicamp2-missing .comicamp2,
        .unavailable-font-missing .unavailable-font {
            color: var(--color-error);
        }
    </style>
</head>

<body>
    <!-- ## Existing font -->

    <div>
        <amp-font layout="nodisplay" 
            font-family="georgia" timeout="2000" 
            on-error-remove-class="comicamp-loading"
            on-error-add-class="comicamp-missing" 
            on-load-remove-class="comicamp-loading"
            on-load-add-class="comicamp-loaded">
        </amp-font>

        <p class="comicamp">
            geeks for geeks
        </p>

    </div>

    <!-- ## Unavailable font  -->
    <div>
        <amp-font layout="nodisplay" font-family="abc" 
            timeout="2000" on-error-remove-class=
            "unavailable-font-loading"
            on-error-add-class="unavailable-font-missing" 
            on-load-remove-class="unavailable-font-loading"
            on-load-add-class="unavailable-font-loaded">
        </amp-font>

        <p class="unavailable-font">
            geeks for geeks
        </p>

    </div>
</body>

</html>
```

**输出:**

![](img/c4af5ada0f226551c84cedcc8e4ded71.png)