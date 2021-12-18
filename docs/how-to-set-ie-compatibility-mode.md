# 如何设置 IE 兼容模式？

> 原文:[https://www . geesforgeks . org/how-set-ie-compatibility-mode/](https://www.geeksforgeeks.org/how-to-set-ie-compatibility-mode/)

Internet Explorer( **IE** )全球桌面浏览器市场份额占比不足 3%。如果我们正在开发一个包含全球用户或相当数量的老版本 T2 IE(T3)访问者的网站，那么我们必须使我们的网站与 T4 IE(T5)兼容，即使那已经过时了。这个问题的解决方案是 **X-UA 兼容模式**。

本文将告诉您如何使用 HTML 元标签设置 IE(Internet Explorer)。

**X-UA-Compatible** 是一个文档模式的元标签，允许我们选择页面应该呈现哪个版本的 Internet Explorer。关于 *http-equiv* 和*内容*标签的信息可在以下网址找到。

**示例:**此示例使用了一个元元素，该元素在**内容**属性中包含了一个 **X-UA 兼容**头和值 IE=9，该属性限制了网页功能，因此该网页受 Windows Internet Explorer 9 支持。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <title>Your Webpage Title</title>
  <!-- Use Internet Explorer 9 Standards mode -->
  <meta http-equiv="X-UA-Compatible" content="IE=9">
</head>
<body>
  <h>Your Heading</h>
  <p>Your content goes here.</p>
</body>
</html>
```

**的内容*****http-equiv*****标签如下:**

*   **IE=5** :此模式渲染网页，就好像是在 Internet Explorer 7 中以 Quirks 模式显示的一样。
*   **IE=7** :此模式呈现内容时就像是由 Internet Explorer 7 显示的一样
*   **IE=8** :这种模式为行业内很多既定标准提供了支持。
*   **IE=9** :这种模式为很多既定的行业标准提供了最高的支持。
    IE 9 不支持 CSS3 动画。
*   **IE=10** :这个模式为很多既定的行业标准提供了最高的支持，比如 HTML5、CSS3。
*   **IE=11** :这种模式为已经建立和新兴的行业标准提供了最高的支持，比如 HTML5、CSS3。
*   **IE=edge** :此模式指示 Internet Explorer 以可用的最高模式显示内容。
*   **IE =仿真 7** :工作原理与 **IE=7** 模式相同如果有效<！文档类型>声明存在于怪癖模式中。
*   **IE =仿真 8:** 工作原理与 **IE=8** 模式相同如果一个有效的<！文档类型>声明存在于怪癖模式中。
*   **IE =仿真 9:** 工作原理与 **IE=9** 模式相同如果一个有效的<！文档类型>声明存在于怪癖模式中。
*   **IE =仿真 10:** 工作原理与 **IE=10** 模式相同如果一个有效的<！文档类型>声明存在于怪癖模式中。
*   **IE =仿真 11:** 工作原理与 **IE=11** 模式相同如果一个有效的<！文档类型>声明存在于怪癖模式中。

**怪癖模式:**这种模式是一些浏览器在维护为旧浏览器开发的页面的向后兼容性时使用的一种技术，就像我们的 Internet Explorer 一样。