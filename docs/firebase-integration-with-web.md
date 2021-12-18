# Firebase 与 Web 的集成

> 原文:[https://www . geesforgeks . org/firebase-与 web 集成/](https://www.geeksforgeeks.org/firebase-integration-with-web/)

Firebase 是谷歌开发的一个平台，用于创建移动和网络应用程序。我们将看到如何将 firebase 与我们的示例 Web 应用程序集成或连接起来。

**方法:**按照以下步骤将您的网络应用程序与 firebase 集成。

*   First, we will create an HTML page in the index.html file.
*   Once the html page is created, we will create a page named form.js
*   Once the JavaScript of is created, log in to the firebase console and create a new project.
*   Add any name you choose. When finished, go to authentication = > login method.
*   Now click Enable E-mail/Password.
*   After this step, run the HTML file.

下图是上述方法的实施

```htmlhtml
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />

    <script src=
"https://www.gstatic.com/firebasejs/8.2.7/firebase-app.js">
    </script>

    <script src=
"https://www.gstatic.com/firebasejs/8.2.7/firebase-auth.js">
    </script>

    <script src="form.js"></script>
    <title>Login System</title>
</head>

<body>
    <div class="formContainer">
        <h1>Enter Credentials Here:</h1>
        <input type="email" 
            placeholder="email here" id="email" />
        <br />
        <input type="password" 
            placeholder="password here" id="password" />
        <br />
        <button onclick="signUp()" id="signUp">
            SignUp
        </button>
        <button onclick="signIn()" id="signIp">
            SignIn
        </button>
        <button onclick="signOut()" id="signOut">
            SignOut
        </button>
    </div>
</body>

</html>
```