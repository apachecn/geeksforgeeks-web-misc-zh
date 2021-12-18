# 咖啡脚本|简介

> 原文:[https://www.geeksforgeeks.org/coffeescript-introduction/](https://www.geeksforgeeks.org/coffeescript-introduction/)

CoffeeScript 是一种编译成 JavaScript 的轻量级语言。它提供了简单易学的语法，避免了复杂的 JavaScript 语法。CoffeeScript 受到 JavaScript、Ruby、YAML、Haskell、Perl、Python 的影响，并影响了 MoonScript、LiveScript 和 JavaScript。
在本教程中，读者将学习 CoffeeScript 的基本功能，掌握后用代码构建动态网站和 web 应用。
在阅读本教程之前，读者应该先了解 JavaScript，因为它类似于咖啡脚本。它包含额外的功能列表理解和解构任务。

**历史:**咖啡脚本语言是由杰里米·阿什肯纳斯设计的。它于 2009 年 12 月 13 日首次在 git 上推出，当时杰里米·阿什肯纳斯首次提交了 git 咖啡脚本。2010 年 2 月 21 日，第一个纯咖啡脚本编译器发布，早期的咖啡脚本编译器是 Ruby 语言。到那时，GitHub 项目吸引了许多贡献者，使其成为当时需求最大的项目。

### 装置

*先决条件*:在运行下面的命令和安装 CoffeeScript 之前，您应该已经安装了 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 和 [NPM](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 。

```
# Install locally for a project:
npm install --save-dev coffeescript

# Install globally to execute .coffee files anywhere:
npm install --global coffeescript
```

**咖啡的优势脚本:**

*   **通俗易懂:**这种语言的语法是一种简单的 JavaScript 形式。语法的简单是这种编程语言的美妙之处。用 CoffeeScript 编写的代码非常简洁，容易理解。
*   **无 var 关键字:**与 JavaScript 不同，在声明变量之前不需要使用 var 关键字。因此，它有助于避免程序中的范围声明问题。
*   **无符号:**分号、括号和大括号等符号在 CoffeeScript 中不起任何作用。相反，空格用于区分函数、循环等内部的代码。
*   **少代码:**与 JavaScript 相比，代码行数减少了一半。好处，更少的代码降低了程序的复杂性。
*   **可维护:** CoffeeScript 为许多操作符提供了别名的概念，这使得代码易于理解、可读。维护用 CoffeeScript 编写的程序变得很容易。
*   **可靠:** CoffeeScript 是一种可靠安全的制作动态网页的编程语言。

CoffeeScript 使用 JavaScript 库，反之亦然，这些库在使用 CoffeeScript 时提供了大量的库。这种语言的文件扩展名是。要执行咖啡脚本文件，您需要键入以下命令:

```
coffee -c filename.coffee
```

语法并不奇怪。例如，如果你想在控制台上打印一些东西，那么你只需要在控制台中键入它。

## java 描述语言

```
console.log "Hello world"
```

**CoffeeScript 的好处:**学习 coffee script 的好处在于，您将探索其庞大的库，包括 JavaScript 库。咖啡脚本包含了每个程序员都想要的三样东西:

*   有效空白
*   直接的类定义和函数
*   λ函数

**限制:**coffee script 唯一的限制就是对空格非常敏感。如果没有保持适当的缩进，将会引发错误。因此，程序员需要非常小心空白。

### CoffeScript 与 Typescript:

<figure class="table">

| 咖啡脚本 | 以打字打的文件 |
| 当我们想要更多可读的代码和大量的语法糖时，最好使用它。 | 当我们想要可选的静态类型和更好的工具支持时，最好使用它。 |
| 它仅用于服务器端 web 应用程序。 | 它用于服务器端和客户端 web 应用程序。 |
| 它是由开源开发者社区自己根据麻省理工学院许可证开发和维护的。 | 它由微软根据 Apache2 许可证开发和维护。 |

</figure>

### 咖啡脚本死了吗？

随着 2015 年 ES6 的出现以及新语言的出现，可以跨平台编译为 JS，很多都改变了 CoffeeScript 的劣势。它开始面临严峻的竞争。主要问题不是不好，而是不够好。在 ES6 中，JavaScript 还增加了许多强大的新功能，并且拥有更大的社区。截至今天，2021 年 1 月，咖啡脚本在市场上几乎已经死亡。