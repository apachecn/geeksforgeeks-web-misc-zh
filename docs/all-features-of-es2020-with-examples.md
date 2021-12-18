# 带示例的 ES2020 的所有特性

> 原文:[https://www . geesforgeks . org/all-features-of-es 2020-with-examples/](https://www.geeksforgeeks.org/all-features-of-es2020-with-examples/)

ES2020 是 ES(ECMAscript)JavaScript 改进的延续。2020 年，ES 的重要变化如下:

### **1 .斑点〔t1〕**

BigInt 是 JavaScript 中一个新的数值原语。在 BigInt 类型中，您可以存储任意精度的整数。BigInt 可以存储大于 max_safe_integer (2 <sup>53</sup> -1)的数字。在这个特性之前，程序员需要使用一些第三方库，这会导致更多的加载时间，更多的编译时间，更多的解析时间。

**档案名称:index . js**

## 【JavaScript】

```
let max = Number.MAX_SAFE_INTEGER;

console.log(max);
//  9007199254740991

console.log(++max);
//  9007199254740992

console.log(++max);
//  9007199254740992

console.log(++max);
//  9007199254740992

let big = 9007199254740991n;

console.log(big)
//  9007199254740991n

console.log(++big);
//  9007199254740992n

console.log(++big);
//  9007199254740993n

console.log(++big);
//  9007199254740994n 

console.log(typeof big);
//  bigint
```