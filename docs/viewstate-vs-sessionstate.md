# 视图状态 Vs 会话状态

> 原文:[https://www.geeksforgeeks.org/viewstate-vs-sessionstate/](https://www.geeksforgeeks.org/viewstate-vs-sessionstate/)

众所周知，web 是无状态的，这意味着每次请求特定的网页时。它每次都会被重新创建并发布到服务器。此外，HTTP 是一种无状态协议，即它不能在网页上保存客户端信息。所以它需要维护一个页面的状态以及服务器端的状态，状态管理就完成了。视图状态和会话状态分别用于客户端状态管理和服务器端状态管理。这两者之间的基本区别是，视图状态是在客户端管理状态，这使得最终用户可以轻松管理状态，而会话状态是在服务器端管理状态，这也使得从这一端管理内容变得容易。

**视图状态:**仅在页面级的一个级别维护。在单个页面上所做的更改在其他页面上不可见。在视图状态下收集的信息只为客户端存储，不能传输到任何其他地方。视图状态仅与可序列化数据同义。

视图状态倾向于页面实例特定数据的持久性。当使用视图状态时，发布到特定页面的值会保留在客户端正在使用的浏览区域中，并且只有在整个操作完成后才会发布回来。加载另一页时，上一页的数据不再可用。此外，在这种情况下，数据是不安全的，因为它会暴露给客户端。加密可用于数据安全。

**SessionState:** 它是在会话级维护的，可以跨 web 应用程序中的所有页面访问数据。信息存储在服务器中，任何能够访问存储信息的服务器的人都可以访问这些信息。

SessionState 倾向于持久保存用户特定的数据，并在服务器端进行维护。在会话完成或用户关闭浏览器之前，这些数据保持可用。会话状态仅对类型对象有效。

**视图状态和会话状态的区别:**

| View state | Session |
| --- | --- |
| is only maintained at the page level. | Stay at the session level. |
| The view state can only be seen from a single page, not from multiple pages. | The availability of session state values spans all available pages in the user session. |
| It will hold the value when the postback operation occurs. | In the session state, user data remains in the server. Users can use the data before the browser closes or the session expires. |
| Information is only stored in the client. | Information is stored on the server. |
| It is used to allow the persistence of specific page instance data. | It is used to persist user-specific data on the server side. |
| The view state value is lost/cleared when loading a new page. | Session state can be cleared by programmer or user, or it can be cleared in case of timeout. |

**用法:**

*   [t0】 session state: 【t1] can be used to store the information you want to access on different web pages.
*   **View state** can be used to store the information you want to access from the same webpage.