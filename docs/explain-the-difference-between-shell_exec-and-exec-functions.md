# 解释 shell_exec()和 exec()函数的区别

> 原文:[https://www . geesforgeks . org/explain-shell _ exec-和-exec-functions/](https://www.geeksforgeeks.org/explain-the-difference-between-shell_exec-and-exec-functions/)

在本文中，我们将学习 PHP 中的 shell_exec() & exec()函数。我们知道，为了在系统中执行一个命令，我们需要相应操作系统的外壳，但是如果我们需要在像 PHP 这样的编程语言的帮助下执行同一个命令，那么我们使用这两个函数。我们使用这两个函数中的任何一个，但是它们在输出方面有所不同，它们将在成功执行后给出。请参考 [PHP | shell_exec() vs exec()函数](https://www.geeksforgeeks.org/php-shell_exec-vs-exec-function/)。

**shell_exec()函数:**shell _ exec()函数是 PHP 中的一个内置函数，用于通过 shell 执行命令，并将完整的输出作为字符串返回。shell_exec 是 backtick 运算符的别名，用于*nix。如果命令失败，它将返回空值，并且这些值对于错误检查是不可靠的。当 PHP 在安全模式下运行时，该函数被禁用。

**语法:**

```
string shell_exec( $cmd )
```

**参数:** shell_exec()函数只传递一个参数($cmd)，因为它保存要执行的命令。

**返回值:**返回执行的命令，如果出现错误则返回空。

**例 1:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php

// Command 
$command = "DATE";

// Passing the command to the function
$cmd_output = shell_exec($command);

echo $cmd_output;
?>
```

**输出**

```
The current date is 08-07-2021\. Enter the new date: (dd-mm-yy)
```

**例 2:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php

// Command 
$command = "TIME";

// Passing the command to the function
$cmd_output = shell_exec($command);

echo $cmd_output;
?>
```

**输出:**

```
The current time is: 21:05:01.82\. Enter the new time: 
```

**exec()函数:**exec()函数是 PHP 中的一个内置函数，用于执行外部程序并返回输出的最后一行。如果没有命令正常运行，它也会返回空值。它给 wrt shell_exec()函数的输出不同。它执行该命令，并以数组的形式给出该命令的所有输出，它还提供了一些额外的信息，我们可以使用这些信息来检查该命令是否成功执行。

**语法:**

```
string exec( $command, $output, $return_var )
```

**参数:**该功能将接受三个参数:

*   **$command:** 用于保存要执行的命令。
*   **$output:** 用于指定将使用命令的每一行输出填充的数组。
*   **$return_var:** 该参数与输出参数一起出现，然后它返回将被写入该变量的已执行命令的状态。

**返回值:**返回执行的命令。

**例 1:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php

// Command to be executed in the shell
$command = "DATE";

// Calling exec function 
exec($command, $output_array, $cmd_status);

echo "Command status - ".$cmd_status." <br><br>";
echo var_dump($output_array)

?>
```

**输出:**

```
Command status - 1

array(2) { [0]=> string(31) "The current date is: 08-07-2021" 
           [1]=> string(30) "Enter the new date: (dd-mm-yy)" } 
```

**例 2:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php

// Command to be executed in the shell
$command = "TIME";

// Calling exec function 
exec($command, $output_array, $cmd_status);

echo "Command status - ".$cmd_status." <br><br>";
echo var_dump($output_array)

?>
```

**输出:**

```
Command status - 1

array(2) { [0]=> string(32) "The current time is: 21:38:09.81" 
           [1]=> string(19) "Enter the new time:" }
```

**shell _ exec()与 exec()的区别函数:**

<figure class="table">T20】1。

| 

#### shell _ exec()

 | 

#### 执行（）

 |
| --- | --- |
| shell _ exec()函数是 PHP 中的一个内置函数，用于通过 shell 执行命令，并将完整的输出作为字符串返回。 | exec()函数是 PHP 中的一个内置函数，用于执行外部程序，并返回输出的最后一行。如果没有命令正常运行，它也会返回空值。 |
| 2。 | shell _ exec()函数以字符串形式提供完整的输出。 | exec()函数可以以数组的形式提供指定为第二个参数的所有输出。 |
| 3。 | 当出现错误或程序不产生输出时，shell_exec()函数可以为这两种情况返回 null。 | exec()函数只有在没有命令正确执行的情况下才能返回 null。 |

</figure>