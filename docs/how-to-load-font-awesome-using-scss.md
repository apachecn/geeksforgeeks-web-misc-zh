# 如何使用 SCSS 加载字体-牛逼？

> 原文:[https://www . geesforgeks . org/how-load-font-awesome-using-scss/](https://www.geeksforgeeks.org/how-to-load-font-awesome-using-scss/)

为了在 SCSS 加载令人敬畏的字体图标，您需要遵循以下步骤:

*   **安装 font-awesome 入门套件:**前往 Font-Awesome 网站，下载免费的 web 入门套件。
*   **Create a project in your directory:** In your project directory create 2 folders:
    *   公众的
    *   资源

    **公共**文件夹将包含您的 html 和 css 文件，而**资源**文件夹包含您的 scss 文件。

*   **在终端中运行 npm init:**通过运行 npm init 命令来初始化 NPM，创建一个 package.json 文件。

    ```
    npm init
    ```

*   **安装节点-sass:** 运行 npm init 命令后，安装一个名为“节点-sass”的库。这个命令将把 SCS 编译成 css。
    **注意:** Node-sass 需要作为开发依赖项安装。

    ```
    npm install node-sass --save-dev
    ```

*   **在资源内部创建一个文件夹:**在资源文件夹中创建一个名为 assets 的文件夹。解压缩下载的 font-awesome 初学者工具包，复制 SCS 文件夹，并粘贴到资产文件夹。
*   **将 webfonts 添加到公共文件夹:**在 css 文件夹内创建 style.css 文件。复制 webfonts 文件夹并将其粘贴到公共文件夹中。
*   **编辑 scss 文件夹中的 _variables.scss 文件:**打开变量文件，通过写入 webfont 文件夹的路径来编辑“$fa-font-path”。

    ```
    // Variables
    // --------------------------

    $fa-font-path:         "../webfonts" !default;

    ```

*   **在 scss 文件夹内创建 style.scss 文件:**在 scss 文件夹内创建 style.scss 文件，导入字体 awesome。

    ```
    @import "fontawesome.scss";
    @import "solid.scss";

    ```

*   **创建 index.html 文件:**在公共目录中创建 index.html 文件，并添加以下代码:

    ```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0">

        <title>Document</title>
        <link rel="stylesheet" href="css/style.css">
    </head>
    <body>
        <i class="fas fa-thumbs-up"></i>
    </body>
    </html>
    ```

*   **Edit the scripts field in package.json file:**

    ```
    "scripts": {
        "compile:sass": "node-sass resources/assets/scss/style.scss public/css/style.css -w"
      }

    ```

    该命令将把 SCS 转换成 css 文件，同时跟踪更改。

*   **编译你的代码:**打开终端，使用以下命令:

    ```
    npm run compile:sass
    ```

**注意:**编译后如果在 style.css 文件中遇到以下错误，请注释/删除“-ms-filter”行。