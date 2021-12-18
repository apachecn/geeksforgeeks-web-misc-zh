# 使用可解除警戒时如何移除额外的右边距？

> 原文:[https://www . geeksforgeeks . org/如何删除使用时的额外右边距-警告-可忽略/](https://www.geeksforgeeks.org/how-to-remove-extra-right-margin-when-using-alert-dismissible/)

通过使用警报 JavaScript 插件，可以内嵌消除任何警报。

*   请确保您已经加载了**警报插件**，或者**编译的引导 JavaScript** 。
*   它需要 util.js ，如果你正在从源**构建 JavaScript。**编译版包含了这个。
*   我们可以添加一个关闭按钮和**。警报解除**类，它在警报的右侧添加了额外的填充，并定位**。关闭**按钮。
*   在消除按钮上，添加**数据-消除=“警报”**属性，这将触发 JavaScript 功能。请务必使用 **<按钮>** 元素，以便在所有设备上正常运行。
*   可以添加**。淡化**和**。取消警报时，显示**类来激活警报。

**示例:**

## 超文本标记语言

```htmlhtml
<!doctype html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,
        initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
        integrity=
"sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk"
        crossorigin="anonymous">

    <!-- JavaScript Plugins -->
    <!-- jQuery first, then Popper.js,
         then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
        integrity=
"sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
        integrity=
"sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
        crossorigin="anonymous">
    </script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js"
        integrity=
"sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI"
        crossorigin="anonymous">
    </script>

    <title>
        How to Remove extra right margin 
        when using alert-dismissible?
    </title>
</head>

<body>
    <div class="container">
        <a class="navbar-brand text-success" href="#">
            Geeksforgeeks
        </a>
        <div class="alert alert-warning alert-dismissible
                fade show" role="alert">
            <b>Hello Everyone!</b> 
            click on 'x' symbol to close

            <button type="button" class="close" 
                data-dismiss="alert" aria-label="Close">
                <span aria-hidden="true">×</span>
            </button>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/54934ab5c92f498fb5783ee494e70ebb.png)

**使用 JavaScript 触发器:**启用通过 JavaScript 消除警报:

```htmlhtml
$('.alert').alert()

```

或者在警报内的按钮上显示数据属性，如上所示:

```htmlhtml
<button type="button" class="close" 
        data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
</button>

```

请注意，关闭警报会将其从 DOM 中移除。

**示例:**

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,
            initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
        integrity=
"sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk"
        crossorigin="anonymous">

    <!-- JavaScript Plugins -->
    <!-- jQuery first, then Popper.js,
         then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
        integrity=
"sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
        integrity=
"sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
        crossorigin="anonymous">
    </script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js"
        integrity=
"sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI"
        crossorigin="anonymous">
    </script>

    <style type="text/css">
        .fade {
            -webkit-transition-duration: 7s;

            /* Safari */
            transition-duration: 7s;
        }
    </style>
</head>

<body>
    <div class="container">
        <a class="navbar-brand text-success"
                href="#">
            Geeksforgeeks
        </a>
        <h2>
            Alert dismiss using 
            javascript trigger
        </h2>
        <div class="alert alert-warning fade show">
            <b>Hello Everyone!</b> 
            click on 'x' symbol to close
        </div>
    </div>

    <!-- JavaScript trigger-->
    <script>
        $(document).ready(function () {
            $(".alert").alert('close');
        }); 
    </script>
</body>

</html>
```

**输出:**

![](img/40cab64e504fd939530c3880cd2408df.png)

**注意:**7 秒后警报会自动解除。

**警报-解除:****警报**–**解除**类在**警报**的右侧添加了额外的填充并定位。关闭按钮。在消除按钮上，添加数据-消除=" **警报**"属性，这将触发 JavaScript 功能。请确保在所有设备上正确使用元素。

使用 alert-disable 时如何去除额外的右边距？

**例** **:**

## 超文本标记语言

```htmlhtml
<!doctype html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,
            initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css"
        integrity=
"sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk"
        crossorigin="anonymous">

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, 
         then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
        integrity=
"sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
        integrity=
"sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
        crossorigin="anonymous">
    </script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js"
        integrity=
"sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI"
        crossorigin="anonymous">
    </script>

    <title>
        Remove extra right margin 
        using alert-dismissible
    </title>

    <style type="text/css">
        .alert-dismissible {
            margin-right: 100px;

            /* Reset pixel value */
            padding-right: 0px;
        }
    </style>
</head>

<body>
    <div class="container">
        <a class="navbar-brand text-success" href="#">
            Geeksforgeeks
        </a>
        <div class="alert alert-warning alert-dismissible
                fade show" role="alert">
            <b>Hello Everyone!</b> 
            click on 'x' symbol to close

            <button type="button" class="close" 
                data-dismiss="alert" aria-label="Close">
                <span aria-hidden="true">×</span>
            </button>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/67a32fbff13d46b51ca80fb65987108b.png)