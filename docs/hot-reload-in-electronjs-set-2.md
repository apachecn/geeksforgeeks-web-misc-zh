# 电子中的热重新加载|设置–2

> 原文:[https://www . geesforgeks . org/hot-reload-in-electronijs-set-2/](https://www.geeksforgeeks.org/hot-reload-in-electronjs-set-2/)

[**electronijs**](https://www.geeksforgeeks.org/introduction-to-electronjs/)是一个开源框架，用于使用能够在 Windows、macOS 和 Linux 操作系统上运行的 HTML、CSS 和 JavaScript 等网络技术构建跨平台的本机桌面应用程序。它将铬引擎和[T5 节点 T7】结合成一个单一的运行时。](https://www.geeksforgeeks.org/introduction-to-nodejs/)

本文是电装中 [**热重装的延续。在前一篇文章中，我们已经讨论了什么是**热重新加载/实时重新加载**，以及如何分别使用**电子重新加载**和**电子重新加载器****](https://www.geeksforgeeks.org/hot-reload-in-electronjs/) **[**npm**](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 包在电子应用程序中实现它。在本文中，我们将分别使用 **elemon** 和**Electron-Hot-Reload**NPM 包在电子应用程序中实现热重载。此外，如前一篇文章所述，热重载功能应该只在**开发**环境中实现。因此，我们使用了 **NODE_ENV** 环境变量来定义与上一篇文章中使用的相同的变量。我们可以使用电子中的全局**进程**对象来访问这个变量。**

*   **参考文章:** [*处理电子中的对象*](https://www.geeksforgeeks.org/process-object-in-electronjs/) *。*

我们也可以从窗口控制台设置这个环境变量。有关电子中支持和使用的环境变量的更多详细信息。

*   **参考文章:** [*电商中的环境变量*](https://www.geeksforgeeks.org/environment-variables-in-electronjs/) *。*

在这种情况下，我们想要一个所有操作系统平台都支持的**开发**登台环境的解决方案，并且不需要任何配置更改，我们也可以参考文章:**在电子 JS** 中管理登台环境。我们将继续使用上一篇文章中的代码库。项目结构和**包**文件也保持不变。我们现在将分别使用 **elemon** 和**电子热重新加载** npm 包来实现热重新加载功能。

*   首先，我们将使用 **npm** 安装 **elemon** 。

```html
npm install elemon --save

```

*   使用 **npm** 安装**电子热装**。

```html
npm install electron-hot-reload --save

```

这两个包是完全不相关的，并且有不同的语法和使用不同的方法。我们可以在 electronic 中分别使用这两个包来实现热重载功能。设置电子应用程序所需的基本步骤保持不变。

**package.json:**

```html
{
  "name": "electron-hot",
  "version": "1.0.0",
  "description": "Hot Reload for Electron",
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  },
  "keywords": [
    "electron"
  ],
  "author": "Radhesh Khanna",
  "license": "ISC",
  "dependencies": {
    "electron": "^8.2.5",
    "electron-hot-reload": "^0.1.4",
    "elemon": "^5.0.3"
  },
  "devDependencies": {
    "electron-reload": "^1.5.0",
    "electron-reloader": "^1.0.1"
  }
}

```

**输出:**

[![](img/b32d8f95392fcbe0adbaa31fa63d952f.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200512225834/Output-1105.png)

**注意:**参考上一篇文章，全面了解 **NODE_ENV** 环境变量。

*   **方法 1:** 使用 **elemon** npm 包。 **elemon** 是一个重量轻的模块，在开发电子应用程序时，它提供了一种简单有效的方法来添加热重载功能。此外，只有在应用程序的**主进程**中发出 **app** 模块的**就绪**事件后，才能使用该包。根据这个包的作者和贡献者，代码符合**标准 JS** ，该标准定义了在 **JavaScript** 中编码时需要遵循的某一组规则。当使用这个包在电子中实现热重新加载时，如果任何**渲染器进程**中有任何变化，则相应的**浏览器窗口**实例被重新加载，但是当应用程序的**主进程**即 **main.js** 文件中有变化时，应用程序退出当前实例并重新启动一个新实例来反映这些变化。
*   **更多详细信息，请参考链接:**此包兼容，从 electronic v 8 . 3 . 0 开始工作，没有任何错误，并且定期更新。

> https://www.npmjs.com/package/elemon.

*   **main.js** :在该文件中添加以下代码片段。我们将把这段代码片段添加到 **createWindow()** 函数中。

## java 描述语言

```html
const env = process.env.NODE_ENV || 'development';
// ..
    // Open the DevTools.
    win.webContents.openDevTools()

    if (env === 'development') {
        const elemon = require('elemon')
        elemon({
            app: app,
            mainFile: 'main.js',
            bws: [
                // The BrowserWindow Instance used 
                // in the createWindow() function is win. 
                { bw: win, res: ['index.html'] },
            ]
        });
    }
```

*   **说明:****elemon(参考文献)**实例方法采用以下参数。此方法没有任何返回类型。该实例方法中传递的所有参数都是**必需的**。
    *   **参考:对象**该对象引用**应用程序**实例、**浏览器窗口**实例、**主进程**文件以及各自的**渲染器进程**文件和实例。它接受以下参数。
        *   **app: Object** 该参数取一个**对象**，该对象代表在 **main.js** 文件开始时导入的主 **app** 模块的实例。
        *   **主文件:字符串**该参数取一个**字符串**，代表**主进程**文件名。在这种情况下，是 **main.js** 文件。
        *   **bws: Object[]** 此参数采用对象的**数组**，每个对象代表各自的**浏览器窗口**实例及其关联的文件和资源。如果在应用程序的**主进程**中定义了多个**浏览器窗口**实例，那么每个**浏览器窗口**实例将在数组中表示为一个单独的对象。每个 **bws** 对象接受以下参数。
            *   **bw:对象**该参数表示全局**浏览器窗口**实例。
            *   **res: String[]** 此参数表示一个**字符串数组**，其中每个字符串表示一个资源或文件的名称，该文件以某种方式连接到该**浏览器窗口**实例。在我们的例子中，这个参数将由**index.html**组成，作为 **res** 数组中唯一的字符串元素。为了更好的理解，请参考代码。

*   **方法 2:** 使用**电子热装** npm 包。**电子热重加载**也是一个重量轻的模块，它提供了一种在开发电子应用程序时添加热重加载功能的简单方法。此外，只有在应用程序的**主进程**中发出 **app** 模块的**就绪**事件后，才能使用该包。这个包没有 **elemon** 那么受欢迎，但是它提供了一套与其他包不同的功能。这个包最关键的特点是，它为应用程序的**主进程**和不同的**渲染器进程**提供了单独的**观察器**，因此，它对每个进程都更具可定制性。我们还可以在对文件进行热重装之前指定**钩子**，并且我们可以直接指定我们想要热重装的文件的名称。这个包还提供了捕捉应用程序中**未处理错误**的额外优势，如果我们指定的话。
*   **更多详细信息，请参考链接:**此包的行为与 **elemon** 相同。在对**主进程**的更改中，应用程序被重新启动，在对**渲染器进程**的更改中，相应的**浏览器窗口**实例被重新加载。该软件包是兼容的，并且从 electronic v 8 . 3 . 0 和起没有任何错误，但是没有定期更新。

> https://www.npmjs.com/package/electron-hot-reload.

*   **main.js** :在该文件中添加以下代码片段。我们将在文件的末尾添加这个代码片段，而不涉及任何现有的代码。

## java 描述语言

```html
// Importing the watchers from electron-hot-reload
const { mainReloader, rendererReloader } = require('electron-hot-reload')
const env = process.env.NODE_ENV || 'development';
// ..
if (env === 'development') {
    const mainFile = path.join(__dirname, 'main.js');
    const rendererFile = path.join(__dirname, 'index.html');

    mainReloader(mainFile, (error, path) => {
        console.log(path);
        console.log("It is a main's process hook!");
    });

    rendererReloader(rendererFile, (error, path) => {
        console.log(path);
        console.log("It is a renderer's process hook!");
    });
}
```

*   **解释:**两个**主加载器(路径，忽略，处理程序，选项)**实例方法和**渲染器加载器(路径，忽略，处理程序，选项)**实例方法具有相同的方法签名。这两种实例方法都采用以下参数。这两种方法都没有任何返回类型。
    *   **路径:字符串/字符串[]** 该参数采用一个**字符串**参数或一个**字符串数组**,表示要关注热重装的文件的路径。我们需要指定文件的完整路径，因此我们使用了 NodeJS **path** 模块的 [**path.join()**](https://www.geeksforgeeks.org/node-js-path-join-method/) 方法。在本教程中，我们为**主进程**和**渲染器进程**观察者分别指定了 **main.js** 文件和**index.html**的路径。
    *   **忽略:RegExp/RegExp[](可选)**该参数为**可选**参数。此参数采用一个**正则表达式**参数或一个**正则表达式数组**，表示热重装要忽略的文件和目录的**正则表达式**。有关**正则表达式**的更多详细信息，请参考文章: [**JavaScript 正则表达式【abc】表达式**](https://www.geeksforgeeks.org/javascript-regexp-abc-expression/) 。要了解正则表达式在 JavaScript 中的工作原理，请参考文章: [**JavaScript 正则表达式**](https://www.geeksforgeeks.org/javascript-regular-expressions/) 。
    *   **处理程序:功能(可选)**该功能为可选。该函数是一个**回调**函数，用于创建钩子并捕获应用程序中未处理的错误，如描述中所述。该函数接收两个参数:
        *   **错误**未处理的错误。
        *   **路径**文件的路径发生了变化。