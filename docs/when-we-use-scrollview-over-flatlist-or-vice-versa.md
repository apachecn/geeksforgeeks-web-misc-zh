# 当我们在平面列表上使用滚动视图时，反之亦然？

> 原文:[https://www . geesforgeks . org/when-we-use-scroll view-over-flat list-反之亦然/](https://www.geeksforgeeks.org/when-we-use-scrollview-over-flatlist-or-vice-versa/)

**滚动视图:**滚动视图组件是一个内置的反应原生组件，作为一个通用的可滚动容器，能够滚动其中的子组件和视图。

**何时使用 ScrollView？**

ScrollView 加载所有内容，即一次全部显示在屏幕上的数据。这是在组件加载后立即完成的。因此，整个内容(数据列表)被一起装载。现在，如果该数据列表包含许多项目，它将自动导致性能问题。因此，如果您有一百或一千个项目要显示在屏幕上，最好不要使用 ScrollView。当有限大小的列表中的数据项较少时，使用它。

**平面列表:**平面列表组件是一个内置的反应原生组件，在可滚动列表中显示类似结构的数据。它只显示那些当前显示在屏幕上的元素。

**什么时候使用 FlatList？**

与 ScrollView 相反，FlatList 只呈现那些当前显示在屏幕上的元素(默认:10 个项目)。因此，它对应用程序的性能没有任何影响。因此，最好使用平面列表组件来显示一个大的数据列表。

**scroll view 和 Flatlist 的主要区别是:**

<figure class="table">

| 滚动视图 | 平面列表 |
| --- | --- |
| It does not provide any memory management. | Provide automatic memory management. |
| It loads everything at once. | It loads the content when the window scrolls. |
| It will slow down the rendering speed and increase the memory usage. | Does not affect the rendering speed. |
| It maintains the component state. | Do not maintain component state. |
| It presents common content in a scrollable container. | A list of similar items is presented. |
| 可以从自然反应导入为:
*从反应-本地人'*导入{滚动视图}； | 可以从原生反应导入为:
*从“反应-本地”导入{平面列表}；* |

</figure>