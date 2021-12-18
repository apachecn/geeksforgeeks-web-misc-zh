# 空合并运算符有什么用？

> 原文:[https://www . geeksforgeeks . org/什么是空-合并-运算符/](https://www.geeksforgeeks.org/what-is-the-use-of-null-coalesce-operator/)

PHP 7 引入了一个空合并操作符。？语法。如果该运算符的值已设置且不为空，则该运算符返回其第一个操作数，否则将返回其第二个操作数。这个操作符可以用在程序员想要从用户那里得到一些输入的场景中，如果用户跳过了输入，那么必须给变量分配一些默认值。

**空值合并运算符的用法:**

*   It is used to replace ternary operator with PHP [**isset ()**](https://www.geeksforgeeks.org/php-isset-function/) **function .**
***   Can be used to write short expressions.*   It reduces the complexity of the program.*   Even if the first operand does not exist, no error will be thrown.**

****示例:**如果分配了 *$name* 和 *$age* 的值，则将打印分配的值，否则表达式中提供的默认值将作为值分配给这些变量。**

## **PHP**

```
<?php

  echo 'Output when values are not Set'."\xA<br>";

  // Using ternary operator
  $name = isset($_GET['name']) ? $_GET['name'] : 'Default'; 
  echo 'Name : '.$name."\xA<br>";

  // Using Null Coalescing
  $age = $_GET['age'] ?? 'Default';   
  echo 'Age : ' .$age."\xA \xA<br><br>";

  echo 'Output when values are Set'."\xA<br>";

  $_GET['name']='GFG';
  $_GET['age']='18';

  // Using ternary operator
  $name = isset($_GET['name']) ? $_GET['name'] : 'Default'; 
  echo 'Name : '.$name."\xA<br>";

  // Using Null Coalescing
  $age = $_GET['age'] ?? 'Default'; 
  echo 'Age : ' .$age;

?>
```

****输出**

```
Output when values are not Set
Name : Default
Age : Default

Output when values are Set
Name : GFG
Age : 18
```**