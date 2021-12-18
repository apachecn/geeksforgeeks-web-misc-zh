# 当用户向下滚动时动态改变图像|设置 2

> 原文:[https://www . geesforgeks . org/change-image-dynamic-when-user-scroll-down-set-2/](https://www.geeksforgeeks.org/change-image-dynamically-when-user-scrolls-down-set-2/)

[当用户使用 JavaScript 滚动时动态改变图像|设置 1](https://www.geeksforgeeks.org/how-to-change-image-dynamically-when-user-scrolls-using-javascript/)

可能存在图像需要基于用户输入动态改变的情况。在这种情况下，当用户向下滚动。

**进场:**

*   设置一个滚动事件监听器来知道用户已经滚动了页面。
*   计算用户垂直向上滚动的像素。它是通过使用 scrollTop 元素来访问的。

    ```html
    document.documentElement.scrollTop
    ```

*   使用该值动态更改图像的来源。

**示例 1:** 在本例中，只要页面垂直滚动 150 像素，我们就会更改图像的来源。该页面由图像和文本部分组成。它们是通过内部 CSS 设计的。

用户每次滚动时`window.onscroll`监听器都会调用一个函数。然后，被调用的函数使用`document.getElementById("myImage")`选择图像，并在滚动像素超过 150 像素时改变图像的源路径。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>
        How to change image dynamically
        when user scrolls down?
    </title>

    <style media="screen">
        img {
            position: fixed;
            width: 30%;
        }

        .main-content {
            padding-left: 35%;
            height: 1000px;
        }

        h1,
        h3 {
            color: green;
        }
    </style>
</head>

<body>
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200122115631/GeeksforGeeks210.png"
        alt="GeeksforGeeks Logo" id="myImage">

    <div class="main-content">
        <h1>GeeksforGeeks</h1>
        <h3>First Image Section</h3>
        <p>
            Scroll past the below line 
            to see the change
        </p>
        <hr>
        <h3>Second Image Section</h3>
        <p>
            Scroll back up to see 
            the original image
        </p>
    </div>

    <script>
        window.onscroll = function () {
            scrollFunction();
        };

        function scrollFunction() {
            var image = document.getElementById("myImage");
            if (document.documentElement.scrollTop > 150)
                image.src = 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png";
            else
                image.src = 
"https://media.geeksforgeeks.org/wp-content/uploads/20200122115631/GeeksforGeeks210.png";
        }
    </script>
</body>

</html>
```

**输出:**
![](img/55b46e2b80e60cbbdd33d24b8631ae05.png)

**示例 2:** 在本例中，我们将根据用户向下滚动的程度动态更改图像的排列。该页面由四个图像组成，在页面底部有一个粘性位置。

滚动侦听器调用的函数动态地打乱图像的来源。这给了我们图像旋转的外观。

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>
        How to Change Image Dynamically when
        User Scrolls using JavaScript ?
    </title>

    <style media="screen">
        .main-content {
            height: 800px;
        }

        .footer {
            position: sticky;
            bottom: 0;
            background-color: white;
        }

        .footerRow::after {
            content: "";
            clear: both;
            display: table;
            position: sticky;
            bottom: 0;
            width: 100%;
        }

        .footerColumn {
            float: left;
            width: 25%;
            display: table;
            position: relative;
            margin: auto;
        }

        img {
            width: 100%;
        }

        h1,
        h3 {
            color: green;
        }
    </style>
</head>

<body>

    <div class="main-content">
        <h1>GeeksforGeeks</h1>
        <h3>Section One</h3>
        <p>Scroll here to see the change</p>
        <hr>
        <h3>Section Two</h3>
        <p>Scroll here to see the change</p>
        <hr>
        <h3>Section Three</h3>
        <p>Scroll here to see the change</p>
        <hr>
        <h3>Section Four</h3>
        <p>Scroll here to see the change</p>
        <hr>
    </div>

    <div class="footer">
        <div class="footerRow">
            <div class="footerColumn">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png" 
                id="image1">
            </div>
            <div class="footerColumn">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200122115631/GeeksforGeeks210.png"
                    id="image2">
            </div>
            <div class="footerColumn">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200121120603/GeeksforGeeks30.png"
                    id="image3">
            </div>
            <div class="footerColumn">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20191026152101/geeks_for_geeks.jpg"
                    id="image4">
            </div>
        </div>
    </div>

    <script>
        window.onscroll = function () {
            scrollFunction();
        };

        function scrollFunction() {
            var imageSource1 = 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png";
            var imageSource2 = 
"https://media.geeksforgeeks.org/wp-content/uploads/20200122115631/GeeksforGeeks210.png";
            var imageSource3 = 
"https://media.geeksforgeeks.org/wp-content/uploads/20200121120603/GeeksforGeeks30.png";
            var imageSource4 = 
"https://media.geeksforgeeks.org/wp-content/uploads/20191026152101/geeks_for_geeks.jpg";

            var image1 = document.getElementById("image1");
            var image2 = document.getElementById("image2");
            var image3 = document.getElementById("image3");
            var image4 = document.getElementById("image4");
            if (document.documentElement.scrollTop < 150) {
                image1.src = imageSource1;
                image2.src = imageSource2;
                image3.src = imageSource3;
                image4.src = imageSource4;
            } else if (
                document.documentElement.scrollTop < 250) {
                image1.src = imageSource2;
                image2.src = imageSource3;
                image3.src = imageSource4;
                image4.src = imageSource1;
            } else if (
                document.documentElement.scrollTop < 350) {
                image1.src = imageSource3;
                image2.src = imageSource4;
                image3.src = imageSource1;
                image4.src = imageSource2;
            } else {
                image1.src = imageSource4;
                image2.src = imageSource1;
                image3.src = imageSource2;
                image4.src = imageSource3;
            }
        }
    </script>
</body>

</html>
```

**输出:**
![](img/09841175770fdd1dce7210aa63b15555.png)