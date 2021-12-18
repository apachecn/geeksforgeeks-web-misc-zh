# 【body.onload()和 document.ready()功能的区别

> 原文:[https://www . geesforgeks . org/body-on load-and-document-ready-function/](https://www.geeksforgeeks.org/difference-between-body-onload-and-document-ready-function/)

一旦加载了 DOM 和所有相关的资源，比如图像，就会调用 **body.onload()** 事件。基本上， [**onload()**](https://www.geeksforgeeks.org/html-onload-event-attribute/) 将在页面已经完全加载了整个图像、iframes 和样式表等时被调用。

例如，如果我们的页面包含更大尺寸的图像，那么 **onload()** 事件将等待直到图像完全加载。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- using jquery library -->
    <script 
       src="https://code.jquery.com/jquery-git.js">
    </script>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">

</head>

<body onload="loadBody()">
    <h2>GeeksForGeeks</h2>

    <script>
       function loadBody(){
           alert("page loaded");
       }
    </script>
</body>

</html>
```

**输出:**

![](img/da27bd2e143895613bbafe15f1029fbc.png)

车身负载

加载 DOM 后将立即执行**[**document . ready()**](https://www.geeksforgeeks.org/how-to-run-a-code-on-document-ready-event-in-jquery/)功能。它不会等待图像、脚本、对象、iframes 等资源被加载。**

**我们的代码中可以有多个 **document.ready()** 函数，但是只允许有一个 **body.onload()** 。**

****示例:****

## **超文本标记语言**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Using jquery library -->
    <script src="https://code.jquery.com/jquery-git.js"></script>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">

</head>

<body onload="loadBody()">
    <h2>GeeksForGeeks</h2>

    <script>
       $(document).ready(function(){
           alert("ready - page loaded")
       })
    </script>
</body>

</html>
```

****输出:****

**![](img/29801d738c15ee559bd9eb869b6d5159.png)

多姆准备好了** 

****body . onload 和 document.ready 的区别:****

<figure class="table">

| 尸体。onload() | 文件。就绪() |
| --- | --- |
| **onload()** It will only be called when everything is loaded. | Call this function as soon as DOM is loaded. |
| It will wait until all resources such as images, iframes, objects, scripts, etc. are loaded. | Called after DOM is loaded. |
| We can only have one **body. onload ()** function. | Our page can have multiple **documents.ready ()** functions. |

</figure>