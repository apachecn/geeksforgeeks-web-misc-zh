# 电子表格中的进度条|设置–2

> 原文:[https://www . geesforgeks . org/进度条-in-electronijs-set-2/](https://www.geeksforgeeks.org/progress-bars-in-electronjs-set-2/)

本文是以下文章的延续: [**电竞进度条| Set–1**](https://www.geeksforgeeks.org/progress-bars-in-electronjs-set-1/)。在前一篇文章中，我们讨论了如何使用**浏览器窗口**对象的实例方法在电子应用程序的任务栏/dock 图标中创建进度条。在本文中，我们将在电子应用程序中实现一个自定义进度条，使用我们之前在应用程序设置期间安装的**电子进度条** [npm](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 包。我们将继续使用上一篇文章中的代码库。项目结构和 **package.json** 文件也保持不变。如前一篇文章所述，**电子进度条**包提供了一个简单且高度可定制的应用编程接口来显示和控制电子应用程序中的进度条。该包装只能在**主流程**中直接导入使用。要在**渲染器进程**中导入和使用这个包，我们需要对 **main.js** 文件进行额外的更改。在这种情况下，我们不能使用电子**远程**模块，因为它是一个外部包。此外，只有在应用程序的**主进程**中发出 **app** 模块的**就绪**事件后，才能使用该包。

*   **main.js** : Add the following fragment to this file. After that, we can import and use this package in the renderer process of the application, because we have added the import to the **global** object in the **main.js** file. If you import the **electronic progress bar** package directly in the **renderer process** , you will encounter an error: **Type error is not captured: the browser window is not a constructor** . This error is caused because internally, the package tries to initialize a **browser window** object directly from the electronic device, instead of using **remote** module which is only supported in **main process** but not supported in **renderer process** .

## JavaScript

```html
const { app, BrowserWindow } = require('electron')
global.ProgressBar = require('electron-progressbar');
```

*   **index.html** : Add the following fragment to that file.

## html

```html
<h3>Progress Bar in Electron</h3>
    <button id="progress">
        Click to Launch BrowserWindow Progress Bar
    </button>
    <br><br>
    <button id="custom">
        Click to Launch Electron ProgressBar from Package
    </button>
```

*   **index.js** : **Click the button** to start the electronic progress bar from the package and there is no related function. To change this, please add the following code in the **index.js** file.

## JavaScript

```html
const { getGlobal, app, BrowserWindow } = electron.remote
// Importing ProgressBar in the Renderer Process from global
// Actual Import in main.js file
const ProgressBar = getGlobal('ProgressBar');

// Cannot Import Directly in the Renderer Process
// const ProgressBar = require('electron-progressbar')

var custom = document.getElementById('custom');
custom.addEventListener('click', () => {
    var progressBar = new ProgressBar({
        abortOnError: false,
        // Determinate Progress Bar
        indeterminate: false,
        initialValue: 0,
        maxValue: 100,
        // On Completion, Progress Bar window will not close.
        closeOnComplete: false,
        title: 'Title of the Progress Bar',
        text: 'Text of the Progress Bar',
        detail: 'Detail to Show actual Progress, ' +
                'Can be set as Dynamic to show actual Status',
        style: {
            text: {},
            detail: {},
            bar: { 'width': '100%', 'background-color': '#BBE0F1' },
            value: {}
        },
        browserWindow: {
            parent: null,
            modal: true,
            resizable: false,
            closable: false,
            minimizable: false,
            maximizable: false,
            width: 500,
            height: 170,
            // Important - If not passed, Progress Bar will not be displayed.
            webPreferences: {
                nodeIntegration: true
            }
        }
    });

    progressBar
        .on('completed', (value) => {
            console.log(progressBar.isCompleted());
            console.log('Progress Bar Completed');
            progressBar.detail = 'Task completed. Exiting...';
        })
        .on('ready', () => {
            console.log(progressBar.getOptions())
        })
        .on('aborted', (value) => {
            console.log(`aborted... ${value}`);
        })
        .on('progress', (value) => {
            progressBar.detail =
            `Value ${value} out of ${progressBar.getOptions().maxValue}...`;
        });

    setInterval(function () {
        if (!progressBar.isCompleted()) {
            progressBar.value += 1;
        }
    }, 100);
});
```