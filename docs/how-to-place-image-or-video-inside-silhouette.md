# 如何在《剪影》里面放置图像或视频？

> 原文:[https://www . geesforgeks . org/how-to-place-image-or-video-inside-剪影/](https://www.geeksforgeeks.org/how-to-place-image-or-video-inside-silhouette/)

在本文中，我们将学习如何使用 CSS 将图像或视频放置在剪影中。在此之前，我们先来简单定义一下剪影。它基本上是任何人、动物的图像，或者它可以是任何用纯色调色板表示的物体。一般是黑色的。基本上，我们在这篇文章中要做的是，我们将放置或插入任何想要的图像或视频，然后我们将实现一个效果，这样我们的图像将只显示为纯色的剪影。我们可以用一个叫做*混合-混合-模式*的简单 CSS 属性非常容易地做到这一点。

[![](img/a37419eb7464e87d61db76aab709a04a.png)](https://media.geeksforgeeks.org/wp-content/uploads/20210723162735/pattern1-300x295.png)

为了在剪影中放置任何图像或视频，请确保我们有所需的图像和视频文件&我们将放置它们的剪影。让我们从一步一步的过程开始。

**示例:**创建一个 HTML 文件，并添加下面一行代码。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"/>

    <title>Image inside the Silhouette</title>

    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
      body {
        min-height: 100vh;
      }
      .container {
        display: flex;
        justify-content: center;
        align-items: center;
      }
      .container .main {
        position: relative;
        width: 400px;
        height: 400px;
        margin: 50px;
      }
      .container .main img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        mix-blend-mode: screen;
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="main">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210723124629/gfg-200x200.png"/>
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210723162735/pattern1-300x295.png"/>
      </div>
    </div>
  </body>
</html>
```

**输出:**在这种情况下，我们可以看到花哨的形状被用作剪影图像。这就是我们如何将图像添加到剪影中。现在，对于添加视频或 gif，我们不需要做任何额外的工作，我们只需要在现有文件中添加一些更多的 HTML 和 CSS。

[![](img/1645ae84850d36ea99dc0a00d934f3af.png)](https://media.geeksforgeeks.org/wp-content/uploads/20210723162903/gfg-300x285.jpg)