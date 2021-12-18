# Emmet 在 visual studio 中的代码

> 原文:[https://www.geeksforgeeks.org/emmet-in-visual-studio-code/](https://www.geeksforgeeks.org/emmet-in-visual-studio-code/)

**Visual Studio 代码中的 Emmet:**Emmet 是 Visual Studio 代码中的内置功能。你不必为 emmet 支持安装任何扩展。Emmet 通过提供 Emmet 缩写来防止你自己编写整个代码。默认情况下，Emmet 在 html、haml、pug、slim、jsx、xml、xsl、css、scss、sass、less 和手写笔文件中是启用的，在继承了上述任何一种语言(如 handlebars 和 PHP)的语言中也是启用的。

<video class="wp-video-shortcode" id="video-502776-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200810000546/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-10-00-03-21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200810000546/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-10-00-03-21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200810000546/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-10-00-03-21.mp4)</video>

当您开始键入埃米特缩写时，您会看到该缩写以下拉列表的形式显示在建议列表中。如果您键入简短形式(如元素名称)，您将看到展开的预览。

【HTML 的 Emmet:

**1。通过名称创建元素:**在 HTML 中，当您键入 HTML 标记的名称时，您将获得一个建议列表，从建议列表中选择您想要插入的元素。例如，输入 **h1** 点击回车，得到<h1>T6/h1>。您也可以对所有的 HTML 标签这样做。

<video class="wp-video-shortcode" id="video-502776-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200810003330/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-10-00-29-26.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200810003330/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-10-00-29-26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200810003330/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-10-00-29-26.mp4)</video>

**2。通过元素的类名创建元素:**在 HTML 中，如果您想要创建一个具有特定类名的元素，那么首先输入元素的名称和“**”。**'和您想赋予元素的类的名称，然后点击回车。将使用您指定的类名创建元素。

<video class="wp-video-shortcode" id="video-502776-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200813110424/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-02-13.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20200813110424/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-02-13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200813110424/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-02-13.mp4)</video>

**3。通过元素的 id 创建元素:**在 HTML 中，如果您想要创建一个具有特定 id 的元素，那么首先输入元素的名称和“ **#** ”以及您想要给元素的 id，然后点击 enter。将使用您指定的 id 创建元素。

<video class="wp-video-shortcode" id="video-502776-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200813110811/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-04-47.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20200813110811/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-04-47.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200813110811/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-04-47.mp4)</video>

**4。创建多个元素:**如果您想使用 emmet 创建多个元素，请指定元素的名称和“ ***** ”，并指定您想要多少个该类型的元素，然后按回车键。

<video class="wp-video-shortcode" id="video-502776-5" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200813115045/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-09-44.mp4?_=5">[https://media.geeksforgeeks.org/wp-content/uploads/20200813115045/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-09-44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200813115045/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-09-44.mp4)</video>

**5。创建嵌套元素:**可以使用“ **>** 创建嵌套元素，输入外部元素名称，输入“ **>** ”输入内部元素，点击回车，得到想要的输出。

<video class="wp-video-shortcode" id="video-502776-6" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200813111741/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-15-12.mp4?_=6">[https://media.geeksforgeeks.org/wp-content/uploads/20200813111741/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-15-12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200813111741/GeeksForGeeks.html---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-15-12.mp4)</video>

**CSS 中的 Emmet:**在 CSS 中，当你开始打字时，Emmet 开始给你建议可以选择的地方，然后点击回车。在 CSS 中，您可以在建议中获得属性名称和值。

<video class="wp-video-shortcode" id="video-502776-7" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200813112257/GeeksForGeeks.css---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-19-12.mp4?_=7">[https://media.geeksforgeeks.org/wp-content/uploads/20200813112257/GeeksForGeeks.css---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-19-12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200813112257/GeeksForGeeks.css---GeeksForGeeks---Visual-Studio-Code-2020-08-13-11-19-12.mp4)</video>

Emmet 还支持许多其他语言。