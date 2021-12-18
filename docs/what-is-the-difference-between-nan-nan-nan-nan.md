# 有什么区别(NaN！= NaN) & (NaN！== NaN)？

> 原文:[https://www . geesforgeks . org/什么是-nan-nan-nan-nan/](https://www.geeksforgeeks.org/what-is-the-difference-between-nan-nan-nan-nan/)

**NaN** 在大多数编程语言中的意思是“不是数字”。它属于数字数据类型(int、long、short 等)。它表示不能解释为有限值的数值。那是一个无法定义它的价值。NaN 的使用相当罕见。NaN 是全局对象和数字对象的属性。它主要用于检查用户的数字输入，从而使程序无错误。
在 JavaScript 中，这个问题就产生了，NaN 有什么区别！=NaN 和 NaN！==NaN？这个问题的答案是，出于 NaN 的目的，两者产生了相同的答案。两者都会导致真。这是由于 NaN 的变量值。NaN 不等于 NaN。

*   **代码 1:**

## java 描述语言

```html
<script type="text/javascript">
var value1 = Math.sqrt( -0.5 );
        document.write("First Value : " + value1 );
var value2 = Math.sqrt( -49 );
        document.write("<br />Second Value : " + value2 );
var boo= value1!==value2
        document.write("<br />Nan!==Nan: "+boo);
var boo= value1!=value2
        document.write("<br />Nan!=Nan: "+boo);
</script>                   
```

*   **输出:**

```html
First Value : NaN
Second Value : NaN
Nan!==Nan: true
Nan!=Nan: true
```

*   **代码 2:** 现在，在第一个例子中，我们清楚地知道，我们不能计算负数的平方根，因此它导致 NaN。我们可以清楚地看到输出。

## java 描述语言

```html
<script type="text/javascript">
var x="Hello";
    document.write("<br />"+ isNaN(x) + "<br />");
var y="World";
    document.write(isNaN(y)+"<br />");
document.write(y!==x);
document.write("<br />");
document.write(y!=x);
</script>                   
```

*   **输出:**

```html
true
true
true
true
```

现在有两种方法可以检查所需的输入是否为 NaN。第一种检查方法是 **isNaN()** 另一种是[T3】number . isNaNT5**()**。第二种方法仅适用于数值数据类型。第一种方法在代码 2 中演示。字符串变量是非数字的，因此您将得到真实的输出(即它是 NaN)。
**区别 NaN！=Nan 和 Nan！==NaN:**](https://www.geeksforgeeks.org/number-isnan-javascript/) 

*   主要区别不在 NaN 上，而是在运算符 single = compare(NaN！=NaN)只有对每个 NaN 不相等的值
*   在 NaN！= =南比较值的类型也因此区别现在很明显了。