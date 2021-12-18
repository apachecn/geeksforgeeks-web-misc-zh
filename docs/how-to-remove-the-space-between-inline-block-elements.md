# 如何去除内嵌块元素之间的空间？

> 原文:[https://www . geeksforgeeks . org/如何删除内联块元素之间的空间/](https://www.geeksforgeeks.org/how-to-remove-the-space-between-inline-block-elements/)

有两种方法可以删除内联块元素之间的空间。

**方法 1:** 将内嵌块元素的父元素的字体大小指定为 0px，然后将适当的字体大小指定给内嵌块元素

> **语法:**
> 父元素{
> 字号:0px
> }
> 父元素子元素{
> 显示:内嵌块；
> 字号:必选字号；
> }

以下代码说明了上述概念:

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>

        /*Assign font-size of parent element to 0px*/
        div {
            font-size: 0px;                              
        }

        /*Making the element inline-block*/
        /*Assign proper font-size to the inline block element*/
        div span {
            display: inline-block;                        
            background-color: green;
            font-size: 10rem;                             
        }
    </style>
    <title>How to remove spaces between inline block elements</title>
</head>

<body>
    <div>
        <span>Geeks</span>
        <span>For</span>
        <span>Geeks</span>
    </div>
</body>

</html>
```

**输出:**

![](img/2a28bfc584e7cf06e1f0ac76a6582fd4.png)

**方法 2:** 使父元素的显示弯曲。

> **语法:**
> 
> 父元素{
> 显示:flex
> }
> 父元素子元素{
> 显示:内嵌块；
> 字号:必选字号；
> }

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /*Making the parent element a flexbox*/
        div {
            display: flex;                             
        }

        /*Making the element inline-block*/
        /*Assign proper font-size to the inline block element*/
        div span {
            display: inline-block;                        
            background-color:rgb(53, 77, 5);
            font-size: 10rem;                             
        }
    </style>
    <title>How to remove spaces between inline block elements</title>
</head>

<body>
    <div>
        <span>Geeks</span>
        <span>For</span>
        <span>Geeks</span>
    </div>
</body>

</html>
```

**输出:**

![](img/0341327be59afbdf3329e0697443ce2d.png)