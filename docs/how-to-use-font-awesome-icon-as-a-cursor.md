# 如何使用字体牛逼图标作为光标？

> 原文:[https://www . geesforgeks . org/如何使用-字体-真棒-图标作为光标/](https://www.geeksforgeeks.org/how-to-use-font-awesome-icon-as-a-cursor/)

让一个简单的光标看起来像汽车、饮料、表情符号或任何其他形状或符号看起来很迷人。我们实际上可以将光标更改为网页上任何字体的牛逼图标。为了给光标添加任何字体棒的图标，我们需要在标题部分添加字体棒的 CDN。

有一个 CSS **光标**属性可以改变光标的类型。它还允许在光标属性中添加图像。

```htmlhtml
cursor: url(cursor1.png) 4 12, auto;
```

因此，要添加一个“字体棒极了”图标作为光标，我们首先需要将“字体棒极了”图标制作成图像。我们可以借助 HTML 中的画布来做到这一点。然后将该图像作为光标属性的 URL 提供。

**示例:**

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width,initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link href=
"https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css"
        rel="stylesheet" />
    <script src=
        "https://code.jquery.com/jquery-2.1.1.min.js">
    </script>
    <title>Font Awesome Cursor</title>

    <style>
        body {
            position: fixed;
            left: 0;
            right: 0;
            top: 0;
            bottom: 0;
        }

        p {
            color: #4cb96b;
        }
    </style>
</head>

<body>
    <p>GeeksforGeeks</p>

    <script>
        $(function () {
            var canvas = document.createElement("canvas");

            // Width and height of canvas can
            // be varied depending on the
            // size of icon
            canvas.width = 30;
            canvas.height = 28;

            // Set interval for allowing the
            // font awesome icon to load
            setInterval(() => {
                var ctx = canvas.getContext("2d");

                // Setting the color of the icon
                ctx.fillStyle = "#4CB96B";

                // Set size of cursor
                ctx.font = "24px fontawesome";

                // '\uf0f9' is the unicode of
                // the font awesome icon
                ctx.fillText("\uf25a", 0, 20);

                // Converting the canvas to image
                var dataURL = canvas.toDataURL("image/png");

                // Setting the cursor property
                // to the image created
                $("body").css(
                    "cursor", "url(" + dataURL + "), auto");
            }, 1000);
        });
    </script>
</body>

</html>
```

**输出:**
![output](img/67b38b36e8a240aa1a2ab5e889133de4.png)

字体牛逼图标的所有 Unicode 都可以在*https://fontawesome.com/cheatsheet*找到

**font awesome cdn link:***https://maxcdn . bootstracdn . com/font-awesome/4 . 5 . 0/CSS/font-awesome . min . CSS*