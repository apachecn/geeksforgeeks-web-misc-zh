# 如何在图像文件中插入视频链接？

> 原文:[https://www . geesforgeks . org/如何在图像文件中插入视频链接/](https://www.geeksforgeeks.org/how-to-insert-a-video-link-within-an-image-file/)

**在图像文件中插入视频链接主要有两种方法:**

**方法 1:**

将包含视频的 HTML 文件与不同 HTML 文件中的图像链接起来。

**Steps:**

*   创建一个 html 文件并添加视频。
    **语法:**

    ```htmlhtml
    <video src="video_url" controls></video>
    ```

    *   创建另一个包含该图像的 HTML 文件，其中该图像应该包含前一个 HTML 文件的链接。
    **语法:**

    ```htmlhtml
    <a href="html_file_url">
                <img src="image_url">
    </a>
    ```

    **示例:**下面是有视频的 HTML 文件。

    ## 视频 source.html

    ```htmlhtml
    <!DOCTYPE html>
    <html>
        <body bgcolor="black">
            <!--adding the video file-->
            <video width="50%" 
                   height="50%"
                   src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200513195558/Placement100-_-GeeksforGeeks-1.mp4" 
                   controls>
          </video>
        </body>
    </html>
    ```

    下面是具有图像的主文件，其中图像与上面的 HTML 文件相链接。

    ## web.html

    ```htmlhtml
    <!DOCTYPE html>
    <html>
        <body bgcolor="black">
            <!--Adding the image file-->
            <!--also adding the link of video source.html to the image-->
            <a href=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200513195558/Placement100-_-GeeksforGeeks-1.mp4">
                <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200717172614/authPreLogo.png" 
                     width="100" 
                     height="100" />
            </a>
        </body>
    </html>
    ```

    **输出:**

    ![](img/fa037da0dada183242964a91d19e2cff.png)

    **方法二:**

    创建一个包含图像和视频的 HTML 文件。点击图像，视频打开。

    **步骤:**

    *   用图像创建一个 HTML 文件。*   Add link for the video to that image.
    **Syntax:**

    ```htmlhtml
    <video poster="image_url">
         <source src="video_url" type="video_type">
    </video>
    ```

    **示例:**下面是主 html 文件。

    ```htmlhtml
    <!DOCTYPE html>
    <!--web.html.html-->
    <html>

       <body bgcolor="black">
          <p align='center'>  

            <!--Adding the video file along with the image-->
            <video controls 
                   width="400" 
                  height="200" 
                  poster=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200717172614/authPreLogo.png">
                <source src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20200513195558/Placement100-_-GeeksforGeeks-1.mp4"
                        type="video/mp4">
            </video>

          </p>
       </body>

    </html>
    ```

    **输出:**

    ![](img/9c0ea24afd2d7c7c7f157d21a3651ca2.png)