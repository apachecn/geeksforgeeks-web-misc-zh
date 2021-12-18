# 如何在项目中使用外部模块和 NPM？

> 原文:[https://www . geesforgeks . org/如何在项目中使用外部模块和 NPM/](https://www.geeksforgeeks.org/how-to-use-external-modules-and-npm-in-a-project/)

**对外部模块的需求:**对于一个大型 JavaScript 应用程序来说，仅仅在一个 JavaScript 文件中编写全部代码会变得困难和混乱。这就是 CommonJS 进入图片的地方，这种 CommonJS 格式定义了一种模块格式，可以用来将您的 JS 应用程序分解成多个文件。Node.js 采用这种 Commonjs 格式将我们的 JS 应用程序组织成多个文件。在这个 Node.js 应用程序中，我们有一个 module.exports 属性，用于确定当前模块的导出。
**节点模块的类型:**Node . js 中的模块是组织成单个或多个 JS 文件的简单或复杂的功能，可以在整个 Node.js 应用程序中再次使用。Node.js 模块有三种类型:

*   **本地/基于文件的模块:**它在我们的应用程序中定义文件内的节点模块，并在我们的应用程序中使用。
*   **核心模块:**核心模块是 Node.js 中内置的模块，这些模块提供了足够的功能，外部模块设计人员可以添加自己的功能，在开发 Node 应用程序时可以使用。核心模块包括路径、文件系统、操作系统、util 和一些其他模块。
*   **第三方模块:**第三方模块为外部 Node 模块。这些是由节点开发人员开发的第三方节点模块，通过节点生态系统提供。但是我们需要一个维护所有模块的包管理器，以便可以轻松访问它们。这就是 NPM 进入画面的地方。

[**NPM(Node Package Manager)**](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/)**:**NPM 是 Node.js 中 JavaScript 运行时环境的默认包管理器，Node.js Package Manager (npm)是 Node.js 生态系统中默认且最流行的包管理器，主要用于安装和维护 Node.js 应用中的外部模块。用户基本上可以使用 npm 安装应用程序所需的节点模块。
**如何导出模块？**
首先，通过在命令提示符/终端中键入 **npm init** 来初始化 node.js 应用程序(确保您在当前项目文件夹中)。它将创建一个 package.json 文件。
使用以下语法在 Node.js 项目中添加一个模块。
**语法:**

```
var module = require("module_name");
```

**创建自己的模块并使用:**首先，通过在命令提示符/终端中键入 **npm init** 来初始化目录中的节点。

*   **创建 Node.js 模块:**

## java 描述语言

```
module.exports = (length, breadth, callback) => {
    if (length <= 0 || breadth <= 0)
        setTimeout(() => callback(new Error(
                "Dimensions cannot be negative: length = "
                + length + ", and breadth = "
                + breadth), null), 5000);
    else
        setTimeout(() => callback(null, {
                Perimeter: () => (2*(length+breadth)),
                 Area:() => (length*breadth) }), 5000);
}
```

*   **在您的应用程序中使用节点模块:**

## java 描述语言

```
var rect = require('./rectangle');
module.exports.Rect = function Rect(l, b) {
    rect(l, b, (err, rectangle) => {
        if (err)
            console.log("There is an ERROR!!: ", err.message);
        else {
            console.log("Area of rectangle with dimensions length = "
                + l + " and breadth = " + b + " : " + rectangle.Area());

            console.log("Perimeter of the rectangle with dimensions length = "
                 + l + " and breadth = " + b + " : " + rectangle.Perimeter());
        }
     console.log("\n\n");
    });
};
```