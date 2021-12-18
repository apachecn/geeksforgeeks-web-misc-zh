# SASS |风格规则

> 原文:[https://www.geeksforgeeks.org/sass-style-rules/](https://www.geeksforgeeks.org/sass-style-rules/)

就像 CSS 一样，样式规则也是 SASS 的基础。它的使用类似于 CSS。使用选择器选择要设置样式的元素，然后声明其属性，这会进一步影响这些元素的外观。

**例:**
萨斯码:

```htmlhtml
.header
  padding: 3px 10px
  font-size: 40px
  font-family: sans-serif
  border: 2px solid green
```

这将导致以下 CSS 输出:

```htmlhtml
.header{
  padding: 3px 10px;
  font-size: 40px;
  font-family: sans-serif;
  border: 2px solid green;
}

```

但是，这样做的好处只是在重复。SASS 希望让你的代码变得简单，而不仅仅是重复。因此，在 SASS 中，您可能会避免一次又一次地重复相同的选择器。你可以很容易地把一个风格规则写在另一个里面。SASS 自动完成你想要的工作。SASS 的这个特性被称为[嵌套](https://www.geeksforgeeks.org/sass-nesting/)。

**示例:** Sass 代码

```htmlhtml
navbar
  ul
    padding: 2px
    list-style: square

  li
    display: inline-block

  a
    display: block
    padding: 4px 10px
    font-family: sans-serif
```

这将导致以下 CSS 输出:

```htmlhtml
navbar ul{
    padding: 2px;
    list-style: square;
}
navbar li{
    display: inline-block;
}
navbar a{
    display: block;
    padding: 4px 10px;
    font-family: sans-serif;
}

```

嵌套规则非常有用，但有时它们会创建大量的 CSS。嵌套越多，生成 CSS 所需的带宽就越多，浏览渲染时要做的工作也就越多。因此选择器必须保持浅。

**一些更有用的例子:**嵌套规则对于处理选择器列表非常有用。选择器列表是指用逗号分隔的选择器列表。这些被编译为以下示例:

**SASS 代码:**

```htmlhtml
.abc, .def
  ul, p
    padding: 2px
    font-family: sans-serif
    border: 1px
```

这将导致以下 CSS 输出:

```htmlhtml
.abc ul, .abc p, .def ul, .def p {
    padding: 2px;
    font-family: sans-serif;
    border: 1px
}

```

**插值:**为了将变量和函数等值插入选择器，可以使用[插值](https://www.geeksforgeeks.org/sass-interpolation/?ref=rp)。插值在创建[混合](https://www.geeksforgeeks.org/sass-mixin-and-include/)时非常有用，因为它允许您从用户提供的参数中生成选择器。

**示例:** Sass 代码

```htmlhtml
@mixin full-form($name, $glyph) 
    span.full-form-#{$name} 
    font-family: sans-serif
    padding: 4px
    border: 10px
    content: $glyph
@include full-form("GFG", "GeeksForGeeks")
```

这将导致以下 CSS 输出:

```htmlhtml
span.full-form-GFG {
  font-family: sans-serif;
  padding: 4px;
  border: 10px;
  content: "GeeksForGeeks";
}

```

Sass 只在插值完全解决后分析选择器，这意味着您可以安全地使用插值来生成选择器的任何部分，而不用担心它不起作用。