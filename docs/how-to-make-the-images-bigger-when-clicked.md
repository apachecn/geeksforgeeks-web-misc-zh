# 点击时如何让图片变大？

> 原文:[https://www . geeksforgeeks . org/如何使图像在单击时变大/](https://www.geeksforgeeks.org/how-to-make-the-images-bigger-when-clicked/)

有两种常用的方法可以用来在使用 javascript 单击时调整图像的大小。javascript 函数可以通过指定***onclick =“function _ name()”***来调用

**方法 1:** 变换:比例()

**语法:**

```html
object.style.transform = scale(sx);

object.style.transform = scale(sx, sy);
```

*变换*属性用于修改元素的形状、大小或位置。通过指定*比例*值，可以根据给定的比例修改元素的大小。
如果未提供 s <sub>y</sub> ，则其默认值为 s <sub>x</sub> ，这将导致均匀缩放，从而保持元素的纵横比。

**进场:**

*   使用**获取所需图像的选择器。getElementById(选择器)。**
*   使用**设置图像需要放大的比例。**
*   可以使用 **.style.transition** 添加动画效果，以给出吸引人的外观。
*   当使用**调用该函数时。onclick()** 方法在图像选项卡上，图像的大小将按照给定的比例成比例地增加。**T3】**

**示例:**

```html
<!DOCTYPE html>
  <head>
    <title>Image Resize JS</title>
  </head>
  <body>
    <div class="container" style="text-align: center; margin-top: 5em;">
      <!-- Image to be enlarged and onclick() function call-->
      <img
        src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png"
        onclick="enlargeImg()"
        id="img1"
      />
      <br /><br /><br />
      <!-- Button to reset the Image size -->
      <button onclick="resetImg()">Reset</button>
    </div>

    <!-- script to set display property -->
    <script>
      // Get the img object using its Id
      img = document.getElementById("img1");
      // Function to increase image size
      function enlargeImg() {
        // Set image size to 1.5 times original
        img.style.transform = "scale(1.5)";
        // Animation effect 
        img.style.transition = "transform 0.25s ease";
      }
      // Function to reset image size
      function resetImg() {
        // Set image size to original
        img.style.transform = "scale(1)";
        img.style.transition = "transform 0.25s ease";
      }
    </script>
  </body>
</html>
```

**输出:**

![](img/0118c66f61d716e47368cf2450c626dd.png)

**方法 2:** CSS 高度和宽度

**语法:**

```html
object.style.width = value(%，px，em，auto 等)；object.style.height= value(%，px，em，auto 等)；
```

CSS 高度和宽度属性指定元素的高度和宽度。利用这一点，我们可以在放大(或缩小)的图像中明确定义我们想要的尺寸。

**进场:**

*   使用**获取所需图像的选择器。getElementById(选择器)**。
*   使用 **.style.width** 设置放大图像应有的宽度/高度值。
*   建议保持其他尺寸值*自动*，以保持图像的纵横比。
*   可以使用 **.style.transition** 添加动画效果，以给出吸引人的外观。
*   当使用**调用该函数时。onclick()** 方法在图像选项卡上，图像的大小将根据给定的尺寸而变化。

**示例:**

```html
<!DOCTYPE html>
<html>
    <body>
        <div class="container" 
             style="text-align: center; 
                    margin-top: 5em;">
            <!-- Image to be enlarged and
                onclick() function call-->
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png"
                 onclick="enlargeImg()" 
                 id="img1" />
            <br />
            <br />
            <br />
            <!-- Button to reset the Image size -->
            <button onclick="resetImg()">Reset
          </button>
        </div>

        <!-- script to set display property -->
        <script>
            img = document.getElementById("img1");
            // Function to set image dimensions
            function enlargeImg() {
                img.style.width = "60%";
                img.style.height = "auto";
                img.style.transition = "width 0.5s ease";
            }
            // Function to reset image dimensions
            function resetImg() {
                img.style.width = "40%";
                img.style.height = "auto";
                img.style.transition = "width 0.5s ease";
            }
        </script>
    </body>
</html>
```

**输出:**

![](img/25b82f08179c4e800a0e4b8a31b032e8.png)

使用“*这个“*关键字 *:* 将图像元素直接传递给函数

除了使用其 *id 获取所需元素外，*还可以将图像元素的引用([使用此关键字](https://www.geeksforgeeks.org/this-reference-in-java/))作为参数传递给函数，并对其执行所需操作。然而，对于重置按钮部分，通过 id 获取元素选择器是最好的选择，因为将它的引用传递给重置函数会改变重置按钮的大小。

**进场:**

*   这类似于第一种方法，只是我们直接将对图像的引用作为参数传递给函数。

**示例:**

```html
<!DOCTYPE html>
<html>
    <body>
        <div class="container" 
             style="text-align: center;
                    margin-top: 5em;">
            <!-- Image to be enlarged and onclick() 
            function call
      Passing the reference to this img
             as a parameter    -->
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png"
                 onclick="enlargeImg(this)" />
        </div>

        <!-- script to set display property -->
        <script>
            // Function to increase image size
            function enlargeImg(img) {
                img.style.transform = "scale(1.5)";
                img.style.transition =
                  "transform 0.25s ease";
            }
        </script>
    </body>
</html>
```

**输出:**

![](img/0118c66f61d716e47368cf2450c626dd.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。