# 如何通过 history.pushState()方法获取历史变更通知？

> 原文:[https://www . geesforgeks . org/how-get-history-changes-notification-via-history-push state-method/](https://www.geeksforgeeks.org/how-to-get-history-changes-notification-via-history-pushstate-method/)

任务是每当调用 **history.pushState()方法**时，检测浏览器历史中的变化。每当调用 **history.pushState()方法**时，为了检测浏览器历史中的变化，我们必须对一个名为 **window.history** 的对象进行修补(改变现有函数的行为，类似于覆盖)。然后，我们将在函数 **history.pushState** 中插入一些我们自己的逻辑，以便每当浏览器的历史发生变化时执行。

**语法:**

```htmlhtml
window.onpopstate = history.onpushstate = function(e) 
    {
      // Code to trigger when the history changes
    };
```

以下示例说明了上述方法:

**示例 1:** 这里我们通过按钮点击来调用 history.pushState 并检测它。单击修改按钮，我们会在控制台中看到历史记录已被修改，新状态已被添加。我们还看到浏览器的网址已经改变，现在指向 test.html，而不是 index.html

```htmlhtml
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 id="Geeks" style="color: green;">
         GeeksforGeeks
        </h1>

        <!-- Button to modify history of browser -->
        <button id="mod">Modify History</button>
    </center>
    <script src=
"https://code.jquery.com/jquery-3.4.1.min.js">
    </script>
    <script type="text/javascript">

        // Monkey patching window.history
        (function(history) {
            var pushState = history.pushState;
            history.pushState = function(state) {
                if (typeof history.onpushstate == "function")
                {
                    history.onpushstate({
                        state: state
                    });
                }
                return pushState.apply(history, arguments);
            }
        })(window.history);
        window.onpopstate = history.onpushstate = function(e)
        {
            console.log('History has been modified!')
            console.log(e)
        };
        $('#mod').click(function() {

            // Adds a gfg state to history and pushes
            // to test.html
            window.history.pushState({
                    gfg: 'Geeks'
                },
                "page 2",
                "test.html");
        });
    </script>
</body>

</html>
```

**输出:**

```htmlhtml
History has been modified!
{state: {gfg: "Geeks"}}

```

**示例 2:** 在本例中，一旦页面加载并检测到，我们将更改浏览器的历史记录。当页面加载时，我们在控制台中看到历史记录已被修改，新状态已被添加。我们还看到浏览器的网址已经改变，现在指向 test.html，而不是 index.html

```htmlhtml
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 id="Geeks" style="color: green;">
          GeeksforGeeks
        </h1>
    </center>
    <script src=
"https://code.jquery.com/jquery-3.4.1.min.js">
    </script>
    <script type="text/javascript">

        // Monkey patching window.history
        (function(history) {
            var pushState = history.pushState;
            history.pushState = function(state) {
                if (typeof history.onpushstate == "function") 
                {
                    history.onpushstate({
                        state: state
                    });
                }
                return pushState.apply(history, arguments);
            }
        })(window.history);
        window.onpopstate = history.onpushstate = function(e) 
        {
            console.log('History has been modified!')
            console.log(e)
        };
        $(document).ready(function() {

            // Adds a gfg state to history and pushes
            // to test.html
            window.history.pushState({
                    gfg: 'Geeks'
                },
                "page 2",
                "test.html");
        });
    </script>
</body>

</html>
```

**输出:**

```htmlhtml
History has been modified!
{state: {gfg: "Geeks"}}

```

**注意:**由于安全原因，window.history.pushState 可能无法在没有服务器的沙盒文档中工作。