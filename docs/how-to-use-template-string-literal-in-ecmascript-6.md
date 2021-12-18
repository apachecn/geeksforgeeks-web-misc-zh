# 如何在 ECMAScript 6 中使用模板字符串文字？

> 原文:[https://www . geeksforgeeks . org/如何使用-模板-字符串-literal-in-ecmascript-6/](https://www.geeksforgeeks.org/how-to-use-template-string-literal-in-ecmascript-6/)

在本文中，我们将学习**模板文字**。JavaScript 中有不同种类的文字，比如*对象文字*和*布尔文字。*我们还有*字符串*，用单引号“”或双引号“”表示。

从 **ES6 (ECMAScript 6)** 开始，我们有了*模板文字*，由倒勾(`)字符表示。模板文字帮助我们编写干净的代码。也叫**模板串。**

**语法:**

```html
`string text`
```

该模板文字也可以包含占位符。我们可以用美元符号和大括号来表示。

```html
`string text ${expression} string text`
```

通过下面的例子，让我们看看这些模板文字是如何让我们的生活变得简单的。

**示例 1:** 使用带有换行符的字符串的传统方式。

## 超文本标记语言

```html
<script>
    const textMessage = "GFG is the\n" +
    "best place to learn DS";
    console.log(textMessage);
</script>
```

**输出:**

```html
GFG is the
best place to learn DS
```

**示例 2:** 使用模板文字，我们可以在不使用换行符的情况下执行与上面示例相同的操作。相反，我们可以根据需要使用换行符来编写文本。

## 超文本标记语言

```html
<script>
    const textMessage = `GFG is the
    best place to learn DS`;
    console.log(textMessage);
</script>
```

**输出:**

```html
GFG is the
best place to learn DS
```

**示例 3:** 我们还可以将一些文本括在单引号内，它将毫无问题地显示出来。

## 超文本标记语言

```html
<script>
    const textMessage = `GFG is the
    best 'place' to learn DS`;
    console.log(textMessage);
</script>
```

**输出:**

```html
GFG is the
best 'place' to learn DS
```

我们还可以在模板字符串中添加动态内容。这可以通过定义花括号内的变量来实现，花括号前有一个美元符号。

**示例 4:** 在本例中，我们将使用模板文字显示字符串内部的名称。

## 超文本标记语言

```html
<script>
    const name = "User";
    const message = `Hi ${name}, Welcome to the GeeksForGeeks`;
    console.log(message);
</script>
```

**输出:**

```html
Hi User, Welcome to the GeeksForGeeks
```