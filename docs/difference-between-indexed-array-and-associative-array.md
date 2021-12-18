# 索引数组和关联数组的区别

> 原文:[https://www . geesforgeks . org/indexed-array-and-associated-array/](https://www.geeksforgeeks.org/difference-between-indexed-array-and-associative-array/)

一个数组 [](https://www.geeksforgeeks.org/php-arrays/) 是包含一组以相同名称存储的变量的对象集合。所有元素都属于相同的数据类型，即字符串、整数或列表。在索引和[关联数组](https://www.geeksforgeeks.org/associative-arrays-in-php/)的情况下，键是唯一的。

**索引数组:**索引数组是带有数字键的数组。它基本上是一个数组，其中每个键都与它自己的特定值相关联。

**例 1:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Declaring an array
$arr = array(1, 2, 3, 4, 5);

echo('Array : ');

// Print the array
print_r($arr);

?>
```

**Output**

```html
Array : Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
)

```

**示例 2:** 可以使用整数索引值将单个值分配给数组索引值，如下面的代码片段所示。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Declaring an array
$arr = array();

// Assigning values
$arr[0] = 5;
$arr[1] = 6;

print("Array : ");
print_r($arr);

?>
```

**Output**

```html
Array : Array
(
    [0] => 5
    [1] => 6
)

```

[**关联数组**](https://www.geeksforgeeks.org/associative-arrays-in-php/) **:** 关联数组以键值对的形式存储。这种类型的数组是以数字或字符串格式存储键的地方。

**例 1:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Declaring an array
$arr = array(
      "Java" => "Spring Boot", 
      "Python" => "Django", 
      "PHP" => "CodeIgniter"
);

// Assigning values
print("Array : ");
print_r($arr);

?>
```

**Output**

```html
Array : Array
(
    [Java] => Spring Boot
    [Python] => Django
    [PHP] => CodeIgniter
)

```

*数组[键] =值*表达式可用于将单个值指定为数组的组成部分。

**例 2:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php

// Declaring an array
$arr = array();

// Declaring key-value pairs
$arr['Python'] = "Django";
$arr['Java'] = "SpringBoot";
$arr['PHP'] = "CodeIgniter";

print("Array : ");
print_r($arr);

?>
```

**Output**

```html
Array : Array
(
    [Python] => Django
    [Java] => SpringBoot
    [PHP] => CodeIgniter
)

```

**索引数组与关联数组的区别:**

<figure class="table">

| **Index array** | **associative array** |
| The key of the index array is an integer starting from 0. | In the case of associative arrays, the key can be a string. |
| They are like single-column tables. | They are like two columns. |
| They are not maps. | They are called maps. |

</figure>