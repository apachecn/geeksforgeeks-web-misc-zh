# 如何使用图像比较滑块比较两幅图像？

> 原文:[https://www . geeksforgeeks . org/如何使用图像比较滑块比较两幅图像/](https://www.geeksforgeeks.org/how-to-compare-two-images-using-image-comparison-slider/)

在这个项目中，我们将创建一个图像滑块，我们可以用它来检查 2 个图像。如果我们要复制它们。我们可以在垂直和水平方向上比较第一幅图像和第二幅图像的每个边界。

**方法:**

*   Create an HTML file, in which we will add the main *div* , and in addition, we will add two [T2】 div 【T3] to add images.
*   Create a CSS file and add images to their respective *div* .
*   Create a JavaScript file that changes direction and compare two pictures.

**HTML 代码:**

*   First, create an HTML file (index.html).
*   Now, after our HTML file is created, we will use the tag to give a title to our webpage. It should be placed between the tags.
*   Then we link the CSS file that provides all the background pictures to our HTML. This is also placed on the label.
*   Come to the main body of our HTML code.
    *   First, create a main div as the main box.
    *   In *div,* adds two [T2】 div 【T3] to increase image 1 and image 2.
    *   Add tag at the end of our body, which links JavaScript file with our HTML file.

## index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>    
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>
      PRESS:'v' for vertical movement & 'h' \
      for horizontal movement
    </h1>
    <div class="main_box">
        <div class="img1"></div>
        <div class="img2"></div>
    </div>
    <script src="index.js"></script>
</body>
</html>
```