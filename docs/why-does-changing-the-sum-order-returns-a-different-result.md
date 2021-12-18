# 为什么改变求和顺序会得到不同的结果？

> 原文:[https://www . geeksforgeeks . org/为什么改变订单总额会得到不同的结果/](https://www.geeksforgeeks.org/why-does-changing-the-sum-order-returns-a-different-result/)

在数学中，加法本质上是联想的。结合律规定求和的结果保持不变，与加数的顺序无关。当加数是整数时，所有编程语言都是如此。但是，当加数是浮点数时，行为略有不同。

今天使用的大多数中央处理器都使用 IEEE 754 二进制浮点标准，当十进制数存储为二进制值时，会引入不准确性。观察求和结果的变化是因为当我们改变顺序时，存储在存储器中的中间值也改变，因此最终结果也改变。让我们考虑下面的例子，它展示了每当订单改变时，如何获得不同的输出。

**例:**

## Javascript

```html
var a = 10.54;
var b = 9.99;
var c = 1.01;

console.log("a+b+c", a+b+c);
console.log("b+c+a", b+c+a);
console.log("b+a+c", b+a+c);
```