# 在 LESS 中操作有什么用？

> 原文:[https://www . geesforgeks . org/什么是无操作使用/](https://www.geeksforgeeks.org/what-is-the-use-of-operations-in-less/)

与许多编程语言类似， **LESS** 也提供类似**加法(+)** 、**减法(-)** 、**除法(/**)和**乘法(***)等算术运算。如果使用得当，这些操作器可以让我们的工作变得更加容易。它就像在样式表中做基础数学一样简单，可以应用于任何变量、数字甚至颜色。使用这些操作符，我们的工作会减少，变得非常快。

让我们通过下面的例子更好地理解这一点。

**示例:**首先我们将创建一个 LESS 文件(扩展名为。更少)。

## 无演示

```
@var : 10px;
.class1 {
    font-size: @var * 8;
    color: red;
}
.class2 {
    font-size: @var + 20;
    color: green;
}
```

使用下面的命令，我们可以将*无演示*编译成 CSS。

```
lessc demo.less demo.css
```

**CSS 输出:**我们得到了一个相当于下面的 CSS 文件。

## 无演示

```
.class1 {
  font-size: 80px;
  color: red;
}

.class2 {
  font-size: 30px;
  color: green;
}
```

现在，让我们创建一个 HTML 文件来尝试这个 CSS 代码。

## index.html

```
<!DOCTYPE html>
<html>
  <head>
    <title>Operations in LESS</title>
    <link rel="stylesheet" 
          type="text/css" href="demo.css" />
  </head>
  <body>
    <p class="class1">GeeksforGeeks</p>

    <p class="class2">Welcome to GFG</p>

  </body>
</html>
```

**输出:**

![](img/a1a7086cd19c4ba52babe4c1b3e0b79e.png)