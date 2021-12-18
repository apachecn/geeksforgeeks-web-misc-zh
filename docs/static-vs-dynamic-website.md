# 静态 vs 动态网站

> 原文:[https://www.geeksforgeeks.org/static-vs-dynamic-website/](https://www.geeksforgeeks.org/static-vs-dynamic-website/)

**什么是网站？**
网站是网页、文本、图像、视频等不同多媒体内容的集合，可以通过浏览器地址栏中可以看到的 URL 进行访问。例如:[https://www.geeksforgeeks.org](https://www.geeksforgeeks.org/)

**如何访问网站？**
当我们在浏览器搜索栏中键入某个 URL 时，浏览器向 Web 服务器请求页面，Web 服务器将所需的网页及其内容返回给浏览器。现在，服务器返回静态和动态网站所需信息的方式有所不同。

**网站类型:**

*   静态网站
*   动态网站

**静态网站:**在静态网站中，网页由服务器返回，这些网页是使用简单语言(如 HTML、CSS 或 JavaScript)构建的预构建源代码文件。静态网站不处理服务器上的内容(根据用户)。服务器返回的网页没有变化，因此静态网站速度很快。没有与数据库的交互。此外，它们的成本更低，因为主机不需要支持不同语言的服务器端处理。

![Architecture of Static Website](img/89df93a5887fba25b3d6a803c2507850.png)

静态网站的架构

**注意:**静态并不意味着它不会响应用户动作，这些网站之所以被称为静态，是因为这些网站不能在服务器上进行操作，也不能与数据库进行交互(动态网站就是这种情况)。

**动态网站:**在动态网站中，网页由服务器返回，在运行时进行处理，这意味着它们不是预构建的网页，而是在服务器支持的 PHP、Node.js、ASP.NET 等服务器端脚本语言的帮助下，根据用户需求在运行时构建的。因此，它们比静态网站慢，但更新和与数据库的交互是可能的。

动态网站优于静态网站，因为与静态网站相比，更新可以非常容易地完成(在静态网站中，每个页面都需要更改)，但是在动态网站中，可以进行一次常见的更改，它将反映在所有网页中。

![Architecture of Static Website](img/2011e31df18d006e59ff1e43f893c12a.png)

动态网站的架构

**静态网站与动态网站的区别:**

<figure class="table">

| 

静态网站

 | 

动态网站

 |
| --- | --- |
| The content of the web page cannot be changed at runtime. | The content of the webpage can be changed. |
| It is impossible to interact with the database. | Interaction with database is possible. |
| Faster than dynamic website loading. | Slower than static websites. |
| Lower development cost. | The development cost is higher. |
| No content management function. | Characteristics of content management system. |
| HTML, CSS and Javascript are used to develop websites. | Use PHP, Node.js and other server-side languages. |
| The same content is passed every time the page is loaded. | Every time the page is loaded, the content may change. |

</figure>