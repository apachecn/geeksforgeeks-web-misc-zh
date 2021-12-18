# MVC 和 MVT 设计模式的区别

> 原文:[https://www . geesforgeks . org/MVC 和 mvt 设计模式之间的区别/](https://www.geeksforgeeks.org/difference-between-mvc-and-mvt-design-patterns/)

**1。模型视图控制器(MVC) :**
它是一种软件设计模式，用于实现用户界面，并强调将数据表示与交互和处理数据的组件分开。

它有 3 个组件，每个组件都有特定的用途:

*   这个**模型**是这个架构的核心组件，管理应用程序的数据、逻辑以及其他约束。
*   **视图**处理如何向用户显示数据，并提供各种数据表示组件。
*   **控制器**操纵模型，并通过充当两者之间的桥梁来渲染视图。

**2。模型视图模板(MVT) :**
这是另一种类似于 MVC 的设计模式。它也用于实现 web 接口和应用程序，但是与 MVC 不同的是，控制器部分由框架本身来负责。

它有 3 个组件，每个组件都有特定的用途:

*   这个类似于 MVC 的**模型**充当了你的数据的接口，基本上是整个 web 应用背后的逻辑结构，由一个数据库比如 MySql、PostgreSQL 来表示。
*   **视图**执行业务逻辑，并与模型交互和呈现模板。它接受 HTTP 请求，然后返回 HTTP 响应。
*   **模板**是 MVT 区别于 MVC 的组件。模板充当表示层，基本上是呈现数据的 HTML 代码。这些文件中的内容可以是静态的，也可以是动态的。

**MVC 与 MVT 设计模式的区别:**

<figure class="table">

| s。没有。 | Model View Controller (MVC) | Model View Template (MVT) |
| --- | --- | --- |
| 1。 | MVC has a controller that drives models and views. | MVT has a view to receive HTTP requests and return HTTP responses. |
| --- | --- | --- |
| 2。 | The view tells the user how the data will be presented. | Templates are used in MVT for this purpose. |
| 3。 | In MVC, we have to write all control-specific code. | Part of the controller is managed by the framework itself. |
| 4。 | Highly coupled | Loose coupling |
| 5。 | It is difficult to modify. | It is easy to modify. |
| 6。 | Suitable for developing large applications but not suitable for small applications. | Suitable for small and large applications. |
| 7。 | The process is clearly defined and easy to understand. | Compared with MVC, Flow is sometimes more difficult to understand. |
| 8。 | Does not involve URL mapping. | URL pattern mapping occurs. |
| 9。 | 例如 ASP.NET 最有价值球员、春天最有价值球员等。 | Adopt MVT pattern of Jiang Ge. |

</figure>