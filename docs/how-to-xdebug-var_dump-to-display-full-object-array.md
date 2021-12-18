# 如何 xdebug var_dump 显示全对象/数组？

> 原文:[https://www . geesforgeks . org/how-xdebug-var _ dump-to-display-full-object-array/](https://www.geeksforgeeks.org/how-to-xdebug-var_dump-to-display-full-object-array/)

调试对于开发领域的写作来说是必要的。一旦开发人员必须检查变量的数据，就有可能出现这种情况。开发人员可以打印所有的内容，但是 PHP 本身提供了一种尝试和执行常量和类似检查数据类型的方法。

Xdebug 是提供调试和识别功能的 PHP 扩展。它使用调试协议。Xdebug 将在错误消息中给出堆栈和性能跟踪的正确数据，带有完整的参数来显示用户概述的函数、操作名、文件名、行指示和对成员函数的支持。它包括内存分配和对无限递归的保护。
Xdebug 还提供了 PHP 脚本的识别数据、代码覆盖率分析以及与计算机前端程序交互纠正脚本的能力。Xdebug 还通过 PHP 扩展社区库(PECL)提供——通常发音为“pickle”。

var_dump()函数用于显示几个变量的数据。它操作显示结构化数据，如给定变量的种类和价值。数组和对象平方度量递归探索，值缩进指出结构。
var _ dump–转储关于变量的信息。

**语法:**

```
*void* var_dump( $exp )
```

**参数:**该函数接受单个参数 **$exp** ，该参数保存单个变量或包含任何类型的多个区域分隔变量的表达式。

**返回类型:**该功能没有返回类型。该函数显示关于包含其种类和价格的一个或多个附加表达式的结构化数据。数组和对象被递归探索，其值缩进以指出结构。

**例 1:**

```
<?php
$a = array(1, 2, array("a", "b", "c"));
var_dump($a);
?>
```

**Output:**

```
array(3) {
  [0]=>
  int(1)
  [1]=>
  int(2)
  [2]=>
  array(3) {
    [0]=>
    string(1) "a"
    [1]=>
    string(1) "b"
    [2]=>
    string(1) "c"
  }
}

```

**例 2:**

```
<?php
$b = 3.1;
$c = true;
var_dump($b, $c);
?>
```

**Output:**

```
float(3.1)
bool(true)

```