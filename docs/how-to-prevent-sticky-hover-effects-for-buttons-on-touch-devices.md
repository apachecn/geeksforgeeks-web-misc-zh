# 如何防止触控设备上的按钮出现粘滞悬停效果？

> 原文:[https://www . geeksforgeeks . org/如何防止触摸设备上按钮的粘滞悬停效果/](https://www.geeksforgeeks.org/how-to-prevent-sticky-hover-effects-for-buttons-on-touch-devices/)

当我们在 CSS 中给一个元素添加悬停效果时，它会粘在触摸设备上。在本文中，我们将学习如何解决这个问题。

有两种可能的方法来解决这个问题–

**1。不使用 JavaScript:** 可以用 CSS 中的媒体查询解决。条件**“悬停:悬停”**是指支持悬停的设备。在这种情况下使用媒体查询可确保仅在此类设备上添加以下 CSS。

**代码片段:**

```htmlhtml
@media(hover: hover) {
    #btn:hover {
        background-color: #ccf6c8;
    }
}
```

这仅在启用悬停的设备上添加悬停效果，这意味着在触摸设备上不应用悬停效果。在这里，悬停时按钮的背景颜色会改变。

**示例:**

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <style>
        #btn {
            background-color: #0dad78;
            margin: 3%;
            font-size: 30px;
        }

        @media (hover: hover) {
            #btn:hover {

                /*Add hover effect to button 
                on hover enabled devices*/
                background-color: #ccf6c8;
            }
        }
    </style>
</head>

<body>
    <button type="button" id="btn">
        Submit
    </button>
</body>

</html>
```

**输出(在非触摸屏上):**

<video class="wp-video-shortcode" id="video-501244-1" width="640" height="360" loop="1" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201005202449/index.html.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201005202449/index.html.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201005202449/index.html.mp4)</video>

按钮在触摸设备上保持其原始状态，因为没有悬停效果。

**2。使用 JavaScript:** 在这种方法中，我们将使用 JavaScript，使用下面的函数来确定我们是否在支持触摸的设备上。当用户触摸一个元素时， **ontouchstart** 事件返回真。**导航器。最大触摸点**返回设备支持的最大同时触摸点数量。**navigator . msmaxtouchpoints**也有同样的功能，厂商前缀为“ms”，目标浏览器为 IE 10 及以下。

因此，如果设备启用了触摸，则给定功能返回真。(要了解更多关于该功能的信息，请参考:[https://www . geeksforgeeks . org/how-detect-touch-screen-device-use-JavaScript/](https://www.geeksforgeeks.org/how-to-detect-touch-screen-device-using-javascript/))

```htmlhtml
function is_touch_enabled() {
    return ('ontouchstart' in window) ||
    (navigator.maxTouchPoints > 0) ||
    (navigator.msMaxTouchPoints > 0);
}
```

如果触摸未启用，我们会为按钮添加一个类。这个类为 CSS 中的按钮添加了悬停效果，如下例所示:

**示例:**

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <style>
        #btn {
            background-color: #0dad78;
            margin: 3%;
            font-size: 30px;
        }

        .btn2:hover {
            background-color: #ccf6c8 !important;
            /*Hover effect is added to btn2 class*/
        }
    </style>
</head>

<body onload="hover()">
    <button type="button" id="btn">Submit</button>

    <script>
        function hover() {
            function is_touch_enabled() {

                // Check if touch is enabled
                return "ontouchstart"
                    in window || navigator.maxTouchPoints > 0
                    || navigator.msMaxTouchPoints > 0;
            }
            if (!is_touch_enabled()) {

                // If touch is not enabled, add "btn2" class
                var b = document.getElementById("btn");
                b.classList.add("btn2");
            }
        }
    </script>
</body>

</html>
```

**输出(在非触摸设备上):**

<video class="wp-video-shortcode" id="video-501244-2" width="640" height="360" loop="1" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201005202449/index.html.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201005202449/index.html.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201005202449/index.html.mp4)</video>

按钮在触摸设备上保持其原始状态，因为没有悬停效果。