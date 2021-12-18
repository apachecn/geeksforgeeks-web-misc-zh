# 如何移除 foreach 循环中的数组元素？

> 原文:[https://www . geesforgeks . org/如何移除 foreach 循环中的数组元素/](https://www.geeksforgeeks.org/how-to-remove-an-array-element-in-a-foreach-loop/)

使用 **[unset()函数](https://www.geeksforgeeks.org/php-unset-function/)** 移除 foreach 循环中的数组元素。unset()函数是 PHP 中的一个内置函数，用于取消指定变量的设置。这个函数的行为取决于不同的事情。如果从任何用户定义的函数内部调用该函数，那么它会取消与内部变量相关联的值，而保留在外部初始化的值。

**语法:**

```
unset( $variable )
```

**返回值:**该函数不返回值。

以下示例使用 unset()函数移除 foreach 循环中的数组元素。

**例 1:**

```
<?php

// Declare an array and initialize it
$Array = array(
    "GeeksForGeeks_1", 
    "GeeksForGeeks_2", 
    "GeeksForGeeks_3"
);

// Display the array elements
print_r($Array);

// Use foreach loop to remove array element
foreach($Array as $k => $val) {
    if($val == "GeeksForGeeks_3") {
        unset($Array[$k]);
    }
}

// Display the array elements
print_r($Array);

?>
```

**Output:**

```
Array
(
    [0] => GeeksForGeeks_1
    [1] => GeeksForGeeks_2
    [2] => GeeksForGeeks_3
)
Array
(
    [0] => GeeksForGeeks_1
    [1] => GeeksForGeeks_2
)

```

**例 2:**

```
<?php

// Declare an array and initialize it
$Array = array(
    array(0 => 1),
    array(4 => 10),
    array(6 => 100)
);

// Display the array elements
print_r($Array);

// Use foreach loop to remove 
// array element
foreach($Array as $k => $val) {
    if(key($val) > 5) {
        unset($Array[$k]);
    }
}

// Display the array elements
print_r($Array);

?>
```

**Output:**

```
Array
(
    [0] => Array
        (
            [0] => 1
        )

    [1] => Array
        (
            [4] => 10
        )

    [2] => Array
        (
            [6] => 100
        )

)
Array
(
    [0] => Array
        (
            [0] => 1
        )

    [1] => Array
        (
            [4] => 10
        )

)

```