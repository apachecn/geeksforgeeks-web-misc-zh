# 什么是可访问性& ARIA 角色在网络应用程序中意味着什么？

> 原文:[https://www . geesforgeks . org/什么是可访问性-aria-角色-网络应用中的手段/](https://www.geeksforgeeks.org/what-is-accessibility-aria-role-means-in-a-web-application/)

**网络应用中的可访问性:**这是一种理念，即该技术必须对残疾人和非残疾人同等无障碍，并且消除访问网络的任何障碍。

**在使网站变得可访问时，谁在得到帮助？**

视力低下或色盲等视觉障碍者，耳聋等听觉障碍者。认知障碍可包括听力障碍者或癫痫患者。身体/运动残疾，如重复性压力损伤、截肢、关节炎。它还可以增强各种其他体验，如互联网连接、嘈杂/繁忙的环境。

ARIA 意味着可访问的丰富的互联网应用程序。它是一组属性，定义了让残障人士更容易访问 web 内容和 web 应用程序的方法。这特别出现在 HTML 5 中。这对那些有视觉障碍的人或那些有残疾的人来说非常有用，他们想使用互联网。一种使用方式是通过屏幕阅读器。它能说出网页上有什么。例如，屏幕阅读器是一个免费的 chrome 扩展。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css" />
</head>

<body>
    <section class="header">
        <nav>
            <a href="/" class="logo">GeeksforGeeks</a>
            <div class="nav-links">
                <ul>
                    <li><a href="/who">who am i</a></li>
                    <li><a href="/services">services</a></li>
                    <li><a href="/contact">contact</a></li>
                </ul>
            </div>
        </nav>
    </section>

    <main>
        <div class="container">
            <h1>About us</h1>
            <p class="subtext">
                We provide a variety of services for you 
                to learn, thrive and also have fun! Free 
                Tutorials, Millions of Articles, Live, 
                Online and Classroom Courses ,Frequent 
                Coding Competitions, Webinars by Industry 
                Experts, Internship opportunities and
                Job Opportunities.
            </p>

            <h2>Read more about our services</h2>

            <ul>
                <li>
                    <h3>Full stack web development:</h3>

                    <p>
                        This course will help you to learn 
                        Full Stack Web Development using:
                        JavaScript, Webpack, React, Redux, 
                        React-Router, Hooks etc. to build 
                        Front-end and Java, Spring / Spring 
                        Boot, JPA / Hibernate, MySQL, RESTful 
                        APIs, Micro-services & related 
                        technologies to build Back-end.
                    </p>
                </li>

                <li>
                    <h3>Competitive Programming:</h3 
                    <p>
                        Looking to be a programmer for a top 
                        company or wishing to top the charts 
                        of leading coding competitions, youve 
                        come to the right place! This live 
                        course will improve your problem-
                        solving skills so you can write 
                        reliable and optimal codes. You will 
                        be mentored by programming experts
                        and they will give you tips and 
                        tricks on which competitions to 
                        participate in and how to succeed in 
                        them!
                    </p>
                </li>

                <li>
                    <h3>System Design:</h3>

                    <p>
                        centric course in which the content 
                        has been designed in a manner that 
                        will prepare you for System Design 
                        interviews for companies like Google, 
                        Amazon, Adobe, Uber, etc. Industry 
                        experts having first-hand experience 
                        will be mentoring and guiding you 
                        throughout the duration of the course.
                    </p>
                </li>
            </ul>
        </div>
    </main>
</body>

</html>
```

CSS 代码:

## style.css

```htmlhtml
* {
    margin: 0;
    padding: 0;
}

body {
    background: palegreen;
}

nav {
    display: flex;
    padding: 2% 6%;
    justify-content: space-between;
    align-items: center;
}

.nav-links {
    flex: 1;
    text-align: right;
}

.nav-links ul li {
    list-style: none;
    display: inline-block;
    padding: 8px 12px;
    position: relative;
}

.nav-links ul li a {
    color: brown;
    text-decoration: none;
    font-size: 20px;
}

.header nav a {
    color: brown;
    text-decoration: none;
    font-size: 30px;
}

.container h1 {
    color: brown;
    text-decoration: none;
    font-size: 30px;
    padding: 8px 80px;
}

.container p {
    font-size: 20px;
    padding: 8px 82px;
}

.container h2 {
    font-size: 30px;
    padding: 8px 70px;
}

.container ul li {
    font-size: 20px;
    padding: 8px 70px;
}
```

**输出:**

<video class="wp-video-shortcode" id="video-638579-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210628180058/ARIA.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210628180058/ARIA.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210628180058/ARIA.mp4)</video>

屏幕阅读器会读取网页上的内容。