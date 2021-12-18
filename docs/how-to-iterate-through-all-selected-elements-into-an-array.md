# 如何将所有选中的元素迭代成一个数组？

> 原文:[https://www . geeksforgeeks . org/如何将所有选定的元素迭代到数组中/](https://www.geeksforgeeks.org/how-to-iterate-through-all-selected-elements-into-an-array/)

任务是将所有选定的 HTML 元素添加到一个数组中，并遍历该数组。要实现这一点，第一步是选择所有需要的元素。有几种方法可以做到这一点。

*   **通过 id 查找 HTML 元素:**

    ```html
    var myElement = document.getElementById("element-id");
    ```

    *   **通过标签名查找 HTML 元素:**

    ```html
    var myElements = document.getElementsByTagName("div");
    ```

    *   **按类名查找 HTML 元素:**

    ```html
    var myElements = document.getElementsByClassName( "element-class");
    ```

    *   **Finding HTML elements by CSS selectors:**

    ```html
    var myElements = document.querySelectorAll("div.class-name");
    ```

    第二步包括迭代数组。有几种方法可以做到这一点:

    *   **用于循环。**

    ```html
    array = [ a, b, c, d, e ];
    for (index = 0; index < array.length; index++) { 
        console.log(array[index]); 
    }
    ```

    *   **使用 while 循环。**

    ```html
    index = 0; 
    array = [ a, b, c, d, e ]; 
    while (index < array.length) { 
        console.log(array[index]); 
        index++; 
    }
    ```

    *   **Using forEach method.**

    ```html
    index = 0; 
    array = [ a, b, c, d, e ]; 
    array.forEach(myFunction); 
    function myFunction(item, index) { 
        console.log(item); 
    }
    ```

    **方法:**
    首先使用`[querySelectorAll](https://www.geeksforgeeks.org/html-dom-queryselectorall-method/)`选择器获取所有元素。然后，使用`[forEach()](https://www.geeksforgeeks.org/javascript-array-foreach/)`和`[cloneNode()](https://www.geeksforgeeks.org/html-dom-clonenode-method/)`方法迭代元素。

    **示例 1:**
    在这种方法中，从第一个容器中选择所有`div`元素，将其添加到第二个容器中。

    *   使用 querySelectorAll()获取第一个容器(列表-1)中的所有 div 元素。*   点击按钮(点击我！)来选择元素并将它们附加到第二个容器。*   使用 querySelector()选择第二个容器(列表-2)。*   使用 forEach()方法循环遍历所有 div 元素。*   Clone each div using the cloneNode() method and add it to the second container using appendChild()

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>Demo</title>
        <style>
            /* Basic styling */

            html {
                text-align: center;
                display: block;
                margin: 0 auto;
            }

            h1 {
                color: green;
                text-align: center;
            }

            .list-1,
            .list-2 {
                width: 240px;
                height: 120px;
                text-align: center;
                display: block;
                margin: 0 auto;
                background: lightgreen;
                border: 1px solid #000;
            }

            div,
            button {
                width: 80px;
                height: 20px;
                margin: 14px 78px;
                color: #fff;
                background: green;
                border: 1px solid #000;
            }
        </style>
    </head>

    <body>
        <h1>GeeksforGeeks</h1>
        <div class="list-1">
            <!-- select elements from here -->
            <div>Element 1</div>
            <div>Element 2</div>
            <div>Element 3</div>
        </div>
        <button>Click Me!</button>
        <div class="list-2">
            <!-- add the selected elements here -->
        </div>
        <script>
            var divs = document.querySelectorAll('.list-1 > div');
            var button = document.querySelector('button');
            button.addEventListener("click", () => {
                var list_2 = document.querySelector('.list-2');
                divs.forEach((div) => {
                    list_2.appendChild(div.cloneNode(true));
                })
            });
        </script>
    </body>

    </html>
    ```

    **输出:**
    **点击按钮前:**
    ![](img/ec124e419948ad56035794b02254cd32.png)

    **点击按钮后:**
    ![](img/d0bb02e12d4c405267b786158203a22c.png)

    **附加说明:**
    querySelectorAll()不是一个 JavaScript 方法，它是一个浏览器 API，可以让你访问 DOM 元素。此方法返回节点列表，而不是数组。节点列表和数组的区别在于，节点列表是一种不依赖于语言的访问 DOM 元素的方式，数组是一个 JavaScript 对象，可以用来包含东西的集合。

    **将节点列表转换为数组:**

    ```html
    var divsArr = Array.prototype.slice.call(divs);
    ```