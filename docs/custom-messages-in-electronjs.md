# 电子邮件中的自定义消息

> 原文:[https://www . geesforgeks . org/custom-messages-in-electronijs/](https://www.geeksforgeeks.org/custom-messages-in-electronjs/)

**[electronijs](https://www.geeksforgeeks.org/introduction-to-electronjs/)**是一个开源框架，用于使用能够在 Windows、macOS 和 Linux 操作系统上运行的 HTML、CSS 和 JavaScript 等网络技术构建跨平台的本机桌面应用程序。它将铬引擎和**T5 节点 T7】结合成一个单一的运行时。**

电子应用程序与用户交互的方式之一是通过消息框和警报。有时在应用程序执行过程中，会出现需要用户注意的情况，或者代码遇到错误，需要让用户意识到这一点。在这种情况下，如果没有用户干预，执行流程就无法向前推进。电子为我们提供了一种方便的技术，通过这种技术，用户可以意识到问题并采取必要的措施。电子为我们提供了一个内置的**对话框**模块来显示自定义消息框和警报，以便与用户交互。本教程将使用对话框模块的实例方法来演示电子邮件中的自定义消息。

我们假设您熟悉上述链接中介绍的先决条件。电子要工作， **[节点](https://www.geeksforgeeks.org/introduction-to-nodejs/)** 和 **[npm](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/)** 需要预装在系统中。

**电子定制消息:****对话框**模块是**主进程**的一部分。为了导入和使用**渲染器进程**中的对话框模块，我们将使用电子**远程**模块。

*   **项目结构:**
    ![Project Structure](img/9fbd36d191dcef9866133748a0a780e6.png)

**示例:**按照给定的步骤在 electronic 中构建自定义消息框。

*   **Step 1:** Navigate to an Empty Directory to setup the project, and run the following command,

    ```
    npm init
    ```

    生成**包. json** 文件。安装 **[电子](https://www.geeksforgeeks.org/introduction-to-electronjs/)** 如果没有安装，使用 npm。

    ```
    npm install electron --save
    ```

    这将安装所需的**节点 _ 模块**依赖项。将您选择的任何图像文件复制到**资产**文件夹中，并将其命名为**image.png**。在本教程中，我们将使用电子标志作为**image.png**文件。

    **package.json:**

    ```
    {
      "name": "electron-message",
      "version": "1.0.0",
      "description": "Custom Messages in Electron",
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
        "electron": "^8.2.5"
      }
    }

    ```

*   **Step 2:** For the Boilerplate code of the **main.js** file, Refer this [link](https://www.electronjs.org/docs/tutorial/first-app#electron-development-in-a-nutshell). We have modified the code to suit our project needs.

    **main.js:**

    ```
    const { app, BrowserWindow } = require('electron')

    function createWindow () {
      // Create the browser window.
      const win = new BrowserWindow({
        width: 800,
        height: 600,
        webPreferences: {
          nodeIntegration: true
        }
      })

      // Load the index.html of the app.
      win.loadFile('src/index.html')

      // Open the DevTools.
      win.webContents.openDevTools()
    }

    // This method will be called when Electron has finished
    // initialization and is ready to create browser windows.
    // Some APIs can only be used after this event occurs.
    /* The 'dialog.showErrorBox()' method can be used before 
       this event occurs. */ 
    // This method is equivalent to 'app.on('ready', function())'
    app.whenReady().then(createWindow)

    // Quit when all windows are closed.
    app.on('window-all-closed', () => {

      // On macOS it is common for applications and their menu bar
      // To stay active until the user quits explicitly with Cmd + Q
      if (process.platform !== 'darwin') {
        app.quit()
      }
    })

    app.on('activate', () => {

      // On macOS it's common to re-create a window in the 
      // app when the dock icon is clicked and there are no 
      // other windows open.
      if (BrowserWindow.getAllWindows().length === 0) {
        createWindow()
      }
    })

    // In this file, you can include the rest of your 
    // app's specific main process code. You can also 
    // Put them in separate files and require them here.
    ```

*   **Step 3:** Create the **index.html** file and **index.js** file within the **src** directory. We will also copy the boilerplate code for the **index.html** file from the above-mentioned link. We have modified the code to suit our project needs.

    **index.html:**

    ```
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="UTF-8">
        <title>Hello World!</title>
        <!-- https://electronjs.org/docs/tutorial
                               /security#csp-meta-tag -->
        <meta http-equiv="Content-Security-Policy" 
              content="script-src 'self' 'unsafe-inline';" />
      </head>
      <body>
        <h1>Hello World!</h1>
        We are using node 
        <script>
            document.write(process.versions.node)
        </script>, Chrome 
        <script>
            document.write(process.versions.chrome)
        </script>, and Electron 
        <script>
            document.write(process.versions.electron)
        </script>.

        <h3>Custom Messages in Electron</h3>
        <button id="show">Show Custom Message Box</button>

        <br><br>
        <button id="error">Show Error Message Box</button>

        <!-- Adding Individual Renderer Process JS File -->
        <script src="index.js"></script>
      </body>
    </html>
    ```

    **输出:**此时，我们的应用程序已经设置好了，我们可以启动应用程序来检查 GUI 输出。要启动电子应用程序，请运行命令。

    ```
    npm start
    ```

    ![](img/b7679d7d3d8e54f041298963135f0d2d.png)

*   **Step 4:** The **Show Custom Message Box** button does not have any functionality associated with it yet. To change this, add the following code in the **index.js** file.

    **对话框显示消息框(浏览器窗口，选项)**用于**选项**对象的所有默认值/基本值。使用此实例方法会显示消息框，并将阻止应用程序执行，直到消息框通过用户的适当操作成功关闭。它接受以下参数。

    *   **浏览器窗口:浏览器窗口(可选)****浏览器窗口**实例。该参数允许**对话框**将其自身附加到父窗口，使其成为**模式**。模态窗口是禁用父窗口的子窗口。如果**浏览器窗口**未显示，对话框将不会附加到其上。在这种情况下，它将显示为独立窗口。在上面的代码中，**浏览器窗口**实例没有被传递到对话框，因此单击**显示自定义消息框**按钮，对话框作为独立窗口打开。
    *   **选项:对象**它接受以下参数:
        *   **type: String (Optional)** It can hold the following values.
            *   **无**
            *   **信息**
            *   **错误**
            *   **问题**
            *   **警告**

            这些值中的每一个都表示您想要向用户显示的消息框的类型。默认值为**无**。在**窗口**上，**问题**显示与**信息**相同的图标，除非明确设置了**图标**属性。在 **macOS** 上，**警告**和**错误**显示相同的警告图标。除了默认值之外，这些值都有一个与之关联的默认系统操作系统声音。

        *   **按钮:字符串[](可选)**它代表您希望在自定义消息框中显示的按钮标签的数组。空数组将显示一个按钮，标记为**确定**。
        *   **缺省值:整数(可选)**打开自定义消息框时，缺省选择的`buttons`数组中按钮的索引。该属性依赖于 **noLink** 属性。这将在以下步骤中演示。
        *   **标题:字符串(可选)**消息框中显示的标题。某些操作系统平台及其各自的版本不支持此属性。
        *   **消息:字符串**消息框的主要内容。
        *   **详细信息:字符串(可选)**附加信息将显示在**消息**属性下方的消息框中。
        *   **复选框标签:复选框的字符串(可选)**标签。此属性自动在自定义消息框中包含带有给定标签的复选框。
        *   **复选框选中:布尔值(可选)**该属性表示复选框的初始状态。该属性的默认值为**假**。
        *   **图标:原生图像(可选)**消息框上显示的图标。如果定义了该属性，它将覆盖**类型**属性的默认系统图标，而不管其值如何。该属性接受一个**原生图像**实例或图像的文件路径。在本教程中，我们将使用**路径**模块传递位于**资产**文件夹中的**image.png**文件的文件路径。
        *   **取消:整数(可选)**通过 **Esc** 键取消对话时返回的按钮索引。默认情况下，这被分配给第一个按钮，并且**取消**或**否**作为**按钮**数组属性中的标签。如果不存在这样的标记按钮，并且没有设置该选项，将使用 **0** 作为返回值。这将在以下步骤中演示。
        *   **否链接:布尔型(可选)**该属性仅在**窗口**上受支持。设置该属性后，电子将自动尝试找出其中哪个按钮是常用按钮标签，如**取消**、**是**、**否**、**确定**等，并将其他按钮标签显示为对话框中的命令链接。此属性用于使对话框窗口以现代**窗口**操作系统应用程序和主题的样式出现。默认情况下，该属性设置为**假**。如果使用所有通用按钮标签，此属性将不起作用。此属性将在以下步骤中演示。
        *   **规范化访问键:布尔型(可选)**跨平台规范化键盘访问键。默认值为**假**。启用此属性假设按钮标签中使用了 **' & '** 通配符。这些标签将被转换，以便它们在每个平台上相应地工作。 **' & '** 字符在 **macOS** 上全部删除，在 **Linux** 上转换为 **_** ，在 **Windows** 上不做任何动作。

**对话框显示消息框(浏览器窗口，选项)**返回**承诺**。它解析为包含以下参数的**对象**，

*   **响应:整数**点击按钮的索引，如**按钮**数组属性中所定义。
*   **复选框选中:布尔值**如果设置了**复选框标签**属性，复选框的选中状态。默认情况下，将返回**假**。

**index.js:**

```
const electron = require('electron');
const path = require('path');

// Importing dialog module using remote
const dialog = electron.remote.dialog;

var showBox = document.getElementById('show');

showBox.addEventListener('click', (event) => {
    // Resolves to a Promise<Object>
    dialog.showMessageBox({
        // option Object
        type: 'none',
        buttons: [],
        defaultId: 0,
        icon: '',
        title: 'This is the Title',
        message: 'This is a Message',
        detail: 'This is extra Information',
        checkboxLabel: 'Checkbox',
        checkboxChecked: false,
        cancelId: 0,
        noLink: false,
        normalizeAccessKeys: false,
    }).then(box => {
        console.log('Button Clicked Index - ', box.response);
        console.log('Checkbox Checked - ', box.checkboxChecked);
    }).catch(err => {
        console.log(err)
    }); 
});
```

**输出:**我们现在应该可以通过点击**显示自定义消息框**按钮成功触发一个基本的自定义消息框。
![](img/352ee02193e85ba83528dab994688bd5.png)

**注意:**如果用户在未成功关闭自定义消息框的情况下尝试继续执行应用程序，控制台上会显示以下消息:

```
Attempting to call a function in a renderer window that 
has been closed or released. Function provided here: undefined
```

*   **步骤 5:** 我们现在将修改自定义消息框的**选项**对象，以查看不同的输出，
    *   **类型:字符串**定义不同类型的消息框。
        *   **类型:【信息】** ![type: 'info'](img/78659ee7863804c8e1b66ba9426f4f4a.png)
        *   ****类型:【警告】****
            ![type: 'warning'](img/411f140c467a746c48e239ac58dd26a1.png)
        *   ****类型:【错误】****
            ![type: 'error'](img/29dc9d3e63d5348c4fe9921878e65d53.png)
    *   **按钮:字符串[]** 我们将为**按钮**数组属性定义自定义标签，并通过更改**无链接**属性查看各自的输出。
        *   **buttons: [‘Cancel’, ‘OK’, ‘Button-1’, ‘Button-2’]**, **noLink: false**, **defaultId: 0**
            ![noLink: 'false'](img/4977e5c2c34d9386ec7e2df6dce701f3.png)

            **注意:**在这种情况下，**默认**属性应该突出显示**取消**按钮，但是选择了**按钮-1** 标签。这是由于 **noLink** 属性定义的行为。

        *   **buttons: [‘Cancel’, ‘OK’, ‘Button-1’, ‘Button-2’]**, **noLink: true**, **defaultId: 0**
            ![noLink: 'true'](img/068d00bd76145774a5332960e569af56.png)

            **注意:**根据预期行为，默认选择**取消**按钮。

            *   **取消:整数**评估**取消**属性的行为。按下键盘上的 **Esc** 键可激活该行为。
    *   **buttons: [‘Cancel’, ‘OK’, ‘Button-1’, ‘Button-2’]**, **cancelId: 100**, **noLink: true**

        ![](img/dd6387a566fe8c35af8d8870e5d29d42.png)

        **注意:**返回的值是在**取消**属性中设置的 100。

    *   **buttons: [‘Cancel’, ‘OK’, ‘Button-1’, ‘Button-2’]**, **cancelId: 100**, **noLink: false**
        ![](img/c30999c99f1d0f6c8ddbd1e506677603.png)

        **注意:**尽管将**取消**属性值设置为 100，但返回值为 0。

        *   **icon: NativeImage** We will be passing the filepath of the **image.png** file located in the **assets** folder.
    *   **按钮:['取消'，'确定'，'按钮-1 '，'按钮-2']** ，**图标:路径. join(__dirname，'../assets/image.png')** ， **noLink: true**
        ![noLink: 'true'](img/3b9a1e284db08e0e79c80805b6202c58.png)
    *   **按钮:['取消'，'确定'，'按钮-1 '，'按钮-2']** ，**图标:路径. join(__dirname，'../assets/image.png')** ， **noLink: false**
        ![noLink: 'false'](img/e9bec3b0280e6bded6040f811f3717e0.png)

    **注意:**使用**图标**属性禁用**类型**属性的默认系统操作系统声音，无论其值如何。

我们还可以通过简单地将**按钮**数组属性的索引值与**承诺**返回的**响应**参数进行比较，为消息框中的每个按钮分配不同的行为。

**index.js:**

```
.then(box => {
    console.log('Button Clicked Index - ', box.response);
    console.log('Checkbox Checked - ', box.checkboxChecked);

    if (box.response === 0) {
        console.log('Cancel Button was clicked');
    } else if (box.response === 2) {
        console.log('Button-1 was clicked');
    }
 }).catch(err => {
    console.log(err)
 }); 
```

**输出:**
![](img/bdefb6a7dbdd4e508ed1645f621c6625.png)

*   **Step 6:** Electron also provides us with an instance Method specifically designed for Error Messages. In the above code, the **Show Error Message Box** button does not have any functionality associated with it. To change this add the following code in the **index.js** file.

    **对话框显示错误框(标题，信息)**接受以下参数。它没有任何返回值。该方法不像 **dialog.showMessageBox()** 方法那样是可定制的，但是可以在 **app** 模块的 **ready** 事件发出之前安全地调用该方法。参考 **main.js** 文件中高亮显示的代码。它通常用于显示应用程序启动阶段的错误。如果在 **Linux** 上 **app** 模块的 **ready** 事件之前调用，消息会被发送到 **stderr** ，不会出现 GUI 对话框。

    *   **标题:字符串**错误框的标题。
    *   **信息:字符串**显示在**标题**属性下方的错误框中的文本信息。

    **index.js:**

    ```
    var error = document.getElementById('error');

    error.addEventListener('click', (event) => {
        dialog.showErrorBox('This is the Title', 'This is the Content');
    });
    ```

    **输出:**
    ![](img/4f1a319edce6e36104b8373426a3f55b.png)