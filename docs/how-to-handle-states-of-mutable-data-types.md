# 如何处理可变数据类型的状态？

> 原文:[https://www . geesforgeks . org/如何处理可变数据类型的状态/](https://www.geeksforgeeks.org/how-to-handle-states-of-mutable-data-types/)

可变参数是那些其值可以在作为参数传递的函数中修改的参数。这意味着，当使用 **调用者函数** 将参数传递给函数时，其值将绑定到被调用函数 的 **中的参数，这意味着对该函数中的值所做的任何更改也将反映在调用者函数的参数中。**

在反应组件中，状态是可变的。为了使 react 应用程序具有交互性，我们几乎在每个 React 组件中都使用了状态。状态是用某个值初始化的，基于用户与应用程序的交互，我们使用 setState 方法在某个时间点更新组件的状态。如果 React 组件的状态是用数组或 JavaScript 对象初始化的，那么最好不要通过修改旧的数组或对象本身来改变状态，而是使用一些内置的 JavaScript 方法，如映射、过滤器，或者使用新的 JavaScript 语法，如 spread，来整体返回新更新的状态。

**示例 1:** 在这个示例中，我们将创建一个 todo 应用程序，用户将在其中进行交互并存储他或她想要做的事情，这基本上是一个可变状态。

*   **index.js:**

    ## java 描述语言

    ```html
    import React from 'react'
    import ReactDOM from 'react-dom'
    import App from './App'

    ReactDOM.render(<App />, document.querySelector('#root'))
    ```