# 如何在 ajax 中同时传递表单数据和提交凭证？

> 原文:[https://www . geesforgeks . org/如何在 ajax 提交时传递表单数据和凭据/](https://www.geeksforgeeks.org/how-to-pass-both-form-data-and-credentials-on-submit-in-ajax/)

本文的目的是在一个 HTML 文档中使用 AJAX 将表单数据和凭证发送到 PHP 后端。

**方法:**在 HTML 文档中创建一个带有提交按钮的表单，并为该按钮分配一个 id。在 JavaScript 文件中，向表单的提交按钮添加一个事件监听器，即点击。然后使用 jQuery Ajax 向 PHP 文件发出请求。

**HTML 代码:**

## HTML

```html
<!-- HTML Code -->
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <!-- jQuery Ajax CDN -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

    <!-- JavaScript File -->
    <script src="script.js"></script>

    <!-- Internal CSS -->
    <style>
        .container {
            margin: 35px 0px;
        }

        input,
        textarea,
        button {
            display: block;
            margin: 30px auto;
            outline: none;
            border: 2px solid black;
            border-radius: 5px;
            padding: 5px;
        }

        button {
            cursor: pointer;
            font-size: large;
            font-weight: bolder;
        }

        h1 {
            text-align: center;
        }
    </style>
</head>

<body>
    <div class="container">
        <h1>Demo Form</h1>
        <!-- Form -->
        <form>
            <input type="text" name="name" 
                id="name" placeholder=
                "Enter your Name">

            <input type="text" name="age" 
                id="age" placeholder=
                "Enter your Age">

            <textarea name="aaddress" 
                id="address" cols="30" 
                rows="10" placeholder=
                "Enter your address">
            </textarea>

            <!-- Form Submit Button -->
            <button type="submit" 
                id="submitBtn">
                Submit
            </button>
        </form>
    </div>
</body>

</html>
```