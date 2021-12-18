# 日期时间不可变创建自可变()函数

> 原文:[https://www . geeksforgeeks . org/datetime imberty-create from mutatable-function/](https://www.geeksforgeeks.org/datetimeimmutable-createfrommutable-function/)

**DateTimeMultible::createFromMultible()**函数是 PHP 中的一个内置函数，用于返回封装给定 DateTime 对象的新的**DateTimeMultible**对象。

**语法:**

> 日期时间不可变日期时间不可变::createFromMutable(DateTime $ object)

**参数:**这个函数接受一个单参数$对象，该对象用于获取要转换为不可变版本的可变*日期时间*对象。

**返回值:**该函数成功返回*日期时间不可变*对象，失败返回假。

**示例 1:** 下面的程序说明了 PHP 中的**datetime imbible::createFromMutable()**函数。

## PHP

```html
<?php

$dateTime = new DateTime("2020-04-12");

var_dump(DateTimeImmutable::createFromMutable($dateTime));

?>
```

**输出:**

```html
object(DateTimeImmutable)#2 (3) {
  ["date"]=>
  string(26) "2020-04-12 00:00:00.000000"
  ["timezone_type"]=>
  int(3)
  ["timezone"]=>
  string(3) "UTC"
}
```

**例 2:**

## PHP

```html
<?php

// Creating a new DateTime::add() object 
$datetime = new DateTime("2019-10-03T10:00:00");

var_dump(DateTimeImmutable::createFromMutable($datetime));

// Creating a new DateTimeImmutable() object 
$datetime = new DateTime(); 

// Initialising year, month and day 
$Year = '2019'; 
$Month = '10'; 
$Day = '03'; 

// Calling the DateTimeImmutable::setDate() function 
$datetime = $datetime->setDate($Year, $Month, $Day);

var_dump(DateTimeImmutable::createFromMutable($datetime));

?>
```

**输出:**

```html
object(DateTimeImmutable)#2 (3) {
  ["date"]=>
  string(26) "2019-10-03 10:00:00.000000"
  ["timezone_type"]=>
  int(3)
  ["timezone"]=>
  string(3) "UTC"
}
object(DateTimeImmutable)#1 (3) {
  ["date"]=>
  string(26) "2019-10-03 20:35:03.000000"
  ["timezone_type"]=>
  int(3)
  ["timezone"]=>
  string(3) "UTC"
}
```

**参考:**[https://www . PHP . net/manual/en/datetime imbervable . createfromutable . PHP](https://www.php.net/manual/en/datetimeimmutable.createfrommutable.php)