# JavaScript 中写函数的不同方式

> 原文:[https://www . geesforgeks . org/differential-writing-way-functions-in-JavaScript/](https://www.geeksforgeeks.org/different-ways-of-writing-functions-in-javascipt/)

**什么是函数？**

一个**函数**是一个代码块，它被设计用来执行一个任务，并在被调用时被执行。

用 JavaScript 编写函数有 3 种方法:

*   函数声明
*   函数表达式
*   箭头函数

**1。函数声明:**函数声明是定义函数的传统方式。它在某种程度上类似于我们在其他编程语言中定义函数的方式。我们开始使用关键字*“函数”来声明。*然后我们写函数名，然后写参数。

下面是说明使用*函数声明的例子。*

## java 描述语言

```html
// Function declaration
function add(a, b) {        
    console.log(a + b);
}

// Calling a function
add(2, 3);
```

在定义了一个函数之后，只要需要这个函数，我们就调用它。

**输出:**

```html
5
```

**2。函数表达式:**函数表达式是 JavaScript 中定义函数的另一种方式。这里我们使用一个变量定义一个函数，并将返回值存储在那个**变量**中。

下面是说明使用*函数表达式的例子。*

## java 描述语言

```html
// Function Expression
const add = function(a, b) {
    console.log(a+b);
}

// Calling function
add(2, 3);
```

这里，整个函数是一个表达式，返回值存储在变量中。我们使用变量名来调用函数。

**输出:**

```html
5
```

**3。箭头函数:**箭头函数已经在 **ES6 版本**的 JavaScript 中引入。它用于缩短代码。这里不使用“**功能”**关键字，使用箭头符号。

下面是说明使用*箭头* *功能的例子。*

**示例:**

## java 描述语言

```html
// Single line of code
let add = (a, b) => a + b;

console.log(add(3, 2));
```

与其他方法相比，这将代码缩短为一行。在单行代码中，函数隐式返回。

**输出:**

```html
5
```

**注意:**当需要包含多行代码时，我们使用括号。此外，当括号中有多行代码时，我们应该显式地编写 return 来返回函数的值。

**示例:**

## java 描述语言

```html
// Multiple line of code
const great = (a, b) => {
    if (a > b)
        return "a is greater";
    else
        return "b is greater";
}

console.log(great(3,5));
```

**输出:**

```html
b is greater
```