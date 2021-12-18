# 如何点击将导航菜单的汉堡图标转换成 X？

> 原文:[https://www . geeksforgeeks . org/如何将导航菜单中的汉堡图标转换为点击 x/](https://www.geeksforgeeks.org/how-to-convert-the-hamburger-icon-of-navigation-menu-to-x-on-click/)

导航菜单是网站最重要的部分。它有助于浏览网站。有一个合适的动画不仅使网站看起来很好，而且为客户提供了一个用户友好的界面。因此，这个动画将有可能转换三行或汉堡图标，因为它经常被称为，变成一个 X 点击，反之亦然。
代码将包含 3 个不同的结构，这将使应用这个动画成为可能。HTML 主体、CSS 主体和 JavaScript 主体。
**创建结构:**在本节中，我们将借助 HTML 创建一个基本结构。我们还将添加字体棒极了的链接来生成创建汉堡包图标的线条。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width" />

    <meta http-equiv="X-UA-Compatible"
            content="ie=edge" />

    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" />

    <title>
        Converting the hamburger
        icon to X and vice versa
    </title>
</head>

<body id="bg-img">
    <header>
        <div class="menu-btn">
            <div class="btn-line"></div>
            <div class="btn-line"></div>
            <div class="btn-line"></div>
        </div>

        <nav class="menu">
            <div class="menu-branding">
                <div class="portrait">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200326201748/download312.png"
                        alt="" />
                </div>
            </div>

            <ul class="menu-nav">
                <li class="nav-item current">
                    <a href="#" class="nav-link">
                        HOME</a>
                </li>

                <li class="nav-item">
                    <a href="#" class="nav-link">
                        ABOUT ME</a>
                </li>

                <li class="nav-item">
                    <a href="#" class="nav-link">
                        MY WORK</a>
                </li>

                <li class="nav-item">
                    <a href="#" class="nav-link">
                        CONTACT ME</a>
                </li>
            </ul>
        </nav>
    </header>
</body>

</html>
```

**设计结构:**在上一节中，我们已经创建了汉堡图标的基本结构。在这一节中，我们将借助 CSS 设计结构。

## 钢性铸铁

```html
<style>
    /* Styling the menu button */
    .menu-btn {
        position: absolute;
        z-index: 3;
        right: 35px;
        top: 35px;
        cursor: pointer;
        transition: all 0.5s ease-out;
    }

    /* Styling the hamburger lines */
    .menu-btn .btn-line {
        width: 28px;
        height: 3px;
        margin: 0 0 5px 0;
        background: black;
        transition: all 0.5s ease-out;
    }

    /* Adding transform to the X */
    .menu-btn.close {
        transform: rotate(180deg);
    }

    /* Styling the three lines
        to make it an X */
    .menu-btn.close .btn-line:nth-child(1) {
        transform: rotate(45deg) translate(5px, 5px);
    }

    .menu-btn.close .btn-line:nth-child(2) {
        opacity: 0;
    }

    .menu-btn.close .btn-line:nth-child(3) {
        transform: rotate(-45deg) translate(7px, -6px);
    }

    /* Styling the position of the menu icon */
    .menu {
        position: fixed;
        top: 0;
        width: 100%;
        opacity: 0.9;
        visibility: hidden;
    }

    .menu.show {
        visibility: visible;
    }

    /* Adding a transition delay to the
       4 items in the navigation menu */
    .nav-item:nth-child(1) {
        transition-delay: 0.1s;
    }

    .nav-item:nth-child(2) {
        transition-delay: 0.2s;
    }

    .nav-item:nth-child(3) {
        transition-delay: 0.3s;
    }

    .nav-item:nth-child(4) {
        transition-delay: 0.4s;
    }
</style>
```