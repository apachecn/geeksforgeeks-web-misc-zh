# 如何设置弹性箱之间的空间？

> 原文:[https://www . geeksforgeeks . org/如何设置 flexbox 之间的空间/](https://www.geeksforgeeks.org/how-to-set-space-between-the-flexbox/)

柔性盒模块或柔性盒是一种布局模型。这种布局的主要目的是在容器中的项目之间分配空间。这种布局是一维布局模型。当项目的大小未知或动态时，flexbox 布局甚至可以工作。

要设置弹性框之间的空间，您可以使用弹性框属性 **[调整内容](https://www.geeksforgeeks.org/advance-css-layout-with-flexbox/)** 您也可以访问该链接中的所有属性。

我们可以使用 flex 容器的对齐内容属性来设置 flexbox 之间的空间。
**语法:**

*   值 space-between 用于显示行间有空格的弹性项。

    ```
    justify-content: space-between;
    ```

*   值空格用于显示线条之间、之前和之后有空格的弹性项。

    ```
    justify-content: space-around;
    ```

下面的示例将说明用于设置 flexbox 之间的空间的属性。

**示例:**

```
<!DOCTYPE html> 
<html> 
    <head> 
        <title>Space between flexbox</title> 
        <style> 
            .flex2 { 
                display: flex; 
                justify-content: space-around; 
                background-color: green; 
            } 
            .flex3 { 
                display: flex; 
                justify-content: space-between; 
                background-color: green; 
            } 
            .flex-items { 
                background-color: #f4f4f4; 
                width: 100px; 
                height:50px; 
                margin: 10px; 
                text-align: center; 
                font-size: 40px; 
            } 
            h3 { 
                text-align:center; 
            } 
            .geeks { 
                font-size:40px; 
                text-align:center; 
                color:#009900; 
                font-weight:bold; 
            }                     
        </style> 
    </head> 

    <body> 
        <div class = "geeks">GeeksforGeeks</div> 
        <h3>Space between flexbox</h3> 

        <br> 
        <b>justify-content: space-around </b> 
        <div class="flex2"> 
            <div class="flex-items">1</div> 
            <div class="flex-items">2</div> 
            <div class="flex-items">3</div> 
        </div> 
        <br> 
        <b>justify-content: space-between </b> 
        <div class="flex3"> 
            <div class="flex-items">1</div> 
            <div class="flex-items">2</div> 
            <div class="flex-items">3</div> 
        </div> 
        <br> 

    </body> 
</html>                                 
```

**输出:**
![](img/38769d1a8e7758e7ee4f14ac2d82b462.png)