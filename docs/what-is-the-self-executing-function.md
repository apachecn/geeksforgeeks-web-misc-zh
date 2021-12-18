# 什么是自动执行功能？

> 原文:[https://www . geesforgeks . org/什么是自动执行功能/](https://www.geeksforgeeks.org/what-is-the-self-executing-function/)

一个**自执行函数**是 JavaScript 中的一个函数，它的执行不需要被调用，它在 JavaScript 文件中一创建就执行自己。此函数没有名称，也称为匿名函数。这个函数在一组圆括号内初始化，参数可以通过最后的圆括号传递。

**语法:**

```
(function (parameters) {
    // Code block to be executed
})(parameters);
```

**示例:**

## HTML

```
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>

    <b>
        What is a self-executive function?
    </b>

    <p>
        This page was generated on: 
        <span class="output"></span>
    </p>

    <script type="text/javascript">
        (function () {
            date = new Date().toString();

            document.querySelector('.output').textContent
                        = date;
        })();
    </script>
</body>

</html>
```