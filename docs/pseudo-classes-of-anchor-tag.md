# 锚标签的伪类

> 原文:[https://www.geeksforgeeks.org/pseudo-classes-of-anchor-tag/](https://www.geeksforgeeks.org/pseudo-classes-of-anchor-tag/)

[伪类](https://www.geeksforgeeks.org/css-pseudo-classes/)是描述链接状态的一种方式，或者它赋予锚标签 [<一个>](https://www.geeksforgeeks.org/html-a-tag/) 效果。用户可以显示一个链接，无论该链接以前是否被他们访问过或者处于运行状态，

我们也可以在鼠标在上面时改变光标符号。它有以下语法。

**语法:**

```htmlhtml
selector:pseudo-class { property: value; }
```

基本上有四种样式表示链接的状态。

**1。链接:**它代表一个特定的单词或句子作为链接。它是蓝色的，基本上表明它是一个未访问的链接，或者用户从未点击过该链接。

**2。已访问的链接:**这表明该特定链接之前已经被用户访问过。在本例中，已访问的链接显示为红色。

**3。悬停:**当鼠标在链接上时。有助于在链接中抓住读者的注意力。它被显示为绿色。当鼠标在链接上时，链接的颜色将变为绿色。

**4。活动:**点击链接后，链接状态变为活动状态，表示链接到该链接的页面正在加载。在一段时间内，它会保持活动状态，直到页面完全加载。

活动状态显示为橙色。例如，让我们用一个例子来理解这一点。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <title>Pseudo-Classes</title>
    <style>
        a:link {
            color: blue;
        }

        a:visited {
            color: red;
        }

        a:hover {
            color: green;
        }

        a:active {
            color: orange;
        }
    </style>

</head>

<body>
    <h2>Welcome To GFG</h2>

    <p><a href="https://www.geeksforgeeks.org">
            Click on this link to see the effects.
        </a>
    </p>
</body>

</html>
```

**输出:**

![](img/34d547da5b0ea5ac067a4acf591a8649.png)