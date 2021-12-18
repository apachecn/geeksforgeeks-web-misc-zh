# LESS 中有哪些嵌套规则？

> 原文:[https://www . geesforgeks . org/什么是嵌套规则 in less/](https://www.geeksforgeeks.org/what-are-nested-rules-in-less/)

我们可以非常容易地在 LESS 中定义嵌套规则。嵌套规则被定义为一组 CSS 属性，允许一个类的属性用于另一个类，并包含类名作为其属性。在 LESS 中，可以使用类或 ID 选择器来声明**混合**，方式与 CSS 样式相同。它可以存储多个****值**，并且可以根据需要在代码中重用。**

**人们一定听说过*嵌套*这个词，大概指的是旧表格设计网站中的嵌套表格。使用 LESS，我们基本上是在做同样的概念，但是在其他规则中嵌套 LESS 规则。下面的例子将演示在 LESS 中嵌套的概念。**

****示例 1:****

## **HTML**

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" 
        type="text/css" href="style.css" />
</head>

<body>
    <div class="container">
        <h1>Example of less</h1>

        <p>We will discuss LESS here.</p>

        <div class="MyClass">
            <h1>Geeks for Geeks portal</h1>

            <p>
                Nested rules are clever about
                handling selector lists 
            </p>
        </div>
    </div>
</body>

</html>
```