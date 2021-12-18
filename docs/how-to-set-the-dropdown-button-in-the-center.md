# 如何设置中间的下拉按钮？

> 原文:[https://www . geeksforgeeks . org/如何设置中心下拉按钮/](https://www.geeksforgeeks.org/how-to-set-the-dropdown-button-in-the-center/)

下拉菜单是一个提供选项列表供选择的菜单。菜单的标题始终显示，其余项目隐藏。这是一个可切换的菜单，点击它可以显示所有的项目。

通过将下拉 div 的“文本对齐”属性设置为居中，下拉按钮可以位于页面的中心。以下示例包含一个简单的引导下拉菜单，其中添加了一个类“我的菜单”。属性“text-align: center”被添加到类中。

**示例:**这里，属性“text-align: center”将下拉 div 的内容对中，这将下拉按钮设置为居中。

```
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" 
              href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" 
              integrity=
"sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" 
              crossorigin="anonymous" />

        <style>
            .my-menu {
/*Sets all the content of dropdown div to center*/
                text-align: center; 
            }
        </style>
    </head>

    <body>
<!-- my-menu class is added to dropdown div for styling-->
        <div class="dropdown my-menu">
            <button class="btn btn-secondary 
                           dropdown-toggle" 
                    type="button"
                    id="dropdownMenuButton" 
                    data-toggle="dropdown" 
                    aria-haspopup="true" 
                    aria-expanded="false">
                Dropdown button
            </button>
            <div class="dropdown-menu" 
                 aria-labelledby="dropdownMenuButton">
                <a class="dropdown-item" 
                   href="#">Action 1</a>
                <a class="dropdown-item" 
                   href="#">Action 2</a>
                <a class="dropdown-item" 
                   href="#">Action 3</a>
            </div>
        </div>

        <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" 
                integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" 
                crossorigin="anonymous">
      </script>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" 
                integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" 
                crossorigin="anonymous">
      </script>
        <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" 
                integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" 
                crossorigin="anonymous">
      </script>
    </body>
</html>
```

**输出:**

![](img/e2bd42f9efc62e7790b1bb70a319abd0.png)