# 为什么过渡属性不适用于显示属性？

> 原文:[https://www . geesforgeks . org/why-transition-properties-not-work-with-display-properties/](https://www.geeksforgeeks.org/why-transition-properties-does-not-work-with-display-properties/)

当我们想对*显示使用过渡:无*到*显示:阻止*时，过渡属性不起作用。原因是，*显示:无*属性用于清除块，*显示:块*属性用于显示块。块不能部分显示。它可用或不可用。这就是过渡属性不起作用的原因。

所以对于动画，我们使用**关键帧** CSS。

```html
@keyframes animationname {keyframes-selector {css-styles;}}

```

**关键帧是做什么的？**
**@关键帧规则**指定动画的代码。当一组 CSS 样式更改为另一组 CSS 样式时，将创建动画并指定样式何时更改。它可以是百分比，也可以带有关键字“从”和“到”，这将相当于 0%和 100%。这里 0%是动画的开始，100%是动画的结束。

**哪个浏览器支持关键帧，该浏览器的前缀是什么？**

*   Chrome & safari=> -webkit-
*   Mozilla => -moz-
*   歌剧=> -o-

**代码片段:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        html,
        body {
            height: 100%;
            padding: 0;
            font: 20px/40px sans-serif;
        }

        h1 {
            padding: 20px;
        }

        div {
            width: 100%;
            background: pink;
            padding: 20px;
            display: none;
        }

        body:hover div {
            display: block;
            -webkit-animation: slide-down 2.3s ease-out;
            -moz-animation: slide-down 3.3s ease-out;
        }

        @-webkit-keyframes slide-down {
            0% {
                opacity: 0;
            }

            100% {
                opacity: 1;
            }
        }

        @-moz-keyframes slide-down {
            0% {
                opacity: 0;
            }

            100% {
                opacity: 1;
            }
        }
    </style>
</head>

<body>
    <h1>Hover me</h1>
    <div>Hello</div>
</body>

</html>
```

**Output:**
![](img/6dbaed7471e46b530acdd6c39ddc676c.png)