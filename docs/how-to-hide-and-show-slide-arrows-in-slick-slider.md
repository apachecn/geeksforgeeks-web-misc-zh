# 如何在光滑滑块中隐藏和显示滑动箭头？

> 原文:[https://www . geeksforgeeks . org/如何隐藏和显示滑盖箭头/](https://www.geeksforgeeks.org/how-to-hide-and-show-slide-arrows-in-slick-slider/)

在这篇文章中，我们将创建一个光滑滑块，稍后将向您展示如何显示/隐藏光滑滑块的按钮。
要创建一个光滑的滑块，只需声明许多具有相同类名的元素。

**示例:**

```html
<!DOCTYPE html>
<html>
    <body>
        <div>
            <img class="mySlides" 
                 width="33%" 
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101335/1406-7-300x83.png" 
                 alt="" 
                 width="300"
                 height="83" 
                 class="alignnone 
                        size-medium wp-image-2098786" />
            <img class="mySlides" 
                 width="33%" 
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101453/267-300x83.png" 
                 alt="" 
                 width="300" 
                 height="83" 
                 class="alignnone
                        size-medium wp-image-2098787" />
            <img class="mySlides"
                 width="33%"
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101335/1406-7-300x83.png" 
                 alt="" 
                 width="300" 
                 height="83" 
                 class="alignnone 
                        size-medium wp-image-2098786" />
        </div>
    </body>
</html>
```

**输出:**
![](img/f5778b0bbda3d1e99a33cb112e03d5a9.png)

现在，只需在左右角添加两个按钮，使用 HTML 滑动图像，并使用 JavaScript 声明一个 onClick 方法来更改显示图像的
索引。

**示例:**

```html
<!DOCTYPE html>
<html>
    <body>
        <div>
            <img class="mySlides" 
                 width="33%" 
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101335/1406-7-300x83.png" 
                 alt="" 
                 width="300"
                 height="83" 
                 class="alignnone 
                        size-medium wp-image-2098786" />
            <img class="mySlides" 
                 width="33%" 
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101453/267-300x83.png" 
                 alt="" 
                 width="300" 
                 height="83" 
                 class="alignnone
                        size-medium wp-image-2098787" />
            <img class="mySlides"
                 width="33%"
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101335/1406-7-300x83.png" 
                 alt="" 
                 width="300" 
                 height="83" 
                 class="alignnone 
                        size-medium wp-image-2098786" />
            <button onclick="plusDivs(-1)">❮</button>
            <button onclick="plusDivs(1)">❯</button>
        </div>
<script>
    var slideIndex = 1;
    showDivs(slideIndex);

    function plusDivs(n) {
        showDivs((slideIndex += n));
    }

    function showDivs(n) {
        var i;
        var x = document.getElementsByClassName("mySlides");
        if (n > x.length) {
            slideIndex = 1;
        }
        if (n < 1) {
            slideIndex = x.length;
        }
        for (i = 0; i < x.length; i++) {
            x[i].style.display = "none";
        }
        x[slideIndex - 1].style.display = "block";
    }
</script>

    </body>
</html>
```

**输出:**
![](img/cb6145462747f80fd60c44b818c03299.png)

**JavaScript 代码说明:**
第一次加载脚本时，slideIindex 会设置为 1(第一张图片)，当用户点击任意一个按钮时，
slideIndex 会根据它增加或减少。图像就会显示出来。Display = "none "将隐藏图片，
display = "block "将再次显示图片。

**隐藏按钮:**
要隐藏按钮，您可以删除这两行:

```html
" button onclick="plusDivs(-1)">&#10094 button"
" button onclick="plusDivs(1)">&#10095 button"

```

并且不用 onClick 调用脚本，而是使用 setTimeout(function_name，time_in_ms)函数，在设定的时长内自动调用函数
本身。

**示例:**

```html
<!DOCTYPE html>
<html>
    <meta content="text/html; charset=iso-8859-2" http-equiv="Content-Type" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <style>
        .mySlides {
            display: none;
        }
    </style>

    <body>
        <div>
            <img class="mySlides"
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101335/1406-7-300x83.png"
                 alt="" 
                 width="300" 
                 height="83" 
                 class="alignnone 
                        size-medium 
                        wp-image-2098786" />
            <img class="mySlides" 
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101453/267-300x83.png" 
                 alt="" 
                 width="300" 
                 height="83" 
                 class="alignnone 
                        size-medium
                        wp-image-2098787" />
            <img class="mySlides" 
                 src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200813101335/1406-7-300x83.png" 
                 alt=""
                 width="300"
                 height="83" 
                 class="alignnone 
                        size-medium 
                        wp-image-2098786" />
        </div>

        <script>
            var slideIndex = 0;
            showDivs();

            function showDivs() {
                var i;
                var x = document.getElementsByClassName("mySlides");
                slideIndex++;
                if (slideIndex > x.length) {
                    slideIndex = 1;
                }
                for (i = 0; i < x.length; i++) {
                    x[i].style.display = "none";
                }
                x[slideIndex - 1].style.display = "block";
                setTimeout(showDivs, 2000);
            }
        </script>
    </body>
</html>
```

**输出:**
![](img/d33f3e9cd139dc16b46b51836dbe345b.png)
![](img/1966014e8dfdc5c1386830ec4dd72bb3.png)