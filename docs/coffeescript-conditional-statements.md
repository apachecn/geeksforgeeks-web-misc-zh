# 咖啡脚本条件语句

> 原文:[https://www . geesforgeks . org/coffee script-conditional-statements/](https://www.geeksforgeeks.org/coffeescript-conditional-statements/)

**咖啡脚本**编程语言用于编写更简单的语法，在执行之前编译成 JavaScript。在任何编程语言中，条件在特定序列的代码执行中起着重要作用。在本文中，我们将看到各种条件语句，如 If、Else、Else If 等。咖啡脚本支持条件语句的语法。

在 CoffeeScript 中，没有使用括号和花括号。它的函数或多行条件语句都用缩进来分隔。

**If 语句:**如果我们想在执行其他语句之前测试一个条件，那么我们使用 If 语句。在 CoffeeScript 中，“if”语句是使用“If”关键字编写的。

**语法:**

```html
if condition
   statement
```

**例:**

## 咖啡脚本

```html
number = 10; 
if number>0       
   console.log("Number is positive") 
console.log("Outside if block")
```

**输出:**在上面的代码中，“if”语句因为持有真值而被执行，它里面的所有指令都会被执行。一旦“如果”块被执行，它将在条件块之外执行进一步的条件。

```html
Number is positive
Outside if block
```

**If Else 语句:**我们不能每隔一个条件使用 If 语句。除了“如果”条件，还可以有其他条件。如果“if”条件不成立，则需要执行另一条指令。图中出现了“其他人”。让我们看看如何一起使用 *if* 和 *else* 。

**语法:**

```html
if condition1
   statement 1
else 
   statement 2
```

**例:**

## 咖啡脚本

```html
number = -10; 
if number>=0       
   console.log("Number is positive")     
else       
   console.log("Number is negative")
```