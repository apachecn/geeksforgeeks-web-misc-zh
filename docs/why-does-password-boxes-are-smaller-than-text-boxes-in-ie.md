# 为什么 IE 中密码框比文本框小？

> 原文:[https://www . geesforgeks . org/为什么密码盒比 ie 中的文本框小/](https://www.geeksforgeeks.org/why-does-password-boxes-are-smaller-than-text-boxes-in-ie/)

根据微软的说法，每当 Internet Explorer 提供 HTML 页面结构时，即使在 META 标签提供了正确的字符集之后，它也会使用错误的字符集。

**用户输入的 HTML 部分:**下面的 HTML 代码展示了通用的密码输入表单，在谷歌 Chrome、火狐、微软 Edge 中运行良好，但在 **IE** 中则不运行。在 IE 的情况下，即使我们指定“*字符集=‘UTF-8’*”，输入框的宽度也是不同的。

```htmlhtml
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <title>GeeksforGeeks</title>
</head>

<body>
  <form>
    <p>
      <label>TEXT INPUT:</label>
      <br>
      <input type="text">
      <br>
      <label>PASSWORD INPUT:</label>
      <br>
      <input type="password">
    </p>
  </form>
</body>

</html>
```

**注意:**IE 出现这种异常行为的原因在文档中有详细说明，链接如下。
在渲染 html 时使用错误的字符集

**解决方案:**众所周知，IE 的默认字符集有些问题。
让我们研究一些解决这个问题的方法。

1.  **使用 jQuery 的解决方案:**jQuery 代码包含在页面加载中。使用 jQuery 制作等宽的文本和密码输入控制框。

    ```htmlhtml
    <!DOCTYPE html>
    <html>

    <head>
      <meta charset="UTF-8">
      <title>GeeksforGeeks</title>

      <script src=
    "https://code.jquery.com/jquery-3.5.1.min.js"
        integrity=
    "sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
        crossorigin="anonymous">
      </script>

      <script type="text/javascript">
        $(document).ready(function () {
          $("input[type='text']").height(
            $("input[type='password']").height());

          $("input[type='text']").width(
            $("input[type='password']").width());
        });
      </script>
    </head>

    <body>
      <form>
        <p>
          <label>TEXT INPUT:</label>
          <br>
          <input type="text">
          <br>
          <label>PASSWORD INPUT:</label>
          <br>
          <input type="password">
        </p>
      </form>
    </body>

    </html>
    ```

    或者

    ```htmlhtml
    <!DOCTYPE html>
    <html>

    <head>
      <meta charset="UTF-8">
      <title>GeeksforGeeks</title>

      <script src=
    "https://code.jquery.com/jquery-3.5.1.min.js"
        integrity=
    "sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
        crossorigin="anonymous">
      </script>

      <script type="text/javascript">
        $(document).ready(function () {
          $("input[type='password']").height(
            $("input[type='text']").height());

          $("input[type='password']").width(
            $("input[type='text']").width());
        });
      </script>
    </head>

    <body>
      <form>
        <p>
          <label>TEXT INPUT:</label>
          <br>
          <input type="text">
          <br>
          <label>PASSWORD INPUT:</label>
          <br>
          <input type="password">
        </p>
      </form>
    </body>

    </html>
    ```

2.  **使用 CSS 的解决方案:**根据您的项目，将两个输入控件的宽度固定为某个值。这里使用的是“14em”宽度，只需将其更改为所需宽度的值。

    ```htmlhtml
    <!DOCTYPE html>
    <html>

    <head>
      <meta charset="UTF-8">
      <title>GeeksforGeeks</title>
      <style type="text/css">
        input {
          width: 14em;
        }
      </style>
    </head>

    <body>
      <form>
        <p>
          <label>TEXT INPUT:</label>
          <br>
          <input type="text">
          <br>
          <label>PASSWORD INPUT:</label>
          <br>
          <input type="password">
        </p>
      </form>
    </body>

    </html>
    ```

3.  **通过设置输入的默认字体系列:(最喜欢的解决方案)**该方法对所有输入使用相同的字体系列。

    ```htmlhtml
    <!DOCTYPE html>
    <html>

    <head>
      <meta charset="UTF-8">
      <title>GeeksforGeeks</title>
      <style type="text/css">
        input {
          font-family: sans-serif;
        }
      </style>
    </head>

    <body>
      <form>
        <p>
          <label>TEXT INPUT:</label>
          <br>
          <input type="text">
          <br>
          <label>PASSWORD INPUT:</label>
          <br>
          <input type="password">
        </p>
      </form>
    </body>

    </html>
    ```