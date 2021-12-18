# 斗嘴| At 规则

> 原文:[https://www.geeksforgeeks.org/sass-at-rules/](https://www.geeksforgeeks.org/sass-at-rules/)

At-rules 只是一些指示 CSS 在特定条件下如何行为的 CSS 语句。它们以一个**“@”**符号开始，后跟一个标识符，以一个分号(在 SCSS 的情况下)或下一个 CSS 语句(在 SASS 的情况下)结束，这取决于所使用的 [Sass 语法](https://www.geeksforgeeks.org/sass-syntax/)。

**语法:**

## 【CSS】

```html
@identifier(rule);
```

以下是使用的 Sass at 规则列表:

*   **@使用**一起处理来自不同 Sass 样式表的混合、函数和变量。它还将各种不同样式表的 CSS 组合成一个。
*   **@forward** 处理一个 Sass 样式表，并使其混合、函数和变量可用于@use 规则。
*   **@import** 扩展 CSS at-rule 来处理来自其他样式表的样式、混合、函数和变量。
*   **@mixin** 、**包含**使得再次使用样式的章节变得容易。
*   **@函数**定义要在 Sass 表达式中使用的自定义函数。
*   **@extend** 允许选择器相互接收样式。
*   **@在根处**将其中的样式放到 CSS 文档的根处。
*   **@error** 导致编译失败，并显示给定的错误消息，如上例所示。
*   **@warn** 打印警告而不完全停止编译。
*   **@debug** 打印命令用于调试。
*   像 **@if、@每、@for、**和**这样的流量控制规则，而**控制风格的排放数量。

Sass 还为简单的 CSS at 规则提供了某些行为，比如: **@charset** 和 **@namespace。**可以包含[插值](https://www.geeksforgeeks.org/sass-interpolation/)，可以嵌套在样式规则中。其中一些，像 **@media** 、**@ support**，即使不使用插值，也允许在规则本身中直接使用 Sass。

许多 Sass 的额外功能以这些 **at-rules** 的形式出现。

**示例代码:**

## CSS

```html
.error
  border: 1px green
  background-color: black

  &--serious
    @extend .error
    border-width: 3px
```

这将给出以下 CSS 输出:

```html
.error, .error--serious {
  border: 1px green;
  background-color: black;
}
.error--serious {
  border-width: 3px;
}
```