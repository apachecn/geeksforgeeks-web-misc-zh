# 发布/重定向/获取(PRG)设计模式

> Original: [https://www.geeksforgeeks.org/post-redirect-get-prg-design-pattern/](https://www.geeksforgeeks.org/post-redirect-get-prg-design-pattern/)

先决条件-[HTTP 协议](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/)，[使用 Python 的 GET 和 POST 请求](https://www.geeksforgeeks.org/get-post-requests-using-python/)

**简介：**

*PRG*是 Web 开发中使用的众多设计模式之一。 用于防止在提交表单后重新加载同一网页而导致表单重新提交。 它消除了内容的冗余以加强搜索引擎优化，并使网站变得用户友好。
它被大型的、值得信赖的在线商店和其他功能强大的网站所使用，这些网站旨在为用户提供友好的服务。

**问题：**

当我们尝试提交 Web 表单时，会向服务器发送一个 HTTP POST 请求。 服务器处理请求并向客户端发送响应代码为 2XX 的响应。 当客户端尝试刷新/重新加载网页时，他/她会无意中向服务器发送另一个 HTTP POST 请求，其中包含与之前相同的数据。 这可能会导致不想要的结果，例如重复的网络购买。

*浏览器重新加载后弹出警告消息框，如下图所示：*

![](img/bdf5ba56ba531c542348be21ae43d225.png)

**内部工作：**

下面是上述问题的内部工作框图。

![](img/f451529acc75af92eedb07a86c3317ec.png)

**解决方案：**

为了避免这个问题，许多 Web 开发人员使用*POST/REDIRECT/GET*模式，而不是直接返回网页，而是根据需要返回到另一个网页或相同网页的重定向。

**内部工作：**

下面是上述解决方案的内部工作框图。

![](img/c13ced73671e56d8a50f202870b31251.png)

**使用 flask 框架演示上述概念的最小 python 和 HTML 代码。**

*   在项目根目录下创建一个名为*app.py*的文件，并将以下代码写入其中。 并使用以下设备安装烧瓶-

    ```html
    $pip install flask

    ```

    ```html
    from flask import Flask, render_template, redirect, request, url_for

    # Initiate flask app
    app = Flask(__name__)

    # Declare routes and methods
    @app.route('/', methods =['GET', 'POST'])
    def home():
        # If it is POST request the redirect
        if request.method =='POST':
            return redirect(url_for('home'))

        return render_template('home.html', title ='Home')

    if __name__=='__main__':
        app.run()
    ```

*   在项目根目录中创建文件夹*Templates*，在 Templates 目录中创建文件*home.html*，并在其中写入以下代码。

    ```html
    <!-- Create a form -->
    <form action="" method="post">
        <!-- Create a input box -->
        <input type="text", value="Suraj Yadav"><br><br>
        <!-- Create a submit button -->
        <input type="submit" value="Submit">
    </form>
    ```

*   **要运行 Web 服务器，请在控制台中键入：**

    ```html
    $python app.py
    Output:
    Running on http://127.0.0.1:5000/

    ```

*   转到 Web 浏览器，键入*localhost：5000*，然后按 Enter 键。

**控制台输出：**
在下图中，第一个 GET 请求是在我们使用 localhost：5000 时发出的，然后我们将数据发布到服务器。 现在，在处理之后，数据服务器通过发出 GET 请求来重定向我们，因此服务器发出第三个 GET 请求，最后在我们尝试刷新页面时发出第四个 GET 请求。

![](img/53e640e73f6f2f6006428765d89a8da8.png)

**注意：尝试在不重定向的情况下处理代码。**