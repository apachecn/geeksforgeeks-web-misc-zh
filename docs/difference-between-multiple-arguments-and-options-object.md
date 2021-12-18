# 多个参数和选项对象的区别

> 原文:[https://www . geeksforgeeks . org/多参数和选项之间的差异-对象/](https://www.geeksforgeeks.org/difference-between-multiple-arguments-and-options-object/)

**多个参数:**Arguments 对象是一个类似数组的对象，表示调用函数时传递的参数。这个类似数组的对象没有数组原型链，因此它不能使用任何数组方法。它有长度属性，但没有像 [forEach()](https://www.geeksforgeeks.org/javascript-array-foreach/) 和 [map()](https://www.geeksforgeeks.org/javascript-array-map-method/) 方法那样的数组内置方法。
**功能:**

*   Javascript 中的参数通过值传递。这个函数只知道值，不知道参数的位置。
*   Javascript 中的**参数长度**取决于调用参数，而不是函数签名。
*   您可以使用**参数。长度**来确定在给定的函数调用期间传入了多少个参数。
*   代码可读性最大。

**用法:**

*   **参数。被调用方:**参数所属的当前正在执行的函数的引用。
*   **参数长度:**传递给函数的参数数量。
*   **参数.调用者:**对调用当前正在执行的函数的函数的引用。
*   **参数[@ @迭代器]:** 返回一个新的数组迭代器对象，该对象包含参数中每个索引的值。

**示例:**这是 javascript 中多个参数的示例。实际上参数不像数组，除了[长度](https://www.geeksforgeeks.org/length-vs-length-java/)之外，它不遵循数组属性。我们可以使用函数的所有类型的输入作为多个参数。在函数中，我们可以传递多个参数，但是很难将命名参数作为多个参数传递。

*   **节目:**

## java 描述语言

```html
<script>
// Example of arguments of two
// number a and b.
function args(){ 

    // Using for loop
    //  It can use length method
    for(var i = 0; i < arguments.length; i++) {
        console.log(arguments[i]);   
    }
}

args(1, 3);
</script>
```

*   **输出:**

```html
1
2
```

**选项对象:**选项对象是将命名参数传递给函数的常见模式。当一个函数有两个或多个参数时，我们可以使用 options 对象。对于具有四个或更多参数的函数，options 对象是一个不错的选择。一个函数有一个或两个参数，我们希望将来添加更多的参数，这样我们就可以使用 options 对象，而不是在以后重写代码。
options 对象不同于多个参数，因为多个参数可以接受多种类型的参数，例如 int、float、char、string…等，而 options 对象只能接受像 AlertIcon 等命名参数。
**特色:**

*   该功能最多可接受 34 个参数，所有参数都是可选的。
*   使用“选项作为对象”的方法将是最好的。你不必担心属性的顺序。

**用法:**

*   如果你有四个以上的参数。
*   至少有一个参数是可选的。
*   想知道参数函数是什么，感觉很复杂。

**例:**

*   **节目:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Option object</title>

    <script type="text/javascript">
        var courses = ['HTML', 'CSS',
                'JavaScript', 'Bootsrtap'];

        function courselist() {
            var countryList =
                document.getElementById ("course");

            for (var i = 0; i < courses.length; i += 1) {

                // Option (text, value)
                var courseOption =
                    new Option (courses[i], courses[i+1]);

                countryList.options.add (courseOption);
            }
        }
    </script>
</head>

<body onload="courselist()">
    <select id="course"></select>
</body>

</html>      
```

*   **输出:**

```html
A dropdown menu of available courses
```

**多个自变量与选项对象的区别:**

<figure class="table">

| Multiple independent variables | Option object |
| --- | --- |
| Many independent variables are required. | Options objects are mostly used to name parameters. |
| After implementation, you can add no more parameters without rewriting. | After implementation, more parameters can be added without rewriting. |
| It has index attributes like arrays, for example, parameters have indexes like [0,1,2,3 …]. | There is no such index property as array. |
| Is passed by value. | Pass by reference. |
| It can be used for any number of parameters, but it can be used for a smaller number of parameters except optional parameters. | Can be used for more than four parameters, at least one of which is optional. |

</figure>