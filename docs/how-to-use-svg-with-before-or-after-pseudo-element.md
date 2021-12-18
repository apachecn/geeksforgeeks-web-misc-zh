# 如何使用带有:before 或:after 伪元素的 SVG？

> 原文:[https://www . geesforgeks . org/how-using-SVG-with-before-or-after-pseudo-element/](https://www.geeksforgeeks.org/how-to-use-svg-with-before-or-after-pseudo-element/)

[**:在**](https://www.geeksforgeeks.org/css-before-selector/) 和[**之前:**](https://www.geeksforgeeks.org/css-after-selector/) 之后的伪元素允许在不添加不必要的标记的情况下给网页添加样式。可以通过以下方法使用这些伪元素添加 SVG 内容:

**方法 1:使用背景图像属性:**[**背景图像**](https://www.geeksforgeeks.org/css-background-image-property/) 属性用于为元素设置一个或多个背景图像。我们也可以使用这个属性添加 SVG 内容，并将内容属性留空。其他 CSS 属性有助于正确定位和调整内容的大小。

**示例:**

## HTML

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <style>
        .svg-demo {
            text-align: center;
            font-weight: bold;
            font-size: 20px;
        }

        .text {
            text-align: center;
        }

        /* Using the :before pseudo-element
           to add the SVG content */
        .svg-demo:before {
            display: inline-flex;
            content: '';

            /* Using the background-image and
               its related properties to add
               the SVG content */
            background-image: url('gfg_logo.svg');
            background-size: 40px 40px;
            height: 40px;
            width: 40px;
        }

        /* Using the :after pseudo-element
           to add the SVG content */
        .svg-demo:after {
            display: inline-flex;
            content: '';

            /* Using the background-image and
               its related properties to add
               the SVG content */
            background-image: url('gfg_logo.svg');
            background-size: 40px 40px;
            height: 40px;
            width: 40px;
        }
    </style>
</head>

<body>
    <p class="svg-demo">
        This is the normal content
    </p>

    <p class="text">
        The SVG images are added before
        and after the line using :before
        and :after pseudo-elements
    </p>

</body>

</html>
```