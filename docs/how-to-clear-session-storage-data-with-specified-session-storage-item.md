# 如何清除指定会话存储项的会话存储数据？

> 原文:[https://www . geesforgeks . org/how-clear-session-storage-data-with-specified-session-storage-item/](https://www.geeksforgeeks.org/how-to-clear-session-storage-data-with-specified-session-storage-item/)

在本文中，我们将学习如何通过获取指定的会话存储项，使用 JavaScript 清除浏览器的会话存储。

我们可以通过使用 [**窗口会话存储()**](https://www.geeksforgeeks.org/html-window-sessionstorage-property/) 属性来实现这一点。*窗口* *会话存储()*属性用于在网络浏览器中保存键/值对。它只为一个会话在浏览器中存储键/值对，一旦加载新会话，数据就会过期。

**语法:**

```html
window.sessionStorage
```

我们可以使用 **getItem()** 方法获得指定的会话存储。

```html
sessionStorage.getItem('GFG_Item')
```

我们可以使用 **clear()** 方法清除会话存储。

```html
sessionStorage.clear()
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h4>
        How to clear session storage data 
        with getting the specified session 
        storage item?
    </h4>

    <input type="text" id="text">

    <button onclick="display()">
        Display my item
    </button>

    <p id="display"></p>

    <button onclick="isEmpty()">
        Checking if Empty
    </button>

    <p id="isEmpty"></p>

    <script>

        // Setting items in the local storage
        sessionStorage.setItem('item1', 'Kotlin');
        sessionStorage.setItem('item2', 'Flutter');
        sessionStorage.setItem('item3', 'React');

        function display() {

            // Getting the text value of input field
            let item = document.getElementById('text').value;

            // Getting particular item from the
            // session storage
            let displayItem = sessionStorage.getItem(item);

            // Checking if key exists or not in 
            // the session storage 
            if (displayItem == null) // If key doesn't exist
            {
                document.getElementById('display')
                    .innerText = 'Key does not exist';
            } else {

                // If it exists
                document.getElementById('display')
                    .innerText = displayItem;

                // Clearing the session storage
                sessionStorage.clear();
            }

        }

        // Checking if session storage is empty
        function isEmpty() {

            // If session storage is empty
            if (sessionStorage.length == 0)
                document.getElementById('isEmpty')
                    .innerText = 'It is empty';
            else
                document.getElementById('isEmpty')
                    .innerText = 'It is not empty';
        }
    </script>
</body>

</html>
```

**输出:**

![](img/a2321923b154186c1c253aecf7f69066.png)