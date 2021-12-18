# 如何使用 div 作为推特 Popover 的内容？

> 原文:[https://www . geesforgeks . org/a-div-as-content-for-twiters-Popo ver/](https://www.geeksforgeeks.org/how-to-use-a-div-as-content-for-twitters-popover/)

![](img/dcae18163b662573dcb253c41407b071.png) [推特的 Popover](https://www.geeksforgeeks.org/bootstrap-4-popover/) 是一个引导组件，有点类似于工具提示，突出显示的区别在于，每当用户点击指定的选择器时，它就会被触发。在我们使用< div >作为 popover 里面的内容之前，让我们来看看 popover 的 DOM 结构:

**程序:**popover 的 DOM 结构。

```html
<!-- DOM structure template for the popover
     id's and attributes are usually specified
     automatically -->
<div class="popover fade show" 
     role="tooltip" 
     id="popover_XYZ"
     style="position: absolute; 
            will-change: transform;
            top: 0px; left: 0px; 
            transform: translate3d(6px, 360px, 0px);"
     x-placement="bottom">
    <div class="arrow" style="left: 80px;"></div>
    <h3 class="popover-header">Popover Header here</h3>
    <div class="popover-body">Popover Content here</div>
</div>
```

**输出:**
![](img/3e73315be48315756cc57e5dbb3a5e0a.png)

**pop ver 内部的 Div:**默认情况下，我们不能在 pop ver 内部定义 HTML。为此，我们将 **html** 选项设置为**“真”**，以允许在初始阶段初始化时弹出窗口中的 html 内容。将 HTML div 内容存储在变量中，将变量初始化为弹出窗口选项。

*   **语法:**

    ```html
    $([selector]).popover({ html:true; title:[header]; content:[Content] });
    ```

*   **例:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="utf-8">
        <meta name="viewport"
              content="width=device-width, initial-scale=1">

        <!-- CDN's Required -->
        <link rel="stylesheet" href=
    "https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
        <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
        </script>
        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js">
        </script>
        <script src=
    "https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js">
        </script>
    </head>

    <body>
        <br>
        <br>
        <center>
            <div class="container">

                <!-- Data for popover header -->
                <div class="pickHead">
                    <h3 class="text text-success">
                      GeeksforGeeks
                    </h3>
                </div>

                <!-- Data for popover content -->
                <div class="pickData">
                    <div class="text">
                      A computer science portal for Geeks
                    </div>
                </div>
                <br>
                <br>

                <!-- Popover Button -->
                <button class="btn btn-success" 
                        data-toggle="popover">
                  Twitter's popover
                </button>
            </div>
        </center>
        <script>

            // Pick the div data as required
            var head = "" + $('.pickHead').html();
            var data = "" + $('.pickData').html();

            // Append the html data as the options
            $(document).ready(function() {
                $('[data-toggle="popover"]').popover({
                    html: true,
                    title: head,
                    content: data
                });
            });
        </script>
    </body>

    </html>
    ```

*   **输出:**
    ![](img/837076501f061f1b589de34f8e0df94d.png)