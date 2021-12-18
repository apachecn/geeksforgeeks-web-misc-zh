# 如何用谷歌 AMP 制作简易网站？

> 原文:[https://www . geeksforgeeks . org/如何制作简单网站-使用-google-amp/](https://www.geeksforgeeks.org/how-to-make-simple-website-using-google-amp/)

![](img/da896cbc9c91eb6bafeb2ca1d138fca6.png)

谷歌 AMP 是一个很好的方法，使移动网站具有快速加载功能。它完全建立在最新的网络技术上。谷歌 AMP 通过限制 HTML、CSS 和 JavaScript 的某些部分以尽可能好的速度加载网页而不失美观，达到了这样的速度。这些限制导致自定义元素和规则的定义。

### 规则:

*   doctype 声明是必需的。

```html
<!doctype html>

```

*   设计者必须使用或代替或标准的标签来启动放大器页面代码。这告诉浏览器该文件是一个放大器文件。

```html
<html amp>

```

*   HEAD 标签必须包含以下链接和代码，才能使 AMP 代码工作。

## 超文本标记语言

```html
<!-- The charset definition must be the
    first child of the `<head>` tag. -->
<meta charset="utf-8">
<!-- The AMP runtime must be loaded as
    the second child of the `<head>` tag.-->

<script async src=
    "https://cdn.ampproject.org/v0.js">
</script>
<!-- AMP HTML files require a canonical
    link pointing to the regular HTML.
    If no HTML version exists, it should
    point to itself -->

<link rel="canonical" href=
"https://amp.dev/documentation/examples/introduction/hello_world/index.html">

<!-- AMP HTML files require a viewport declaration.
It's recommended to include initial-scale=1 -->
<meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

<!-- The AMP boilerplate -->
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
```

*   通过在 AMP CSS 标记中编写 CSS，可以在 AMP 页面中添加自定义 CSS，如下所示:

## 超文本标记语言

```html
<style amp-custom>
  <!-- Custom CSS -->
</style>
```

可以注意到，大多数的 HTML 标签可以直接用在 AMP 页面中，而一些像 img 这样的标签被重新定义的 AMP 标签所取代。

**示例:**

## 超文本标记语言

```html
<!-- Doctype declaration is required. -->
<!doctype html>

<!-- This tells the browser that this is
    an AMP file. `<html ⚡>` works too. -->
<html amp>

<head>
    <!-- The charset definition must be the
        first child of the `<head>` tag. -->
    <meta charset="utf-8">

    <!-- The AMP runtime must be loaded as the
       second child of the `<head>` tag.-->
    <script async src=
        "https://cdn.ampproject.org/v0.js">
    </script>

    <!-- AMP HTML files require a canonical
        link pointing to the regular HTML.
        If no HTML version exists, it should
        point to itself -->
    <link rel="canonical" href=
"https://amp.dev/documentation/examples/introduction/hello_world/index.html">

    <!-- AMP HTML files require a viewport
        declaration. It's recommended to
        include initial-scale=1 -->
    <meta name="viewport" content=
"width=device-width,minimum-scale=1,initial-scale=1">

    <!-- CSS must be embedded inline -->
    <style amp-custom>
        h1 {
            color: forestgreen;
        }
    </style>

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
    <h1>
        Hello World!<br>Welcome to
        GeeksForGeeks
    </h1>
</body>

</html>
```

**输出:**

![](img/3bc19e4660a7f8f918ffae3e7b6e987a.png)

此输出适用于 iPhone 6/7/8