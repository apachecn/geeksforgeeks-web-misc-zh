# SASS |数值运算符

> 原文:[https://www.geeksforgeeks.org/sass-numeric-operators/](https://www.geeksforgeeks.org/sass-numeric-operators/)

Sass 支持标准的数学数值运算符。它们可以在兼容的单位之间自动转换，就像分钟可以加上秒一样，它们会自动转换。

数字运算符:

*   <expression>**+** <表达式>运算符将两个值或表达式相加，或者我们可以说将第一个值加到第二个值上。</expression>
*   <expression>**–**<表达式>运算符从第二个值中减去**第一个值。这一点需要记住。**</expression>
*   <expression>***** <表达式>运算符将两个值相乘。</expression>
*   <expression>**/** <表达式>运算符将第一个值除以第二个值。</expression>
*   <expression>**%** <表达式>运算符返回第一个值除以第二个值的余数。它也被称为**模运算符。**</expression>

**示例:**

*   ```html
    @debug 20px + 10px
    ```

    **输出:** 30px

*   ```html
    @debug 5s - 20s
    ```

    **输出:**15 秒

*   ```html
    @debug 10px * 2px
    ```

    **OUTPUT:** 20px*px(本文后面会介绍 **px*px**

*   ```html
    @debug 10px / 2px
    ```

    **输出:** 5px

*   ```html
    @debug 2in / 5px
    ```

    **输出:** 0.0208 (1in == 96px)

*   **无单位数**可以和任意单位数一起使用。

**示例:**

*   ```html
    @debug 20px + 7
    ```

    **输出:** 27px

*   ```html
    @debug 4s * 10
    ```

    **输出:** 40s

*   不同的数字或者你可以说不相容的单位不能被加、减或用于模运算符。

**示例:**

*   ```html
    @debug 10s - 5px
    ```

    **输出:** *错误:不可进单位 s 和 px*

**一元运算符:**

也可以使用 **+和–**作为一元运算符，其中需要一个简单的表达式。

*   + <expression>返回值而不改变。</expression>
*   –<expression>返回负值。</expression>

**示例:**

*   ```html
    @debug +(5s + 4s)
    ```

    **输出:**9 秒

*   ```html
    @debug -(6s + 3s)
    ```

    **输出:** -9s

*   ```html
    @debug -(3s - 4s)
    ```

    **输出:** -1s

**单位:**

Sass 有很强的能力根据日常生活(现实生活)中的使用来操纵这些单元。这意味着当两个数相乘时，它们的单位与值相乘，在除法的情况下也会发生同样的情况。通过这些**例子，你会了解更多:**

*   ```html
    @debug 4px * 6px
    ```

    **输出:** 24px*px

*   ```html
    @debug 10px/2s
    ```

    **输出:** 5px/s

*   ```html
    @debug 10px * 4s * 2em / 2deg
    ```

    **输出:** 40 像素*秒*电磁/度

*   ```html
    $pixels-per-second : 10px/s
    @debug $pixels-per-second
    ```

    **输出:** 10px/s

*   ```html
    @debug 1/$pixels-per-second
    ```

    **输出:** 0.1s/px

    就像这样，如果它们是兼容的，并且是分开的，那么这些单元就会被取消:

*   ```html
    @debug 1in / 96px
    ```

    **输出:** 1

**实际执行:**

以上操作符可以让 CSS 工作起来轻松快捷。

**示例:**

你不需要提供显示速度。在每个组件中，你创建了一个 Sass，它为你想要的每个组件提供了 CSS。

**萨斯码:**

```html
$speed: 1s/50px;

@mixin show($start, $stop) {
  left: $start;
  transition: left ($stop - $start) * $speed;

  &:hover {
    left: $stop;
  }
}

.navbar {
  @include show(5px, 10px);
}

.button {
  @include show(2px, 5px);
}
```

这将自动为您提供以下 CSS 代码:

```html
.navbar {
  left: 5px;
  transition: left 0.1s;
}
.navbar:hover {
  left: 10px;
}

.button {
  left: 2px;
  transition: left 0.06s;
}
.button:hover {
  left: 5px;
}

```