# 如何将文本放入创建的图标中？

> 原文:[https://www . geesforgeks . org/如何将文本放入已创建的图标中/](https://www.geeksforgeeks.org/how-to-put-the-text-inside-of-a-created-icon/)

任务是将文本放入创建的图标中。这篇文章将讨论一些不同的方法，你可以把一个文本放在一个创建的图标/图像里面/上面。所有讨论的解决方案都遵循基于相同基本思想的不同演示，即在图像/图标上书写/放置文本，使用除法使图像/图标成为背景图像/图标，然后书写文本。

*   **Solution 1:**

    ```html
    <!DOCTYPE html>
    <html>
        <head> </head>
        <body>
            <!--Add HTML:-->

            <div class="container">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200728095608/geeksforgeeks56-300x68.png" 
                     alt="GFG"
                     style="width: 100%;" />
                <div class="text-block">
                    <h4>Programming</h4>
                    <p>Geeks For Geeks</p>
                </div>
            </div>

            <style>
                //Add CSS:
                * {
                    box-sizing: border-box;
                }

                /* Container holding the image and the text */
                .container {
                    position: relative;
                }

                /* Bottom right text */
                .text-block {
                    position: absolute;
                    bottom: 0px;
                    right: 20px;
                    background-color: black;
                    color: white;
                    padding-left: 20px;
                    padding-right: 20px;
                }
            </style>
        </body>
    </html>
    ```

    **输出:**
    ![](img/ef0ac3ff083b6f7f0ade95e3db9c48f2.png)

    **解释:**使用。容器划分我们将图像作为背景图像，然后使用样式。文本块分割我们制作一个框，其中包含文本，并将其放置在绝对位置(该值告诉浏览器，无论将要放置什么，都应该从文档的正常流中移除，而是放置在页面上的确切位置)，并使用 CSS 进行首选样式。

*   **Solution 2:**

    ```html
    <!DOCTYPE html>
    <html>
        <head> </head>
        <body>
            <!-- Write HTML code here -->

            <div class="container">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200728095608/geeksforgeeks56-300x68.png" 
                     alt="GFG" 
                     style="width: 100%;" />
                <div class="content">
                    <h1>Heading</h1>
                    <p>Geeks For Geeks</p>
                </div>
            </div>

            <style>
                // CSS Code
                * {
                    box-sizing: border-box;
                }

                .container {
                    position: relative;
                    max-width: 800px; /* Maximum width */
                    margin: 0 auto; /* Center it */
                }

                .container .content {
                   /* Position the background text */
                    position: absolute;
         /* At the bottom. Use top:0 to append it to the top */
                    bottom: 0px; 
                  /* Black background with 0.5 opacity */
                    background: rgba(0, 0, 0, 0.3); 
                    color: #f1f1f1; /* Grey text */
                    width: 100%; /* Full width */
                    padding: 20px; /* Some padding */
                }
            </style>
        </body>
    </html>
    ```

    **输出:**
    ![](img/319cd0339298aeeffbd5b5199650e04c.png)

    **说明:**使用与上面相同的方法，但不是创建文本框，我们在这种方法中将内容覆盖在图像/图标上，而是简单地使用 CSS 调整分割的宽度属性，即设置“宽度:100%；”使文本覆盖在图像/图标的整个宽度上。

*   **Solution 3:** Hover the mouse over the Image

    ```html
    <!DOCTYPE html>
    <html>
        <head> </head>
        <body>
            <!-- Write HTML code here -->

            <div class="container">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200728095608/geeksforgeeks56-300x68.png" 
                     alt="GFG"
                     style="width: 100%;" />
                <div class="overlay">Geeks For Geeks</div>
            </div>

            <style>
                * {
                    box-sizing: border-box;
                }

                /* Container needed to position
              the overlay. Adjust the width as needed */
                .container {
                    position: relative;
                }

                /* Make the image to responsive */
                .image {
                    display: block;
                    width: 100%;
                    height: auto;
                }

                /* The overlay effect - lays on top of 
              the container and over the image */
                .overlay {
                    position: absolute;
                    bottom: 0;
                  /* Black see-through */
                    background: rgba(0, 0, 0, 0.5); 
                    color: #f1f1f1;
                    width: 100%;
                    transition: 0.5s ease;
                    opacity: 0;
                    color: white;
                    font-size: 20px;
                    padding: 20px;
                    text-align: center;
                }

                /* When you mouse over the 
              container, fade in the overlay title */
                .container:hover .overlay {
                    opacity: 1;
                }
            </style>
        </body>
    </html>
    ```

    **输出:**
    **原:**
    ![](img/e188ae9cb5b6828d99f15eae9fa608d7.png)

    **悬停时:**
    ![](img/bc3afc17a674f452fe8045406531b614.png)

    **说明:**在本解决方案中，我们将图像/图标作为背景图像/图标，并将文本覆盖在图像上，作为上述解决方案，但使用“不透明度:0”使文本/内容消失造型。叠加分割，当用户悬停在图像上时，我们再次使用“不透明度:1”设置可见的不透明度。