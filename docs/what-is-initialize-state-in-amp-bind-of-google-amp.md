# 谷歌 amp 的 amp-bind 中的初始化状态是什么？

> 原文:[https://www . geeksforgeeks . org/什么是谷歌 amp-amp-bind 中的初始化状态/](https://www.geeksforgeeks.org/what-is-initialize-state-in-amp-bind-of-google-amp/)

![](img/911091c569b094b6e54a226311a9df7b.png)

amp-bind 的制作方式是，任何使用它的文档都有一个可变的 JSON 数据或状态。该数据可以使用放大器状态进行操作。您的数据不是在页面加载时评估的，而是随着用户输入一起动态评估的。它有各种状态，它们有自己的变量。在本文中，我们将讨论元素的初始状态。

放大器状态变量的初始值总是为空，但是当用户与页面交互时可以更改。

**设置:**要在我们的 amp 页面中使用 amp-bind-macro，我们必须在文档的头部导入 amp-bind 脚本。

## 超文本标记语言

```html
<script async custom-element="amp-bind" src=
"https://cdn.ampproject.org/v0/amp-bind-0.1.js">
</script>
```