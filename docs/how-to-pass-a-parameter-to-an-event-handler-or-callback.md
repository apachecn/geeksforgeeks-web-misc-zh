# 如何将参数传递给事件处理程序或回调？

> 原文:[https://www . geesforgeks . org/如何将参数传递给事件处理程序或回调/](https://www.geeksforgeeks.org/how-to-pass-a-parameter-to-an-event-handler-or-callback/)

[React js](https://www.geeksforgeeks.org/react-js-introduction-working/) 是当今最流行的 JavaScript 框架之一。由于框架的独特功能，有很多公司的网站都是建立在 React 上的。React UI 包含几个组件。用户可以在 React 用户界面上执行许多任务。每个组件都有不同的 HTML 元素，用户可以点击、悬停或触发任何形式的事件。

**事件处理程序:**事件是 UI 发生变化时发送的信号。用户可以单击、悬停、拖动鼠标或按任意键来执行这些事件。为了响应这些变化，用户可以编写事件处理程序代码。在处理 React 事件时，您需要记住这两点。

*   反应事件以 camelCase 的格式命名(onchange 而不是 onChange)。
*   React 事件处理程序放在大括号内(onChange={handleSubmit}而不是 onChange =“handleSubmit”)。

**方法:**让我们创建一个 React 项目，然后我们将创建一个事件处理程序。用户可以通过它进行交互并触发事件。在用户界面中看到响应后，我们将创建自己的参数。这将帮助您理解事件处理程序的底层逻辑，并通过它传递参数。

**创建反应项目:**

*   **步骤 1:** 要创建 react app，需要通过 npx 命令安装 react 模块。**“**Npx”被用来代替“npm”，因为你在你的应用程序的生命周期中只需要这个命令一次。

    ```html
    npx create-react-app project_name
    ```

*   **第 2 步:**创建反应项目后，移动到文件夹中执行不同的操作。

    ```html
    cd project_name
    ```

**项目结构:**运行上述步骤中提到的命令后，如果在编辑器中打开项目，可以看到类似的项目结构，如下图所示。用户创建的新组件或我们将要执行的代码更改将在源文件夹中完成。

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

**示例 1:** 在本例中，我们将创建一个事件处理程序，每当您单击按钮时，它都会发送一条欢迎消息，即 Alert。

## App.js

```html
import React from "react";
class App extends React.Component {
  call() {
    alert("Welcome to Geeks for Geeeks!");
  }
  render() {
    return (
      <button onClick={this.call}>Click the button!</button>
    );
  }
}

export default App;
```

**运行应用程序的步骤:**打开终端，键入以下命令。

```html
npm start
```

**输出:**打开浏览器。默认情况下，它将打开一个运行 localhost 的选项卡(http://localhost:3000/)，您可以看到图像中显示的输出。点击按钮查看欢迎信息。

![](img/90e960ed07fe568869e13a410b019375.png)

**示例 2:** 在本例中，我们将使用[箭头函数](https://www.geeksforgeeks.org/arrow-functions-in-javascript/)创建一个新函数，该函数使用正确的参数调用函数调用。将事件对象作为第二个参数传递给 react。如果你想传递一个参数给点击事件处理程序，你需要使用箭头函数或者绑定函数。如果直接传递参数，onClick 函数甚至会在按下按钮之前自动调用。

## App.js

```html
import React from "react";
class App extends React.Component {
  call(message,event) {
    alert(message);
  }
  render() {
    return (
       //Creating a arrow function 
      <button onClick={(event)=> this.call("Your message",event)}>
         Click the button!
       </button>
    );
  }
}
export default App;
```

**运行应用程序的步骤:**打开终端，键入以下命令。

```html
npm start
```

**输出:**打开浏览器。默认情况下，它将打开一个运行 localhost 的选项卡(http://localhost:3000/)，您可以看到图像中显示的输出。点击按钮查看欢迎信息。

![](img/90e960ed07fe568869e13a410b019375.png)

**示例 3:** 在本例中，我们将使用[绑定方法](https://www.geeksforgeeks.org/reactjs-bind-method/)，该方法也用于在基于类的组件的函数中传递参数。

## App.js

```html
import React from "react";
class App extends React.Component {
  call(message) {
    alert(message);
  }
  render() {
    return (
      <button onClick= {this.call.bind(this,"Your message")}>
        Click the button!
      </button>
    );
  }
}
export default App;
```

**运行应用程序的步骤:**打开终端，键入以下命令。

```html
npm start
```

**输出:**打开浏览器。默认情况下，它将打开一个运行 localhost 的选项卡(http://localhost:3000/)，您可以看到图像中显示的输出。点击按钮查看欢迎信息。

![](img/90e960ed07fe568869e13a410b019375.png)