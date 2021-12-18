# 异常::getMessage 和异常::getLine 的区别

> 原文:[https://www . geesforgeks . org/exceptionetmessage 和-exception-getline 之间的差异/](https://www.geeksforgeeks.org/difference-between-exceptiongetmessage-and-exception-getline/)

**异常::getMessage:**PHP 语言中的 *getMessage e* 异常基本上是程序员用来知道异常消息的。这意味着每当代码中出现异常情况时，为了知道确切的含义以及该异常是关于什么的，就使用了这个函数。这个函数对程序员来说非常有用，因为它帮助他/她找到异常的真正本质，并使用这些有价值的信息编写正确的异常处理代码。

**示例:**在下面的代码中， **getMessage()** 将获得异常消息。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
    try {
        throw new Exception(" error message");
    } catch(Exception $e) {
        echo $e->getMessage();
    }
?>
```

**Output**

```html
 error message
```

**异常::getLine:**PHP 语言中的 *getLine* 异常基本上是程序员为了知道对应的异常发生在哪一行而使用的。这意味着每当代码中出现异常时，这个特殊的 **getLine()** 函数可以找出发生异常的代码的确切位置。当我们有大量的代码并且无法找到特定异常的位置时，这个功能会有所帮助。

**示例:**在下面的代码中， **getLine()** 函数将获得发生异常的行。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
    try {
        throw new Exception(" error message");
    } catch(Exception $e) {
        echo "The exception has occured on line: " 
             . $e->getLine();
    }
?>
```

**Output**

```html
The exception has occured on line: 3
```

**异常的区别::getMessage 和 Exception::getLine:**

<figure class="table">

| **-什么::getMessage** | **-什么* get line〔t1〕** |
| This function returns an exception message. | This function returns the position of the row where the exception occurred. |
| It returns an exception message in string format. | Returns the line number in integer format. |
| It is helpful for all types of code. | It is most helpful in massive code ie. Code containing multiple lines. |

</figure>