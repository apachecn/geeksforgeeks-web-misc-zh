# 如何通过缩小&压缩文件来提高性能？

> 原文:[https://www . geesforgeks . org/如何通过缩小压缩文件来提高性能/](https://www.geeksforgeeks.org/how-to-improve-performance-by-minify-compress-files/)

缩小是一个被广泛认可的有用的过程，它通过从 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 、 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 和 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 文件中删除不必要的部分，通常是空格、换行符和注释，来帮助我们提高 web 应用程序的性能。

**缩小化:**是在不改变应用程序行为和输出的情况下，最小化 web 应用程序内部代码或标记文件大小的过程。简单来说，缩小就是从 HTML、CSS 和 JavaScript 代码中删除所有不必要的东西，包括空格和注释，而不影响我们的输出。它缩小了项目规模并提高了性能。

**缩小是如何工作的？**

*   开发人员首先编写 HTML、CSS 和 JavaScript，因为在开发代码时需要可读性和可理解性。所以我们在开发过程中需要注释、换行符和空白。
*   应用程序完成后，现在可以部署了。我们将在部署之前缩小所有的 HTML、CSS 和 JavaScript 代码。我们将从代码文件中删除所有的换行符、空格和注释。
*   将优化的应用程序部署到服务器。

**缩小的方法:**通常有三种方法可以缩小我们的 HTML、CSS 和 JavaScript 文件。他们是

*   **手动缩小:**这个过程很简单，开发人员从我们的应用程序文件中删除所有不必要的部分。但是，如果项目规模很大，那么这种方法就不是最佳的，因为从开发和部署方面来看，这将花费大量时间。
*   **通过在线工具缩小**有不同的网站可以帮助我们自动缩小代码。但是这些网站对于不同的编程和标记语言是不同的。最广泛用于此类任务的网站如下。复制并粘贴原始代码，它将自动生成缩小版本。这是最理想的方法。

*   **对于 HTML:**

    ```htmlhtml
    https://html-minifier.com/
    ```

*   **对于 CSS:**

    ```htmlhtml
    https://cssminifier.com/
    ```

*   **对于 JavaScript:**

    ```htmlhtml
    https://javascript-minifier.com/
    ```

**编辑器扩展:**像 Visual Studio Code 或 Atom 这样的代码编辑器提供的不同扩展也非常有帮助，可以自动生成 HTML、CSS 或 JavaScript 代码的缩小版本。谷歌搜索根据你使用的特定编辑器将向你展示完成它的路径。**JS&CSS Minifier(Minify)****by**olback**是 Visual Studio Code 中最流行的 JavaScript 和 CSS Minifier 扩展之一。**

****缩小的优势:**缩小的主要方面是缩小了 web 应用的大小。这带来了很多好处。它们如下**

*   ****提高加载时间:**缩小后的页面加载时间比缩小前的加载时间短。缩小可以将应用程序加载时间减少 60%，这一事实使其成为开发基于产品的 web 应用程序的最重要步骤之一。**
*   ****更低的空间使用:**随着 web 应用程序的规模缩小，在服务器中构建和存储它只需要很少的存储空间。这降低了公司在托管 web 应用程序时的服务器成本。**
*   ****更好的用户体验:**缩小化带来的加载时间的改善给用户带来了更好的优化体验，使 web 应用快速响应。应用程序越快，用户体验越好。**

****示例:****

****HTML:****

*   ****缩小前的 HTML:****

    ## **超文本标记语言**

    ```htmlhtml
    <!DOCTYPE html>

    <html>

      <head>

          <title>Page Title</title>

      </head>

      <body>

          <h2>Welcome To GeeksforGeeks</h2>

          <p>How to improve performance by Minify and Compress Files.</p>

      </body>

    </html>
    ```

*   ****缩小后的 HTML:****

    ## **超文本标记语言**

    ```htmlhtml
    <!doctype html>
    <html>
    <head>
    <title>Page Title</title>
    </head>
    <body>
    <h2>Welcome To GeeksforGeeks</h2>

    <p>How to improve performance by Minify and Compress Files.</p>

    </body>
    </html>
    ```

**CSS:**

*   ****缩小前 CSS:****

    ## **半铸钢ˌ钢性铸铁(Cast Semi-Steel)**

    ```htmlhtml
    body {
      background-color: #282c34;
      color: white;
      padding: 40px;
      font-family: Arial;
      text-align: center;
    }
    ```

*   ****缩小后的 CSS:****

    ## **半铸钢ˌ钢性铸铁(Cast Semi-Steel)**

    ```htmlhtml
    body{background-color:#282c34;color:#fff;padding:40px;font-family:Arial;text-align:center}
    ```**