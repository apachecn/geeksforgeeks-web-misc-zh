# 焦点和:活动选择器

之间的区别

> 原文:[https://www . geeksforgeeks . org/焦点和活动选择器之间的差异/](https://www.geeksforgeeks.org/difference-between-focus-and-active-selector/)

**:焦点选择器:**一般适用于表单元素或可以使用键盘或鼠标进行聚焦的元素，如输入框、文本区。当我们对某个元素使用键盘上的**【tab】**键时，该元素处于焦点状态。焦点的状态将保持不变，直到用户切换选项卡到另一个元素或单击。

**语法:**

```
:focus {
    // CSS Property
}
```

**示例:**此示例说明了:焦点选择器。

```
<!DOCTYPE html>
<html>

<head>
    <title>Focus pseudo class</title>

    <style>
        div.one{
            margin-left:40%;
            margin-top: 10%;
        }
        h1{
            color: green;
            font-family: Arial, Helvetica, sans-serif;
            letter-spacing: 2px;
        }
        button{
            font-size: x-large;
            padding: 10px;
            border: 2px solid black;
        }
        button:focus{
            color: green;
            background-color: white;
            font-style: italic;
        }
    </style>
</head>

<body>
    <div class="one">
        <h1>GeeksforGeeks</h1>

        <button type="submit">
            Focus or Click here
        </button>
    </div>
</body>

</html>                    
```

**输出**

*   **对焦前按钮:**
    ![](img/cd7b05e69dcf8ddf2880f9e79a329a2d.png)
*   **对焦后按钮:**
    ![](img/258d8e6cc27326c837902a204c4f7ea7.png)

**说明:**在上例中，使用以下 CSS 属性设置:焦点选择器。

```
button:focus {
    color: green;
    background-color: white;
    font-style: italic;
}
```

这些 CSS 属性用于设置按钮的样式。

*   文本的颜色将变为绿色。
*   背景-按钮的颜色将变为白色。
*   字体样式将从正常更改为斜体。

**激活:**一般适用于按钮和锚点标签。它在用户点击鼠标时触发。活动状态将保持不变，直到用户按住鼠标。

**语法:**

```
:active {
    // CSS property
}
```

**示例:**此示例说明了:活动选择器。

```
<!DOCTYPE html>
<html>

<head>
    <title>
        :active pseudo class
    </title>

    <style>
        div.one {
            margin-left:40%;
            margin-top: 10%;
        }
        h1 {
            color: green;
            font-family: Arial, Helvetica, sans-serif;
            letter-spacing: 2px;
        }
        button {
            font-size: x-large;
            padding: 10px;
            border: 2px solid black;
        }
        button:active {
            color:white;
            background-color: green;
            font-family: 'Courier New', Courier, monospace
        }
    </style>
</head>

<body>
    <div class="one">
        <h1>GeeksforGeeks</h1>

        <button type="submit">
            Focus or Click here
        </button>
        </div>
</body>

</html>                    
```

**输出**

*   **激活前状态(点击按钮前):**
    ![](img/cd7b05e69dcf8ddf2880f9e79a329a2d.png)
*   **点击按钮后:**
    ![](img/4d5c4ca5ec2323718f7bf17b6a27e959.png)

**说明:**在上例中，使用以下 CSS 属性设置:活动选择器。

```
button:active {
    background-color: green;
    font-family: 'Courier New', Courier, monospace
}
```

通过这些代码行，我们正在改变聚焦按钮的样式。

*   背景-按钮的颜色将变为绿色。
*   字体系列将被改变。