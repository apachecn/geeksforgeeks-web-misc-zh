# 如何使用 app-UI 插件设计手机页面视图导航？

> 原文:[https://www . geesforgeks . org/how-to-design-page-view-navigation-for-mobiles-use-app-ui-plugin/](https://www.geeksforgeeks.org/how-to-design-page-view-navigation-for-mobiles-using-app-ui-plugin/)

本文的目的是通过使用 **app-UI** 插件为移动设计提供交互式用户界面组件。在这里，我们将研究各种类型的网页导航视图。
该插件帮助移动开发者使用 HTML、CSS 和 JavaScript 创建应用程序。

请从[链接](https://github.com/triceam/app-UI)下载所需的预编译文件，并保存在您的工作文件夹中以供执行。在包含源代码时，请注意正确的文件路径。

**基本示例:**以下演示了使用 **app-UI** 插件的页面视图导航器的基本 HTML 网页结构。

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html>
    <head>
        <meta
            name="viewport"
            content="width=device-width, initial-scale=1,
                     maximum-scale=1, user-scalable=no"/>

        <script src="src/libs/jquery-1.7.1.js"></script>
        <script src=
"src/libs/jquery.animate-enhanced.js">
        </script>
        <!-- library files for view navigator -->
        <link rel="stylesheet"
              href="src/viewnavigator/viewnavigator.css" 
              type="text/css" />
        <script src=
"src/viewnavigator/viewnavigator.js">
        </script>

        <script>

            $(document).ready( function() {

                // Setup the default view
                var defaultView = getView();
                defaultView.backLabel = null;

                // Setup the ViewNavigator
                window.viewNavigator = new ViewNavigator('body');
                window.viewNavigator.pushView( defaultView );

            });
            function pushView() {

                // Create a view and push it onto
                // the view navigator
                var view = getView();
                window.viewNavigator.pushView( view );
            }
            function popView() {

                // pop a view from the view navigator
                window.viewNavigator.popView();
            }

            function getView()
                       {
              // Create a view descriptor with random content
              var bodyView = $('<h3>Basic navigator using app-UI plugin</h3>'
                        + '<div>' + '<hr><li href="#" onclick="pushView()"
                        class="viewNavigator_backButton">
                        push view</li> <li href="#" onclick="popView()"
                        class="viewNavigator_backButton">pop view</li><hr>'
                        + getPageContent() + '</div>');
                var links = bodyView.find('a');

                return { title: "Default View "
                                    + parseInt(Math.random()*1000),
                         backLabel: "Back",
                         view:  bodyView
                };
            }

            function getPageContent() {

                var result = "";
                for ( var i = 0; i < 8; i ++ )
                                {
                  result +=
                       "Python is a high-level, general-purpose
                        and a very popular programming language.
                        Python programming language (latest Python3)
                        is being used in web development,
                        Machine Learning applications, along with
                        all cutting edge technology in the Software
                        Industry.Python Programming Language
                        is very well suited for Beginners,
                        also for experienced programmers with other
                        programming languages like C++ and Java.
                        <hr>"
                }
                return result;
            }
        </script>
    </head>
</html>
```