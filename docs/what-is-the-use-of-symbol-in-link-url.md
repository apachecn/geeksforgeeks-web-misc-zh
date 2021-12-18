# 链接 URL 中的“#”符号有什么用？

> 原文:[https://www . geesforgeks . org/什么是链接中符号的使用-url/](https://www.geeksforgeeks.org/what-is-the-use-of-symbol-in-link-url/)

我们中的许多人可能在检查一些网站时观察到了网址中的井号(#)。它不是一个简单的规则字符，而是有一个特殊的功能。所以首先，它被称为命名锚，有时也称为片段。命名锚点或片段用于链接到同一网页的一部分。我们通常将一个页面链接到另一个页面，但是如果我们必须链接到同一个网页上的某个标题呢？然后，命名主播(#)进场。

**语法:**它只会指向同一个页面的顶部，因为那个锚点标签没有任何链接。

```html
<a href="#">Click me</a>
```

**示例:**例如，您有一个非常长的网页，其中有几个标题，可以直接导航到这些标题，这将会很有帮助。然后用链接将用户指向那个特定的标题，链接必须包括。因此，基本上为了让用户指向某个特定的标题，我们在锚标签中使用了带有该标题名称的井号。当使用空的没有其他配音标题时，相同的链接指向同一页面的顶部。

**注意:**空白#号不会给你带来任何结果，因为它没有链接到任何 id 属性。

*   **程序:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>link has a pound “#” sign</title>
        <style>

            h1 {
                color: green;
            }

            li {
                font-size: 16px;
                color: blue;
            }
        </style>
    </head>

    <body>
        <h1>GeeksforGeeks</h1>
        <b>A Computer Science Portal for Geeks</b>
        <ul>
            <li><a href="#learn">Learn</a></li>
            <li><a href="#contribute">Contribute</a></li>
            <li><a href="#explore">Explore</a></li>
        </ul>
        <div id="learn">
            <h4>Learn</h4>
            <p>
             A Computer Science portal for geeks. 
             It contains well written, well thought 
             and well explained computer science and 
             programming articles, quizzes and many more.
            </p>
        </div>
        <div id="contribute">
            <h4>Contribute</h4>
            <p>
             A Computer Science portal for geeks. 
             It contains well written, well thought 
             and well explained computer science and 
             programming articles, quizzes and many more.
            </p>
        </div>
        <div id="explore">
            <h4>Explore</h4>
            <p>
             A Computer Science portal for geeks. 
             It contains well written, well thought 
             and well explained computer science and 
             programming articles, quizzes and many more.
            </p>
        </div>
    </body>

    </html>
    ```

*   **输出:**
    ![](img/4183b6d871b8b090ca4761a6911241d5.png)