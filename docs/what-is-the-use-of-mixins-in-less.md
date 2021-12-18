# Mixins 在 LESS 中有什么用？

> 原文:[https://www . geeksforgeeks . org/mixins in less 的用途是什么/](https://www.geeksforgeeks.org/what-is-the-use-of-mixins-in-less/)

在本文中，我们将了解什么是 LESS 中的 Mixins，并通过示例了解它们的实现和用法。CSS 预处理器是通过使用定义的预处理器规则集生成 CSS 代码的程序&有助于降低 CSS 代码的整体复杂性。LESS 是一个 CSS 预处理器，是 CSS 向后兼容的语言扩展。LESS 中的 Mixins 是一种将一组 CSS 属性从一个规则集包含到另一个规则集的方法，即在同一个文件中多次包含。

例如，假设我们在网页中有多个按钮(假设具有不同的按钮 id/类)，每个按钮包含不同的颜色&具有相似的字体大小和填充属性。现在，如果我们需要为这些按钮编写类似的 CSS 属性，那么我们必须为每个按钮重复代码块多次，因此代码大小变得很长。在 LESS 中混合可以减少和丢弃代码中使用的重复属性。使用 LESS，我们可以在一个名称为“button_basic”的 mixin 中定义所有这些重复属性，并在其中定义所有这些重复属性。

**语法:**

```
// Mixin in LESS

.button_basic{
    font-size: 1em;
    padding: 1em;
    font-family: 'Times New Roman', Times, serif;
}
```

**示例**:在这个示例中，我们使用了上面的 mixin，就像调用其他元素块中的函数一样。

```
/*LESS file */

.button_basic{
    font-size: 1em;
    padding: 1em;
    font-family: 'Times New Roman', Times, serif;
}
.btn1{
    .button_basic();
    background-color: rgb(235, 141, 141);
}
.btn2{
    .button_basic();
    background-color: rgb(94, 94, 230);
}
.btn3{
    .button_basic();
    background-color: violet;
}
```

从上面的代码示例中，我们已经调用了“*”。border-basic* 在“btn1”、“btn2”和“btn3”类中声明的“mixins”。编译上述代码后，它将生成以下本机 CSS 代码。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```
.button_basic {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
}
.btn1 {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
  background-color: #eb8d8d;
}
.btn2 {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
  background-color: #5e5ee6;
}
.btn3 {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
  background-color: violet;
}
```

这是 mixins 在 Less 中的基本用法。现在，让我们了解一些其他的概念，这些概念可以应用于 mixins。

**参数化 mixin:**我们可以通过定义 mixin 顶部的参数来传递 mixin 中的参数。

**语法:**

```
.button_basic(@background_color){
    font-size: 1em;
    padding: 1em;
    font-family: 'Times New Roman', Times, serif;
    background-color: @background_color;
}
```

**示例**:在这里，我们可以调用上面的 mixin，就像其他 mixin 一样，在调用的时候我们把值传递给 mixin 的参数。

```
/*Less Code file*/

.button_basic(@background_color){
    font-size: 1em;
    padding: 1em;
    font-family: 'Times New Roman', Times, serif;
    background-color: @background_color;
}
.btn1{
    .button_basic(rgb(235, 141, 141));

}
.btn2{
    .button_basic(rgb(94, 94, 230));

}
.btn3{
    .button_basic( violet);

}
```

当上面的 LESS 代码被编译后，会产生下面的 CSS 代码:

## 【CSS】

```
.btn1 {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
  background-color: #eb8d8d;
}
.btn2 {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
  background-color: #5e5ee6;
}
.btn3 {
  font-size: 1em;
  padding: 1em;
  font-family: "Times New Roman", Times, serif;
  background-color: violet;
}
```

我们也可以将*默认值*赋予参数化混音，如下图所示:

```
.button_basic(@background_color:red){
   font-size: 1em;
   padding: 1em;
   font-family: 'Times New Roman', Times, serif;
   background-color: @background_color;
}
.button1{
   .button_basic();
}
```

当上述代码编译成 CSS 时，会产生如下代码:

## 【CSS】

```
.button1 {
  font-size: 1em;
  padding: 1em;
  font-family: 'Times New Roman', Times, serif;
  background-color: red;
}
```

在调用上面的 mixins 时，如果我们在调用时没有传递任何值，那么在这些情况下将使用参数的默认值。

**Mixins 中的选择器:**我们也可以使用带有 Mixins 的选择器。下面给出了一个例子:

**语法:**

```
.button_basic(){
   &:hover{
      background-color: white;
  }
}
```

**示例**:在上面的示例中，悬停选择器在 mixins 内部使用，可以从其他元素调用。

```
/*LESS Code file */

.button_basic()
{
  &:hover
  {
      background-color: white;
  }
}
.btn1
{
    .button_basic();
}
```

以上代码编译成 CSS 后，会产生如下代码:

## 【CSS】

```
.btn1:hover {
  background-color: white;
}
```

**！重要关键词:**我们可以用！mixin 旁边的重要关键字，使整个 mixin 变得“重要”。

**示例:**这里有一个示例，当从另一个元素调用时，我们使 mixin 变得很重要。

```
/* Less Code */
.button_basic(){
    font-size: 1em;
    padding: 1em;
    font-family: 'Times New Roman', Times, serif;
  }

.btn2{
    .button_basic() !important;

}
```

当上述代码编译成 CSS 时，会产生如下代码:

## 【CSS】

```
/*CSS code */

.btn2 
{
  font-size: 1em !important;
  padding: 1em !important;
  font-family: 'Times New Roman', Times, serif !important;
}
```

因此，我们已经讨论了 mixin 的使用以及 mixin 在 LESS 中的许多特性。LESS 中的 mixin 特性是编写长 CSS 代码时非常有用的特性之一，在长 CSS 代码中有许多项需要重复。它不仅节省了代码行，而且降低了代码的复杂性。

**参考:**T2**https://lesscss.org/features/#mixins-feature**T5】