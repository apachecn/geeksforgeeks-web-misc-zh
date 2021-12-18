# 根据内容调整 iframe 的大小

> 原文:[https://www . geesforgeks . org/resize-an-iframe-based-on-content/](https://www.geeksforgeeks.org/resize-an-iframe-based-on-the-content/)

iframe HTML 元素通常用于插入其他来源的内容。需要调整大小的内容是使用 div 标签间接完成的。诀窍是用一个 div 标签开始，并包含在一个 iframe 标签中。现在用 CSS 提供 iframe。
**注意:**要打开源站点调整其内容大小，源站点必须列在同一个目录中。

**示例 1:** 下面是使用**内部 CSS** 调整内容大小的 HTML 代码的实现:-

```
<html>

<head>
    <style>
        body {
            background-color: LIGHTGREY;
        }

        #target {
            width: 300px;
            height: 200px;
            overflow-y: auto;
            overflow-x: auto;
            resize: both;
            position: relative;
            z-index: 2;
        }

        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>

</head>

<body>
    <div id="target">
        <iframe src="/tryit.php"></iframe>
    </div>
</body>

</html>
```

**输出:**
![](img/6ac5015431d2d614f4636c9acc47f618.png)

这里我们使用了一个内部样式表来将显示区域的尺寸固定为目标下的宽度和高度(以像素为单位)。CSS 溢出属性控制太大而无法放入区域的内容。

**示例 2:** 下面是 HTML 代码调整内容大小的实现，使用的是 Javascript:-
我们将使用 JavaScript *contentWindow 属性*即 iFrame 会根据内容自动调整其高度，不会出现滚动条。

*   我们在脚本标记中选择 iframe:
    var iframe = document . getelementbyid(" myIframe ")；
*   我们通过以下方式调整 iframe 高度加载事件:
    iframe.onload = function(){}

```
<html>

<head>
    <style>
        div {
            width: 50%;
        }
    </style>
</head>

<body>
    <iframe src="/tryit.php" id="target">
    </iframe>
    <script>
        var div = document.getElementById("target");
        div.onload = function() {
            div.style.height =
              div.contentWindow.document.body.scrollHeight + 'px';
        }
    </script>
</body>

</html>
```

**输出:**
![](img/1a1cd3ceb1e895a8c5d400d129cb9cf3.png)