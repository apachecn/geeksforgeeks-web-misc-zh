# 语义-界面|嵌入

> 原文:[https://www.geeksforgeeks.org/semantic-ui-embed/](https://www.geeksforgeeks.org/semantic-ui-embed/)

语义 UI 是一个开源框架，它使用 CSS 和 jQuery 来构建出色的用户界面。它和引导程序一样，有很大的不同元素，可以让你的网站看起来更加惊艳。它使用一个类向元素添加 CSS。

内嵌显示来自其他网站的内容，如 YouTube 视频、Vimeo、谷歌地图等。

**例 1:**

这个例子嵌入了 Youtube。

jQuery:

```
$('.ui.embed').embed();

```

**完整代码:**

```
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>
    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />

    <script src="https://code.jquery.com/jquery-3.1.1.min.js"
        integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px"
        class="ui container">
        <div class="ui embed" data-url=
            "https://www.youtube.com/embed/JfiKYgfxCPc"
            data-placeholder=
"https://media.geeksforgeeks.org/wp-content/uploads/20200511124031/image30.png">
        </div>
    </div>

    <script>
        $('.ui.embed').embed();
    </script>
</body>

</html>
```

**输出:**
![](img/ad0295e9d6c79df164347d60947b8d5e.png)

考试 2:

本示例以编程方式指定详细信息。

**jQuery Code:**

```
$('.ui.embed').embed({
    source: 'youtube',
    id: 'JfiKYgfxCPc',
    placeholder: 'https://media.geeksforgeeks.org/wp-content/uploads/20200511124031/image30.png'
});
```

```
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>

    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />

    <script src="https://code.jquery.com/jquery-3.1.1.min.js"
        integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px" 
        class="ui container">
        <div class="ui embed"></div>
    </div>

    <script>
        $('.ui.embed').embed({
            source: 'youtube',
            id: 'JfiKYgfxCPc',
            placeholder:
'https://media.geeksforgeeks.org/wp-content/uploads/20200511124031/image30.png'
        });
    </script>
</body>

</html>
```

输出:
![](img/edaf3f42f706d7eb6cde497f7fb15195.png)