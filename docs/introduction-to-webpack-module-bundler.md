# 网络包模块捆绑器介绍

> 原文:[https://www . geesforgeks . org/introduction-to-web pack-module-bundler/](https://www.geeksforgeeks.org/introduction-to-webpack-module-bundler/)

**Webpack:** Webpack 是一个用于 JavaScript 应用程序的静态模块捆绑器。由于 webpack 只理解 JavaScript 和 JSON 文件，如果包含相应的加载器，它会将前端资产(如 HTML、CSS 和图像)转换为有效的模块。处理您的应用程序时，webpack 会在内部构建一个依赖图，该图映射项目所需的每个模块，并生成一个或多个输出包。

网络包的一些核心概念是:

1.  Entrance 
2.  output
3.  loader
4.  plug-in component
5.  model

**入口:**入口点定义了网络包应该使用哪个模块来开始构建其内部依赖图。入口点的默认值是 ***。/src/index.js*** ，但是在 webpack 配置中。，您可以通过在此文件中设置 entry 属性来指定不同的或多个入口点。

让我们考虑一个例子，其中 ***极客*** 目录中的 file.js 是入口点。那么 webpack.config.js 文件应该如下所示:

**文件名:webpack.config.js**

```
module.exports = {
 entry: './GeeksForGeeks/file.js'
};
```

**输出:**输出属性指示 webpack 在哪里发出它创建的包，并告诉命名这些文件的方法。默认情况下，其值为 ***。/dist/main.js 主输出文件为*** ，为 ***。/dist*** 文件夹用于任何其他生成的文件，但是我们可以通过在配置中指定输出字段来更改这部分过程。

**文件名:网络包**

```
const path = require('path');
module.exports = {
 entry: './GeeksForGeeks/file.js',
 output: {
   path: path.resolve(__dirname, 'gfg'),
   filename: 'GeeksForGeeks-webpack.bundle.js'
 }
};
```

**加载器:**因为 webpack 只理解 JavaScript 和 JSON 文件。加载器处理其他类型的文件，然后将它们转换成我们的应用程序可以使用的有效模块，并将它们添加到依赖图中。

加载器对其他类型的文件进行预处理，并将它们添加到包中，加载器在 webpack 配置中有两个属性，它们通过这两个属性来实现:

1.  Test attribute
2.  Use attributes

**测试属性:**用于标识哪个或哪些文件应该由相应的加载程序转换。通常，正则表达式用于标识应该转换的文件。

**use 属性:**用于指示应该使用哪个加载器进行转换。

**文件名:网络包**

```
const path = require('path');
module.exports = {
 output: {
   filename: 'GeeksForGeeks-webpack.bundle.js'
 },
 module: {
   rules: [
     { test: /\.txt$/, use: 'raw-loader' }
   ]
 }
};
```

上面的 webpack 配置为一个模块定义了一个规则属性，其中有两个必需属性，即**测试**和**使用**。当 webpack 编译器遇到解析为的路径时。在 require()/import 语句中，它将使用 raw-loader 在将其添加到包之前对其进行转换。

**插件:**虽然加载器用于预处理某些类型的模块，但插件可以用于执行更广泛的任务，如注入环境变量、资产管理和捆绑优化。

为了使用一个插件，我们需要()并将其添加到插件数组中。插件可以通过选项定制。由于一个插件可以在一个配置中为不同的目的使用多次，我们需要通过用新的操作符调用它来创建它的一个实例。

**文件名:网络包**

```
const HtmlWebpackPlugin = require('html-webpack-plugin');
const webpack = require('webpack');
module.exports = {
 module: {
   rules: [
     { test: /\.txt$/, use: 'raw-loader' }
   ]
 },
 plugins: [
   new HtmlWebpackPlugin({template: './src/GeeksForGeeks.html'})
 ]
};
```

在上面的例子中， *html-webpack-plugin* 用于通过自动注入我们生成的所有包来为我们的应用程序生成一个 html 文件。

**模式:**我们可以通过将模式参数设置为开发、生产或无，来启用与每个环境相对应的 webpack 内置优化。它的默认值是生产。

**文件名:网络包**

```
module.exports = {
 mode: 'development'
}
```