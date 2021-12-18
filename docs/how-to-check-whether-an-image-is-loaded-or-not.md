# 如何检查图片是否加载？

> 原文:[https://www . geeksforgeeks . org/如何检查图像是否已加载/](https://www.geeksforgeeks.org/how-to-check-whether-an-image-is-loaded-or-not/)

在 HTML 页面中插入图像时，有时由于以下原因，图像可能无法加载:

*   获取图像网址错误
*   互联网连接不良

因此，我们可能需要检查图像是否由于这些原因而没有加载。要进行检查，我们可以使用以下方法

**方法 1:**

使用 **< img >** 的属性检查图像是否加载。我们将使用的**属性**有:

*   **加载:**加载并执行图像时，会触发加载事件
*   **one error:**如果在执行过程中出现错误，则会触发 one error 事件

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Image load check</title>
  </head>
  <body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png"
     onload=
"javascript: alert('The image has been loaded')"
     onerror=
"javascript: alert('The image has failed to load')" />
  </body>
</html>
```

**输出:**

![](img/b18637fb125bf4e89c1ef4500b0aade7.png)

当图像被成功加载时

![](img/c47485d722137ee8149a260f864731a2.png)

当图像加载失败时

**方法二:**

使用 HTML DOM 中的图像完整属性

如果加载了图像，此属性返回一个布尔值，否则返回 false

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Checking if image is loaded</title>
  </head>
  <script type="text/javascript">
  window.addEventListener("load", event => {
  var image = document.querySelector('img');
  var load = image.complete;
  alert(load);
});
  </script>
  <body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png">
  </body>
</html>
```

这里，变量 load 检查图像是否被加载。如果加载了图像，则警告为真，否则警告为假。

**输出:**

![](img/7ec920c35e2c366a77e2dc4eb362729a.png)

当图像被成功加载时

![](img/b59dde96aff39f53ef6ac71a99f0cfb4.png)

当图像加载失败时

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   微软公司出品的 web 浏览器
*   旅行队
*   歌剧