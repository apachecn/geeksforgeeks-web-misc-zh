# 语义-用户界面|占位符

> 原文:[https://www.geeksforgeeks.org/semantic-ui-placeholder/](https://www.geeksforgeeks.org/semantic-ui-placeholder/)

**语义 UI** 是一个开源框架，使用 CSS 和 jQuery 来构建出色的用户界面。它和引导程序一样，有很大的不同元素，可以让你的网站看起来更加惊艳。它使用一个类向元素添加 CSS。占位符用于为即将出现在布局中的内容保留空间。

以下是不同类型占位符的示例。

**例 1:**

```
<!DOCTYPE html>
<html>
    <head>
        <title>Semantic UI</title>
        <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css" 
              rel="stylesheet" />
    </head>
    <body>
        <div class="ui container">
            <h2>Placeholder</h2>
            <div class="ui placeholder">
                <div class="image header">
                    <div class="line"></div>
                    <div class="line"></div>
                </div>
                <div class="paragraph">
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                </div>
            </div>
        </div>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
    </body>
</html>
```

**输出**
![](img/51b758107a692989f1e15152bb2c3257.png)

**例 2:**

```
<!DOCTYPE html>
<html>
    <head>
        <title>Semantic UI</title>
        <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css" 
              rel="stylesheet" />
    </head>
    <body>
        <div class="ui container">
            <h3>Inline Card Placeholder</h3>
            <div class="ui four column grid">
                <div class="column">
                    <div class="ui raised segment">
                        <div class="ui placeholder">
                            <div class="image header">
                                <div class="short line"></div>
                                <div class="medium line"></div>
                            </div>
                            <div class="paragraph">
                                <div class="large line"></div>
                                <div class="medium line"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="column">
                    <div class="ui raised segment">
                        <div class="ui placeholder">
                            <div class="image header">
                                <div class="short line"></div>
                                <div class="medium line"></div>
                            </div>
                            <div class="paragraph">
                                <div class="large line"></div>
                                <div class="medium line"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="column">
                    <div class="ui raised segment">
                        <div class="ui placeholder">
                            <div class="image header">
                                <div class="short line"></div>
                                <div class="medium line"></div>
                            </div>
                            <div class="paragraph">
                                <div class="large line"></div>
                                <div class="medium line"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="column">
                    <div class="ui raised segment">
                        <div class="ui placeholder">
                            <div class="image header">
                                <div class="short line"></div>
                                <div class="medium line"></div>
                            </div>
                            <div class="paragraph">
                                <div class="large line"></div>
                                <div class="medium line"></div>
                            </div>
                        </div>
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

**输出**T2】

**示例 3:** 这是 Image 的占位符。

```
<!DOCTYPE html>
<html>
    <head>
        <title>Semantic UI</title>
        <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css" 
              rel="stylesheet" />
    </head>
    <body>
        <div class="ui container">
            <h3>Placeholder for Images</h3>
            <div style="width: 150px;" 
                 class="ui placeholder">
                <div class="image"></div>
            </div>
            <div style="width: 150px;" 
                 class="ui placeholder">
                <div class="image"></div>
            </div>
        </div>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
        </script>
    </body>
</html>
```

**输出**T2】

**示例 4:** 这是针对反转占位符的。

```
<!DOCTYPE html>
<html>
    <head>
        <title>Semantic UI</title>
        <link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css" 
              rel="stylesheet" />
    </head>
    <body>
        <div class="ui container">
            <h3>Inverted Placeholders</h3>
            <div class="ui inverted segment">
                <div class="ui active inverted placeholder">
                    <div class="image header">
                        <div class="line"></div>
                        <div class="line"></div>
                    </div>
                    <div class="paragraph">
                        <div class="line"></div>
                        <div class="line"></div>
                        <div class="line"></div>
                    </div>
                </div>
            </div>
            <div class="ui inverted segment">
                <div class="ui active inverted placeholder">
                    <div class="image header">
                        <div class="line"></div>
                        <div class="line"></div>
                    </div>
                    <div class="paragraph">
                        <div class="line"></div>
                        <div class="line"></div>
                        <div class="line"></div>
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

**输出**T2】