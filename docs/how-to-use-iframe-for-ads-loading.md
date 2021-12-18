# 如何使用 iframe 加载广告？

> 原文:[https://www . geeksforgeeks . org/如何使用-iframe-for-ads-loading/](https://www.geeksforgeeks.org/how-to-use-iframe-for-ads-loading/)

iframe 标签是 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 中最古老的 HTML 标签之一。 [HTML strong iframe 标签](https://www.geeksforgeeks.org/html-iframes/)用于在当前文档中嵌入另一个 HTML 文档。我们主要使用 iframe 在网页上显示广告。通常，您的广告提供商会给出广告单元的代码以及< iframe >标签。本文将重点介绍如何在网页中使用这些工具。

Iframes 与网页并行执行，因此减少了页面加载时间。但是这个标签也有一些限制，其中之一就是每个 iframe 标签都是对单个广告单元的独立请求。它不支持多广告单元请求。对于同一网页上的多个广告单元，我们必须为每个广告单元实现一个 iframe 标签。

**进场:**

*   我们将在 HTML 的主体中添加一个 iframe 标签
*   在 src 属性中插入广告网址。该网址将由广告提供商提供。
*   使用“高度和宽度”属性调整广告的高度和宽度。

**语法:**

```htmlhtml
<!-- Insert your ad url in src attribue 
and set height and width of your ad" --> 
<iframe src="https://youradurl.com" 
        height="700px" 
        width="500px">
</iframe>
```

这些是我们将在 iframe 标签中使用的常见属性:

*   **src:** 用于设置 ad 的地址。
*   **srcdoc:** 用于设置页面的 HTML 内容。
*   **高度:**用于以像素为单位设置 iframe 高度。
*   **宽度:**用于以像素为单位设置 iframe 宽度。
*   **名称:**用来设置 iframe 的名称，这样我们就可以在 JavaScript 中使用了。
*   **允许:**用于设置 iframe 的功能策略。
*   **沙盒:**用于设置 iframe 的限制。

**示例:**在此示例中，iframe 源被设置为某个网站，以演示在 iframe 中加载内容。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>
<body>
    <p> Welcome to GFG</p>
    <p>Below is a iframe tag</p>

    <!-- Added iframe tag with its attributes -->
    <iframe src="https://practice.geeksforgeeks.org/events/" 
            height="300px" 
            width="500px">
    </iframe>
</body>
</html>
```

**输出:**

![](img/08f63deb6fca62fc18f072292d4e9f1e.png)

**注意:**一些网站如谷歌、Youtube 等不允许你在 iframes 上显示他们的页面。他们阻止 iframes 显示他们的网站。我们只能在不受 iframe 保护的网站上使用 iframe。