# 咖啡脚本|声明

> 原文:[https://www.geeksforgeeks.org/coffeescript-statements/](https://www.geeksforgeeks.org/coffeescript-statements/)

CoffeeScript 的语法比 JavaScript 更简单，如果你有 JavaScript 的知识，很容易学会。它避免使用分号、大括号和变量声明。

**CoffeeScript 语句:**coffee script 的语句不以分号(；).在这种语言中，一个新行被 CoffeeScript 编译器视为一个单独的语句。我们举个例子来理解一下。

**示例:**

```html
Name = “Geek”
Age = 19

Console.log Name
Console.log Age
```

**输出:**

```html
Geek
19
```

Console.log()是一个用 JavaScript 在控制台上打印结果的函数，但是在 CoffeeScript 中，我们只使用 console.log，不使用任何括号。同样，两个语句可以写成一行，用分号分隔，如下所示:

**示例:**

```html
Name = “Geek” ; Age = 19

Console.log Name
Console.log Age
```

Output:

```html
Geek
19
```

**CoffeeScript 变量:**在 CoffeeScript 中，var 关键字的使用被豁免。变量是通过给它们赋值来创建的。像在 JavaScript 中一样，我们使用 var 关键字声明变量。

```html
var a = 10
var b = 20

```

但是对于 CoffeeScript，我们将变量声明为:

```html
a = 10
b = 20

```

**括号:**在大多数编程语言中声明函数时，我们使用括号来避免歧义，并使代码可读。但是在 CoffeeScript 中，在创建如下所示的函数时，不使用括号，而是使用箭头符号(- >)来代替括号。

**示例:**

```html
Function = > console.log "Hello World"
```

当我们需要使用括号时，有时就是这种情况。例如，当调用上面创建的函数在控制台上显示结果时，我们将函数调用为:

```html
Function()  

```

让我们再举一个 Square 函数的例子，它给出了一个数的平方作为结果:

**示例:**

```html
Square = (x) -> x*x

Console.log Square 4
```

**输出:**

```html
16
```

**花括号:**一般来说，对于函数、循环等代码块，我们使用花括号，但是在 CoffeeScript 中，我们不使用花括号。取而代之的是，适当的缩进应该与身体内部的空白保持一致。这里有一个咖啡脚本函数的例子，在这个例子中，我们使用了四个空格作为缩进来分隔函数中的语句。

**示例:**

```html
Function = ->
    Name = "Nimrat"
    Console.log "Hello" + Name

Function()
```

**输出:**

```html
Hello Nimrat
```

**注释:**在编程语言中，注释用于使代码更容易理解。CoffeeScript 中的注释类似于 Ruby 语言中的注释。在 CoffeeScript 中，有以下两种类型的注释:

*   **Single-line Comments:** When we need to comment on the single line in CoffeeScript, we only need to place a hashtag (#) before starting the line as shown below:

    ```html
    # This is a single-line comment
    ```

    hashtag 后面的任何一行都被编译器视为注释，编译除注释之外的其余代码。

*   **多行注释:**当需要注释多行时，我们需要注释的行被包装在一对三个标签中，如下所示:

    ```html
    ###
    This is how multi lines are commented in CoffeeScript. 
    We can keep as many lines as we want in comments using
    a pair of triple hashtags.
    ###
    ```