# 如何将图像保存到 localStorage 并在下一页显示？

> 原文:[https://www . geeksforgeeks . org/如何将图像保存到本地存储并在下一页显示/](https://www.geeksforgeeks.org/how-to-save-an-image-to-localstorage-and-display-it-on-the-next-page/)

**什么是 localStorage？**

默认情况下，本地存储是所有现代网络浏览器都可以使用的网络应用编程接口。它允许网站在浏览器中存储最少量的数据，以便在未来的浏览器会话中使用。本地存储类似于会话存储，只是本地存储没有到期日期。

**local storage 的优势**

*   Compared with cookie-based data storage, it can store a large amount of data (usually 2MB-10MB).
*   As long as the same protocol in the domain is used, the data will remain in the browser for future browser sessions.
*   Data need not be transferred with each *request* and *RES* object.

**为什么是 localStorage？**

*   当网络连接不良时，尝试使用假后端。
*   当需要多次填写表单数据(名字、地址等)时，跨会话保存一些默认数据。

**语法:**

```
window.localStorage   // It returns a Storage Object
```

**本地存储方式:**

1.  *Setting item (key, value)* : used to save data to local storage.
2.  *Remove item* : used to delete data from localStorage.
3.  *getItem（键）：* 它从 localStorage 读取数据。
4.  *清除()*:清除 localStorage(在域上)。

**将数据保存到本地存储的语法:**

```
localStorage.setItem(*key*, *value*)
Ex: localStorage.setItem("firstName", "Mark Zuker berg");
```

**从本地存储读取数据的语法:**

```
localStorage.getItem(*key*)

// Returns the string "Mark Zuker berg"
Ex: localStorage.getItem("firstName");
```

**从本地存储中删除数据的语法:**

```
localStorage.removeItem(*key*)
Ex: localStorage.removeItem("firstName");
```

我们已经学习了本地存储的必要基础知识。让我们用一个例子来实现上面的方法。

**先决条件:**

1.  The basic knowledge of reaction.
2.  Any code editor.

**示例:**我们将实现一个名为 Pics Villa 的小图片发帖平台，有两个网页:

**1。帖子形式:**接受用户的输入。它采用以下输入:

*   **Post title:** The title of our post is a string type.
*   **picture website:** picture website. It can be a public link to images stored in Google Cloud or any other service you choose. However, for this example, all the images were uploaded to Github and the download link was used. In this case, the image url may look like the following format: *https://raw.githubusercontent.com/ < Your user name >/< Your repurchase name >/< Actual image path >*
*   **Post comment:** It is a multi-line string.

**2。所有帖子:**显示用户输入的表单数据。

**创建应用程序的步骤:**

1.使用以下命令创建您的应用程序:

```
npx create-react-app crud-application
```

2.上面的命令为我们创建了一个带有所有必需样板文件的 React 项目。让我们通过键入以下命令进入项目的 *src* 文件夹:

```
cd crud-application/src
```

3.您可以删除一些不必要的文件(可选步骤):

```
rm App.css App.test.js logo.svg
```

4.允许网页路由。安装以下模块:

```
npm i react-router-dom
```

5.检查您的*包. json* 以匹配以下依赖项:

```
"dependencies": {
    .......................
    "react": "^17.0.1",
    "react-dom": "^17.0.1",
    "react-router-dom": "^5.2.0",
    "react-scripts": "4.0.1",
    "web-vitals": "^0.2.4",
    .....................
    // Other dependencies (if any)
  },
```

**档案名称:app . js**

## 【JavaScript】

```
import React, { Component } from 'react';
import { BrowserRouter, Route, Switch } 
        from 'react-router-dom';
import PostForm from './PostForm';
import AllPost from './AllPost';

class App extends Component {
  render() {
    return (
    <div className="App">
      <BrowserRouter>
        <Switch>
          <Route exact path ='/' render=
            {props => <PostForm {...props} />}>
          </Route>
          <Route exact path='/gallery' render=
            {props => <AllPost {...props} />}>
          </Route>
        </Switch>
      </BrowserRouter>
    </div>
    );
    }
  }
export default App;
```