# 电子表格中的进度条|设置–1

> 原文:[https://www . geesforgeks . org/进度条-in-electronijs-set-1/](https://www.geeksforgeeks.org/progress-bars-in-electronjs-set-1/)

[**electronijs**](https://www.geeksforgeeks.org/introduction-to-electronjs/)是一个开源框架，用于使用能够在 Windows、macOS 和 Linux 操作系统上运行的 HTML、CSS 和 JavaScript 等网络技术构建跨平台的本机桌面应用程序。它将铬引擎和[T5 节点 T7】结合成一个单一的运行时。](https://www.geeksforgeeks.org/introduction-to-nodejs/)

**进度条**是网页开发的关键部分。我们不需要强调进度条在应用程序中的重要性。我们已经有无数种方法可以使用 HTML、CSS 和 JavaScript 开发高度复杂和交互式的进度条。但是，在桌面应用程序中，我们希望显示与本机系统用户界面非常匹配的进度条，并证实系统操作系统的外观和感觉。在 electronic 中，我们可以在应用程序的任务栏/dock 图标中显示进度条。这使得应用程序能够向用户提供进度信息，而用户不必切换到应用程序窗口本身。这可以使用**浏览器窗口**对象的实例方法来实现。此外，在外部包的帮助下，我们可以在应用程序窗口中显示吸引人的、可定制的进度条，这些进度条也与本机系统主题很好地集成在一起。在本教程中，我们将演示如何在电子应用程序中创建进度条。

我们假设您熟悉上述链接中介绍的先决条件。电子要工作， [**节点**](https://www.geeksforgeeks.org/introduction-to-nodejs/) 和 [**npm**](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 需要预装在系统中。

*   **项目结构:**

![Project Structure](img/8c3fc521d63aa10fa12672b9633662b1.png)

**示例:**按照 [**中给出的步骤，设置基本的电子应用程序。复制文章中提供的 **main.js** 文件和**index.html**文件的样板代码。我们将继续使用相同的代码库构建我们的应用程序。另外，使用**](https://www.geeksforgeeks.org/dynamic-styling-in-electronjs/) **[npm](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 安装**电子进度条**组件。这个外部包提供了一个简单且高度可定制的应用编程接口来控制和显示进度条。进度条的每一个方面都可以使用 CSS 定制，并且值也可以动态设置。有关**电子进度条**的更多信息，**

**参考链接:**T2https://www.npmjs.com/package/electron-progressbar.

```html
npm install electron-progressbar --save

```

此外，对**包进行必要的更改，以启动电子应用程序。我们将继续使用相同的代码库构建我们的应用程序。设置电子应用程序所需的基本步骤保持不变。**

**package.json:**

```html
{
  "name": "electron-progress",
  "version": "1.0.0",
  "description": "Progress Bars in Electron",
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
    "electron": "^8.3.0",
    "electron-progressbar": "^1.2.0"
  }
}

```

**输出:**

[![](img/b32d8f95392fcbe0adbaa31fa63d952f.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200512225834/Output-1105.png)

**电子进度条:****浏览器窗口**实例是**主进程**的一部分。要在**渲染器进程**中导入和使用**浏览器窗口**，我们将使用电子**远程**模块。我们将首先演示如何使用**浏览器窗口**对象的实例方法在应用程序的任务栏/dock 图标中创建默认进度条。

*   **index.html:** 在该文件中添加以下代码片段。

## 超文本标记语言

```html
<h3>Progress Bar in Electron</h3>
  <button id="progress">
       Click to Launch BrowserWindow Progress Bar
  </button>
  <br><br>
```