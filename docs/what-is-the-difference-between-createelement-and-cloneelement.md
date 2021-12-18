# 【createElement 和 cloneElement 有什么区别？

> 原文:[https://www . geeksforgeeks . org/create element 和-cloneelement 的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-createelement-and-cloneelement/)

**React.createElement()方法:**react . createelement()方法用于创建元素。每当我们在 JSX 编写代码时，JSX 都会将其转换为 React.createElement()。不建议使用 createElement 方法，因为它很难维护或调试。为了创建一个 React 元素，我们必须每次都调用 React.createElement()方法，即使它只是一个没有属性的 span 标记。

**语法:**

```html
React.createElement(
    type,
    [props],
    [...children]
)
```

**示例:**在本例中，我们使用 React.createElement()方法创建了一个 div 元素。

```html
import React from 'react';
import "./styles.css";
const title = React.createElement('h1', 
    {className:'title'}, 'GeeksforGeeks');
const App =()=>
  React.createElement('div', {}, [
    React.createElement('button',{className:'btn'}, title),
    React.createElement('button', {className:'btn'}, title),
]);

export default App;
```