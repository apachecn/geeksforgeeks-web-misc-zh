# 【ShadowDOM 和 VirtualDOM 有什么区别？

> 原文:[https://www . geesforgeks . org/shadow DOM 和-virtualdom 的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-shadowdom-and-virtualdom/)

[文档对象模型](https://www.geeksforgeeks.org/dom-document-object-model/)是客户端开发中遵循的一个流行概念。这是一种跨平台且独立于语言的基本技术。它被定义为通过对象创建逻辑结构化文档的 HTML 或 XML 文档的应用编程接口。

**虚拟 DOM:**

*   Virtual DOM, simply put, is a complete and complete representation of a real DOM.
*   Because any changes to DOM will cause pages to be rendered more frequently, virtual DOM mainly tries to avoid any unnecessary and expensive changes to DOM.
*   This is achieved by grouping changes and making a single re-rendering, instead of making several small re-renderings.
*   A copy of DOM is stored in memory, which is used to compare any changes being made anywhere in DOM, and compare to find out the differences. Therefore, only the updated part of the application is re-rendered, not the whole DOM.
*   Both VueJS and ReactJS use virtual DOM.

**影子 DOM:**

*   Shadow DOM is mostly related to the concept of encapsulation. It is a tool that allows developers to overcome DOM encapsulation.
*   It means that the browser has the potential to add a subtree of DOM elements in the rendering of the document, but it will not be added to the DOM tree of the main document.
*   Therefore, it isolates the DOM and ensures that the DOM of the component is an independent element and will not appear in the global DOM.
*   In contrast to DOM, Shadow DOM appears in smaller pieces, which means (unlike Virtual DOM) that it is not a complete representation of the whole DOM.
*   It also proved to be helpful for CSS scope. The styles used in the application may overlap, which makes it troublesome to deal with them. Shadow DOM ensures that styles created in a single shadow DOM element remain isolated and within their own scope.

### **暗影形态和虚拟形态的区别**

<figure class="table">

| 虚拟 DOM | 影子 DOM |
| --- | --- |
| 它围绕着解决性能问题。 | 它围绕着封装的概念。 |
| 它是一个实际 DOM 的完整表示。 | 它不是整个 DOM 的完整表示。 |
| 它将几个变化组合在一起，进行一次重新渲染，而不是多次小的变化。 | 它将 DOM 元素的子树添加到文档的渲染中，而不是将其添加到主文档的 DOM 树中。 |
| 它创建了整个 DOM 对象的副本。 | 它创建了 DOM 对象的小块，它们有自己独立的范围。 |
| 它不孤立 DOM。 | 隔离 DOM。 |
| 这对 CSS 范围界定没有帮助。 | 有助于 CSS 的范围界定。 |

</figure>