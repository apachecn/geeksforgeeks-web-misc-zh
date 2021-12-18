# Chrome 控制台中为什么{} + {}不再是 NaN？

> 原文:[https://www . geesforgeks . org/why-is-不再-nan-in-chrome-console/](https://www.geeksforgeeks.org/why-is-no-longer-nan-in-chrome-console/)

***什么是网络控制台？***

现代网络浏览器内置了开发工具，可以与 JavaScript 和其他网络技术协同工作。这些工具包括类似于外壳接口的控制台，以及检查文档对象模型、调试和分析网络活动的工具。

作为 JavaScript 开发过程的一部分，开发人员通常使用控制台来记录信息，这也允许您与网页进行交互。关于 web 控制台以及如何运行的更多详细信息，可以访问[这里的](https://www.geeksforgeeks.org/console-in-javascript/#:~:text=In%20javascript%2C%20the%20console%20is,%2B%20Option%20%2B%20K%20for%20Mac.)。

**在 JavaScript 中加法是如何进行的？**T3】

在 JavaScript 中，加法只能在数字和字符串上执行，所有其他值都被转换为这两种类型中的任何一种。JavaScript 中有两种值-

*   **Primitive** -undefined, empty, Boolean, number, string
*   **Object** -Arrays and functions

**我们来了解一下加法的一般规律:**

因此，考虑给定的表达式

```html
var result = value 1 + value 2
```

*   If value 1 or value 2 is a string, then the result will be a string and the output will be the concatenation of value 1 and value 2;
*   Otherwise, the result is converted into a number, and the sum of values 1 and 2 is output.

**例:**

```html
> var value1 = “hello”  
> var value2 = 123 
> var result = value1 + value2 
> console.log(result)
Output : hello123

> typeof(result) 
Output : “String”

> var result = value1 + value1
> console.log(result)
Output : 246

> typeof(result) 
Output : “number”

```

**一些更期待的结果:** 增加两个空阵:

```html
> var result = []+[]
> console.log(result)
Output :
> typeof(result) 
Output : "string"
Hence the result of []+[] is the concatenation of two empty strings.
```

**JavaScript 对象文字:** 这是一种使用{ }个括号创建对象的简单方法。对象可以在{ }中包含逗号分隔的键-值对，其中键是属性或方法名，值是任何数据类型或函数的属性值。

**语法:**

```html
var <object-name> = { key1: value1, key2: value2,... keyN: valueN};
```

**添加字符串和对象:**

```html
> var result = []+{}
> console.log(result) 
Output : [object Object]
> String({})
Output:'[object Object]'
```

**解释:**因此，在上面的例子中，一个空对象被转换成字符串，产生以下结果。因此，通过连接“”和“[对象对象]”来创建结果。

**一些比较有趣的结果:** 看看下面:

**解释:**这里，JavaScript 将第一个{}解释为一个空的代码块，并忽略它。结果 NaN 是通过计算+ {}计算出来的。这里的加号(+)不是二进制加法运算符，而是一元前缀运算符，它将其操作数转换为数字，方式与 number()相同。例如:

> >+
> 
> 【10】
> 
> **输出:** 10

但是，问题出现了**为什么 javascript 将第一个{}解释为空代码块？**

这是因为整个输入被解析为一条语句，并且该语句的第一个大括号被解释为开始一个代码块。因此，这可以通过强制将输入解析为如下表达式来解决:

> > ({} + {})
> 
> **输出:**'【对象对象】【对象】'

现在，Chrome dev 工具自动将所有以{开始，以}结束的内容包装在一对隐式括号[(参见代码)](https://chromium.googlesource.com/chromium/src.git/+/4fd348fdb9c0b3842829acdfb2b82c86dacd8e0a%5E!/#F2)中，以强制将其求值为表达式。

因此{}+{}在 chrome 控制台和现在的大多数现代浏览器中不再是 NaN。