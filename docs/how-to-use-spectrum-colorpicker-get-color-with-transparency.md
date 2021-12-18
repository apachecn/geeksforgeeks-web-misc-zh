# 如何使用光谱拾色器获得具有透明度的颜色？

> 原文:[https://www . geesforgeks . org/如何使用-光谱-颜色选择器-透明获取颜色/](https://www.geeksforgeeks.org/how-to-use-spectrum-colorpicker-get-color-with-transparency/)

光谱是光被棱镜散射时产生的颜色分布。使用光谱，可以从对话框中轻松选择所需的颜色。通过在选取器区域内单击并拖动光标来突出显示颜色，可以使用光谱。在开发领域，因为它起着至关重要的作用&便于从光谱中选择范围广泛的颜色。

Spectrum 提供了一个名为 showAlpha 的属性，用于获取颜色透明度。showAlpha 是查询插件 Spectrum 的一个属性，可以设置为 true 以获得颜色的透明度，否则设置为 false 以避免透明度。

**语法:**

```html
$("#colorpicker").spectrum({
   showAlpha: boolean
}); 
```

**方法:**为了构建光谱颜色选择器，我们必须遵循某些要点:

1.  从 Html 文件中的 jquery & spectrum CDN 添加必要的库文件。
2.  将 id 为*的标签声明为输出&输入标签为*拾色器*，该标签声明在< div >标签之外。*
3.  为光谱声明一个便于选择颜色的函数&将 showAlpha 的值设置为 true。

**用颜色透明度属性实现光谱**

*   **第一步:**在你的 HTML 文件中包含 Spectrum JQuery CDN。

*   **第二步:**在你的 HTML 文件中包含光谱 CDN。

    > < link rel= "样式表" type = " text/CSS " href = " https://cdnjs . cloudflare . com/Ajax/libs/spectrum/1 . 8 . 0/spectrum . min . CSS ">

*   **步骤 3:** 在你的 HTML 文件的<主体>中添加一个颜色选择器和输出 div。

    > ## GeeksforGeeks
    > 
    > <输入 type = " text " id = " color picker "/>

*   **第四步:**将光谱 JQuery 添加到<脚本>

    ```html
    $(document).ready(function(){
        $('#colorPicker').spectrum({
            color: '#fff',
            showAlpha: true,
            move: function(color){
                $('#output').css(
                    'background-color', color.toRgbString());
            }
        });
    });
    ```

**示例:**您现在可以使用带有透明度的光谱颜色选择器了。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Spectrum Sample</title>

    <!-- Include JQuery and Spectrum CDN -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.min.js">
    </script>

    <link rel="stylesheet" type="text/css"
        href=
"https://cdnjs.cloudflare.com/ajax/libs/spectrum/1.8.0/spectrum.min.css" />
</head>

<body>
    <!-- Output div to show output color -->
    <div id="output" style="height: 200px; width: 200px">
        <h2>GeeksforGeeks</h2>
    </div>

    <!-- Spectrum colorpicker -->
    <input type="text" id="colorPicker" />

    <script>

        // jQuery to show selected color in 
        // the ouput of body tag.
        $(document).ready(function () {
            $("#colorPicker").spectrum({
                color: "#fff",

                // showApla set true to get 
                // transparency slider in 
                // the spectrum.
                showAlpha: true,
                move: function (color) {
                    $("#output").css(
                        "background-color", 
                        color.toRgbString());
                },
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/b28db59de4d1897335e393a80f154836.png)