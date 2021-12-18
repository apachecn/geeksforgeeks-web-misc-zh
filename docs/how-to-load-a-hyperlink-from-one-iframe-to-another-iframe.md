# 如何加载一个 iframe 到另一个 iframe 的超链接？

> 原文:[https://www . geeksforgeeks . org/如何加载从一个 iframe 到另一个 iframe 的超链接/](https://www.geeksforgeeks.org/how-to-load-a-hyperlink-from-one-iframe-to-another-iframe/)

[HTML Iframe](https://www.geeksforgeeks.org/html-iframes/) 或内嵌框架允许在一个 HTML 页面中嵌入多个 HTML 页面。在本文中，我们将看到如何使用另一个 iframe 中的超链接来更改一个 iframe 的内容。

这可以通过正确使用 iframe 标签中的[名称属性](https://www.geeksforgeeks.org/html-name-attribute/)和[锚点标签中的目标属性](https://www.geeksforgeeks.org/html-a-tag/)来实现。name 属性允许每个内联框架有自己唯一的名称，而 target 属性告诉超链接，当单击链接时，必须在超链接所在的位置打开页面。如果我们将目标的值保留为超链接内容应该显示的目标 iframe 的名称，我们的问题就会得到解决。

*   We will create an HTML page consisting of two iframes.
*   Give each iframe a unique name.
*   Create another HTML page with multiple hyperlinks.
*   Add the name of the second iframe to the target attribute of each hyperlink.
*   Click the link in the first iframe, and you should see the page opened in the second iframe.

**示例:**HTML 文档将在其中嵌入两个 iframes。

## 【index.html】

```html
<!DOCTYPE html>
<html>
  <body>
    <center>
      <h2>Hello world!!</h2>
      <br />
      <iframe src="iframe1.html" 
              name="iframe1" 
              width="70%" 
              height="250">
      </iframe>
      <br /><br />
      <iframe src="" 
              name="iframe2" 
              width="70%" height="300">
      </iframe>
    </center>
  </body>
</html>
```