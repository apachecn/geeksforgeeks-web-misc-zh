# 如何将窗宽值加载到 SCSS 变量？

> 原文:[https://www . geesforgeks . org/如何将窗口宽度值加载到 scss 变量/](https://www.geeksforgeeks.org/how-to-load-window-width-value-to-scss-variable/)

任务是将窗口宽度值加载到 SCSS 变量中并使用它。让我们简单介绍一下 SCSS。

[SCSS](https://www.geeksforgeeks.org/sass-introduction/) 变量可以存储任何种类的值颜色、字体系列、字体大小、剪辑路径值等，主要用于维护跨样式表的代码的可重用性。

**进场:**

*   **步骤 1:** 在 SCSS 定义一个函数，并生成精确的视口宽度值以获取窗口宽度

    ```
    @function get-vw($target) { 
      $vw-context: (1000*.01) * 1px;
      @return ($target/$vw-context) * 1vw;
    }
    ```

*   **步骤 2:** 将像素值传入该函数，并将其存储在 SCSS 变量中。

    ```
    $window-width: get-vw(72px);
    ```

    因为视口宽度是视口的 1%，所以我们可以用 px 作为比例来缩放尺寸。

    **步骤 3:** 在需要的地方使用变量。

    ## main . scss

    ```
    $window-width: get-vw(72px); /* Passing in a value in pixels */

    /* Defining the function to generate the window width* /
    @function get-vw($target) { 
      $vw-context: (1000*.01) * 1px;
      @return ($target/$vw-context) * 1vw;
    }

    /* Setting the default values*/
    *{
      padding : 0;
      margin : 0;
      box-sizing: border-box;
    }

    /* Using the property*/
    .misc{
      padding: 3rem 0;
      color: #fff;
      width: $window-width;
      text-align: center;
      font-size: 1.8rem;
      background-color:green;
    }
    ```

    **输出:**这将产生以下 CSS。

    ## main . CSS-主文件

    ```
    /* Passing in a value in pixels */
    /* Defining the function to generate the window width*/
    /* Setting the default values*/
    * {
      padding: 0;
      margin: 0;
      box-sizing: border-box;
    }

    /* Using the property */
    .misc {
      padding: 3rem 0;
      color: #fff;
      width: get-vw(72px);
      text-align: center;
      font-size: 1.8rem;
      background-color: green;
    }
    ```

    **注意:**这里，提到*框大小:边框框*在这里真的很重要，因为这将渲染 DOM 以移除任何默认的边距或空格。

    ## index.html

    ```
    <!DOCTYPE html>
        <html>
         <body>
            <div class="misc">
               GeeksforGeeks
            </div>
         </body>
    </html>
    ```

    **输出:**这里，我们的文本正在占据其当前屏幕的整个宽度。

    ![](img/ac495dca88d9cb35779f31a993f1e611.png)

    **注意:**虽然有像 window.outerWidth 这样的 javascript 方法，但是我们不可能将这些值存储在 SCSS 变量中，因为 SCSS 只是一个预处理器。