# 语义-UI |统计

> 原文:[https://www.geeksforgeeks.org/semantic-ui-statistics/](https://www.geeksforgeeks.org/semantic-ui-statistics/)

语义 UI 是一个开源框架，它使用 CSS 和 jQuery 来构建出色的用户界面。它和引导程序一样，有很大的不同元素，可以让你的网站看起来更加惊艳。它使用一个类向元素添加 CSS。统计数据显示属性的当前值。

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>
    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />
</head>

<body>
    <div style="margin-top: 20px" 
            class="ui container">
        <div class="ui statistic">
            <div class="value">
                14, 080
            </div>
            <div class="label">
                Views
            </div>
        </div>
    </div>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</body>

</html>
```

**输出:**
![](img/a6b7b7f1daa43784dba1036dcf96a152.png)

**示例 2:** 统计组

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>
    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui statistic">
            <div class="ui statistics">
                <div class="statistic">
                    <div class="value">
                        150
                    </div>
                    <div class="label">
                        Likes
                    </div>
                </div>
                <div class="statistic">
                    <div class="value">
                        280
                    </div>
                    <div class="label">
                        Comments
                    </div>
                </div>
                <div class="statistic">
                    <div class="value">
                        12
                    </div>
                    <div class="label">
                        Shares
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/fb0e5698bb335093e57042d4ac82ac3d.png)

**示例 3:** 带图像和图标的统计

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>
    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui statistics">
            <div class="statistic">
                <div class="value">
                    <i class="world icon"></i> 580
                </div>
                <div class="label">
                    Notifications
                </div>
            </div>
            <div class="statistic">
                <div class="value">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200510132051/image30.png"
                        class="ui circular inline image">
                    200k
                </div>
                <div class="label">
                    Followers
                </div>
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/556d2683d291ceb9a15890bce37763a7.png)

**例 4:** 水平

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>
    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui horizontal statistic">
            <div class="value">
                20
            </div>
            <div class="label">
                Downloads
            </div>
        </div>
    </div>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</body>

</html>
```

**输出:**
![](img/ce66169df5cf68bf7a353397d90d0801.png)

**示例 5:** 彩色统计

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI</title>
    <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
        rel="stylesheet" />
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui statistics">
            <div class="red statistic">
                <div class="value">
                    207
                </div>
                <div class="label">
                    Views
                </div>
            </div>
            <div class="orange statistic">
                <div class="value">
                    78
                </div>
                <div class="label">
                    Likes
                </div>
            </div>
        </div>
    </div>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</body>

</html>
```

**输出:**
![](img/87759bc147ce4b53e0356b4335b8f9a2.png)