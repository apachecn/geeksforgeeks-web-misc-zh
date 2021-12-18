# 如何在电话模式下隐藏按钮文字？

> 原文:[https://www . geesforgeks . org/如何隐藏手机模式下的按钮文本/](https://www.geeksforgeeks.org/how-to-hide-button-text-in-phone-mode/)

在为智能手机等小屏幕设备建立网站时，明智地使用每一点屏幕空间变得非常重要，我们不能浪费任何面积。为了实现这一点，我们可以在电话模式下隐藏一些外围元素。

**在电话模式下隐藏按钮文本:**

**示例:**这个示例是使用 CSS 实现的。我们可以使用 [*媒体查询*](https://www.geeksforgeeks.org/css-media-queries/) 在 CSS 中根据设备的屏幕大小隐藏按钮文本。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <style>

        /* Basic styling */
        #btn {
            width: auto;
        }

        /* It is triggered when screen
           size becomes <=768px */
        @media(max-width:768px) {
            #btn-text {

                /* It hides the button text
                when screen size <=768px */
                display: none;
            }
        }
    </style>
</head>

<body>
    <h2 style="color:green">
        GeeksforGeeks
    </h2>

    <b>
        Hiding button text
        in phone mode</b><br /><br />
    <button id="btn">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210520182549/myDelete.png"
            id="icon">
        <span id="btn-text">Delete</span>
    </button>
</body>

</html>
```