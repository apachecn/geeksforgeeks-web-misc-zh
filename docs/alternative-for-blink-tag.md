# 替代<blink>标签</blink>

> 原文:[https://www.geeksforgeeks.org/alternative-for-blink-tag/](https://www.geeksforgeeks.org/alternative-for-blink-tag/)

在本文中，我们将学习 HTML 的眨眼标签的替代方法。闪烁标签没有任何替代的 HTML 标签，但是同样的效果可以在 CSS 的帮助下创建

**示例:**

在这个例子中，我们将使用 CSS 动画来获得眨眼效果

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="content-type"
              content="text/html; charset=utf-8" />
        <title>Geeksforgeeks</title>
        <style type="text/css">

            /* Minor Styling optional */
            .blinky{
                margin: auto;
                width: 200px;
                height: 200px;
                background: cyan;
                text-align: center;
                font-size: 24px;
                /* for support in Safari 4.0 - 8.0 */
                -webkit-animation:
                  1.5s linear infinite blinky-effect;

                animation: 1.5s linear infinite blinky-effect;
            }

            /* for support in Safari 4.0 - 8.0 */
            @-webkit-keyframes blinky-effect {
              0% {
                visibility: hidden;
              }
              50% {
                visibility: hidden;
              }
              100% {
                visibility: visible;
              }
            }

            @keyframes blinky-effect {
              0% {
                visibility: hidden;
              }
              50% {
                visibility: hidden;
              }
              100% {
                visibility: visible;
              }
            }
        </style>
    </head>
    <body>
        <div class="blinky">
            This div is going to blink
        </div>
    </body>
</html>
```