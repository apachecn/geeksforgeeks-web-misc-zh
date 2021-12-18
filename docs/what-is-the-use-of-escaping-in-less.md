# 在 LESS 里逃跑有什么用？

> 原文:[https://www . geesforgeks . org/less 中转义有什么用/](https://www.geeksforgeeks.org/what-is-the-use-of-escaping-in-less/)

在本文中，我们将了解 LESS 中转义的概念&如何在将生成相应 CSS 代码的 LESS 代码中实现和使用它。通过使用 CSS 预处理器语言，即 LESS，这有助于降低编写 CSS 的代码复杂性。在 LESS 中转义，帮助我们使用任意字符串作为 CSS 属性或值。人们基本上可以称它为变量，但转义有很大不同。与变量不同，在变量中我们只能存储值，在转义中，我们可以在任何字符串中存储完整的属性。

**语法:**

```
@name : ~ “ .. ”
```

**示例 1:** 本示例使用转义功能根据屏幕宽度渲染 CSS。

```
/*LESS Code file*/

@mediacondition : ~"min-width:600px";
.content{
   font-size: 1em;
   @media (@mediacondition){
      background-color: gold;
   }
}
```

**输出**:代码编译为原生 CSS 后，会生成如下 CSS 文件。

## CSS

```
/* CSS code */
.content {
  font-size: 1em;
}
@media (min-width:600px) {
  .content {
    background-color: gold;
  }
}
```