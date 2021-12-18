# 一美元的差价！= $b 和$a！== $b

> 原文:[https://www . geeksforgeeks . org/a-b 和-a-b 之间的差异/](https://www.geeksforgeeks.org/difference-between-a-b-and-a-b/)

**$a！=$b**

这个算子也被称为不等式算子。它用于检查两个操作数的相等性，但是，操作数的类型不匹配。例如，如果两个操作数的值相同，整数类型变量就相当于浮点数。它是一个二元运算符。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Assigning values to the 
// variables a and b 
$a = 5;
$b = 5.0;

if($a != $b) {
    echo("Both operands are not Equal");
}
else {
    echo("Both operands are Equal");
}

?>
```

**Output**

```html
 Both operands are Equal
```

**$a！==$b**

这是非身份运算符。它用于检查两个操作数的相等性，然而，操作数的类型也匹配。例如，无论两个操作数的值如何，整数类型变量都不等同于浮点数。它是一个二元运算符。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Assigning the values of
// variables a and b 
$a = 5;
$b = 5.0;

if($a !== $b) {
    echo("Both operands are not same");
}
else {
    echo("Both operands are same");
}

?>
```

**Output**

```html
Both operands are not same
```

**区别！=还有！==话务员:**

<figure class="table">

| **！=** | **！= =** |
| Returns true if the values of the two operands are equal. | Returns true if the values and and data types of the two operands are equal. |
| It is called inequality operator. | It is called a non-identity operator. |
| Null values are considered equivalent. | Null values should belong to the same data type. |

</figure>

**示例:**下面的代码片段以简单的方式说明了这两个运算符的区别。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Assigning values to the 
// variables a and b 
$a = null;
$b = FALSE;

// != operator
if($a != $b) {
    echo("Both operands are not equal (Only Value)\n");
}
else {
    echo("Both operands are equal (Only Value)\n");
}

// !== operator
if($a !== $b) {
    echo("Both operands are not equal (Value and Data Types)");
}
else {
    echo("Both operands are equal (Value and Data Types)");
}

?>
```

**Output**

```html
Both operands are equal (Only Value)
Both operands are not equal (Value and Data Types)
```