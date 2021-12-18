# 如何在网站上播放通知声音？

> 原文:[https://www . geesforgeks . org/如何在网站上播放通知声音/](https://www.geeksforgeeks.org/how-to-play-a-notification-sound-on-websites/)

在网站上播放通知声音有多种方式。在本文中，我们将以三种不同的方式播放通知声音:

*   **在 JavaScript 中使用 Onclick 事件**
*   **在 Javascript 中使用音频类**
*   **使用纯 Jquery:**

下面用 exxampl 代码详细解释了所有过程:

*   **Using Onclick Event in Javascript:** The **[onclick event](https://www.geeksforgeeks.org/html-onclick-event-attribute/)** fires the function when the user clicks on the button. In the following code, the **play1** function is associated with onclick event. Function **play1** receives the name of the audio file, then we select division with **id=sound** and inserts an HTML containing the audio tag.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Notification Sound</title>
            <style>
                body {
                    text-align: center;
                }
                h1 {
                    color: green;
                }
            </style>
            <script>
                function play1() {

                    /* Audio link for notification */
                    var mp3 = '<source src=" " type="audio/mpeg">';
                    document.getElementById("sound").innerHTML = 
                    '<audio autoplay="autoplay">' + mp3 + "</audio>";
                }
            </script>
        </head>
        <body>
            <h1>GeeksforGeeks</h1>
            <b>Notification Sound</b>
            <br>

            <!-- The onclick fires play1 function -->
            <button onclick="play1();">
                Get notification sound
           </button>
            <div id="sound"></div>
        </body>
    </html>
    ```

*   **在 JavaScript 中使用 Audio 类:**这个方法纯粹使用 JavaScript，在 JavaScript 中创建一个 Audio 对象，内置 **[audio.play()方法](https://www.geeksforgeeks.org/html-dom-audio-play-method/)** 。

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Notification Sound</title>
            <style>
                body {
                    text-align: center;
                }
                h1 {
                    color: green;
                }
            </style>
            <script>
                function play2() {

                    /* Audio link for notification */
                    var audio = new Audio(" ");
                    audio.play();
                }
            </script>
        </head>
        <body>
            <h1>GeeksforGeeks</h1>
            <b>Notification Sound</b>
            <br>

            <!-- Plays default sound that is 
                 already set in the function -->
            <button onclick="play2();">
                Get notification sound
            </button>
        </body>
    </html>
    ```

*   **使用纯 Jquery:** 在这个过程中，我们选择播放 id 并与点击事件绑定。在函数中，我们创建一个新的音频文件，然后播放它。

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Notification Sound</title>
            <style>
                body {
                    text-align: center;
                }
                h1 {
                    color: green;
                }
            </style>
            <script>
                $(document).ready(function () {
                    $("#play").click(function () {

                        /* Audio link for notification */
                        var audio = new Audio(" ");
                        audio.play();
                    });
                });
            </script>
        </head>
        <body>
            <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
            </script>

            <h1>GeeksforGeeks</h1>
            <b>Notification Sound</b>
            <br>
            <button id="play">
                Get notification sound
            </button>
        </body>
    </html>
    ```

*   **输出:**对于你使用的任何程序，它都是一样的。
    T3】