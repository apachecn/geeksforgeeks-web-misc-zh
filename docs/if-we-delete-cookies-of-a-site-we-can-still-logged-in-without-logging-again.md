# 如果删除一个站点的 cookies，仍然可以登录而不用再次登录

> 原文:[https://www . geesforgeks . org/if-we-delete-cookies-of-site-we-仍然可以登录-无需再次登录/](https://www.geeksforgeeks.org/if-we-delete-cookies-of-a-site-we-can-still-logged-in-without-logging-again/)

facebook 是用 PHP 编码的，PHP 于 1994 年推出。但是在 PHP 中，有一个缺点，即如果我们禁用 cookies(比如在脸书)，脸书服务器会忘记以前登录过的人，它会在应用程序第一次启动时将该页面带到我面前。但是在 Java (JEE 版，1999 年推出)中，我们有一种叫做“网址编码”的技术，即使在禁用 cookies 后，我们仍然可以使用它登录。所以我们将通过编码向你们展示这个。

有两个视频来描述。

*   [视频 1 描述解决方案](https://youtu.be/92wtJx6c51I)
*   [视频 2 描述解决方案](https://youtu.be/7V1nLY3BnR4)

在第一个视频中，我们删除了脸书的 cookies，并尝试再次登录。但是当应用程序第一次启动时，它将我重定向到了那个页面。正如你在视频中看到的，用户名和密码对我来说是可见的。当我们删除 cookies 时，服务器会忘记你是谁，并在应用程序首次启动时将你重定向到该页面。

现在，我们将使用 Java 展示它。这是一个简单的点击计数器程序，我们将从这里讲述 facebook 背后发生的事情。我们还将在这段代码中看到修改。

```
<% @page contentType = "text/html" pageEncoding = "UTF-8" %>
<!DOCTYPE html>
<head>
    <meta http - equiv = "Content-Type"
            content = "text/html; charset=UTF-8">
    <title>Session Counter</title>
</head>

< % int count
    = 0;
HttpSession sess = request.getSession();
System.out.println("session object id is: " + sess.getId());
System.out.println("session object is new: " + sess.isNew());
String name = request.getParameter("btn");
if (name != null) {
    if (sess.getAttribute("countval") != null) {

        if (name.equals("Next")) {
            count = 
            Integer.parseInt((String)sess.getAttribute("countval")) + 1;
        }
        else {
            count = 
            Integer.parseInt((String)sess.getAttribute("countval")) - 1;
        }
    }
}

sess.setAttribute("countval", String.valueOf(count));

// String url="hitcount.jsp;jsessionid=" + sess.getId();
% > 
<h3> Count is : <%= count %></h3>

<form action
    = <%= "hitcount.jsp" %> // name of program is "hitcount"
    <input type = "submit" value = "Next" name = "btn">
    <input type = "submit" value = "Previous" name = "btn">
</form>
```

**注意:**由于这是一个 servlet 的程序，因此我们需要一个应用服务器来运行它。在这里，我们将使用“Apache Tomcat”并将其与 Netbeans 连接起来。

```
Count is: 0  // The output in the chrome browser.

// In apache tomcat log window.
session object id is: 68EE34B33FCE6ACB8C1183A2FA8CCBBF

session object is new: true

```

我们第一次启动应用程序时的输出。

现在，假设我们增加或减少计数器的值，会话对象 id 将保持不变，但它是新用户吗？不，所以它会给我假的。现在让我们看看计数器值递增时的输出。

```
Count is: 1

// Same alpha numeric string as above, because the
// server has identified me with the  help of cookies
session object id is: 68EE34B33FCE6ACB8C1183A2FA8CCBBF  

session object is new: false

```

**注:【facebook 也是如此。它会检查，你是否是新用户。如果“如果会话对象是新的”为真，那么它会将您重定向到登录页面。否则，您的 facebook 页面将会打开，您无需再次登录。**

**现在如果我们删除 hitcounter** (localhost:我的服务器名)的 cookies 会怎么样

**注:**视频包含如何删除 cookies 的分步说明。
现在当我们删除 localhost 的 cookies 并再次运行 hitcounter 程序时。服务器会忘记谁是用户，并在应用程序首次启动时重定向到该页面。
现在看到删除 localhost 的 cookies 时的输出。删除 cookies 后，无论我们按什么键(即递增或递减)，我都会想到“计数为:0”，因为这是应用程序首次启动时的起始页。

```

Count is: 0

session object id is: 7552ECB909E08330A345AF18915EE743

// Since we have delete cookies, the server will forget
// the previous user and will treat it as a new user.
// Therefore session object id is different from above
// and "session is new" giving true.
session object is new: true 

```

**注意:**当我们删除 facebook 的 cookies 时，我们重定向到了第一次启动时的那个页面，并且能够看到用户名和密码。

在第二个视频中，根据我们的实际目标修改代码。即使我们删除了 cookies，我们仍然可以登录，而无需再次登录。

```
<% @page contentType = "text/html" pageEncoding = "UTF-8" %>
<!DOCTYPE html>
<head>
    <meta http - equiv = "Content-Type" 
            content = "text/html; charset=UTF-8">
    <title> Session Counter</title>
</head>

<% int count
    = 0;
HttpSession sess = request.getSession();
System.out.println("session object id is: " + sess.getId());
System.out.println("session object is new: " + sess.isNew());
String name = request.getParameter("btn");

if (name != null) {
    if (sess.getAttribute("countval") != null) {
        if (name.equals("Next")) {
            count = 
            Integer.parseInt((String)sess.getAttribute("countval")) + 1;
        }
        else {
            count = 
            Integer.parseInt((String)sess.getAttribute("countval")) - 1;
        }
    }
}

sess.setAttribute("countval", String.valueOf(count));

// By using "URL Encoding" method
String url = "hitcount.jsp;jsessionid=" + sess.getId();
%> 
<h3> Count is : <%= count %></h3>

<form action = "<%=url%>">
    <input type = "submit" value = "Next" name = "btn">
    <input type = "submit" value = "Previous" name = "btn">
</form>
```

**输出:**

```
Count is: 0

session object id is: 74E551B3F2E36B74C09885DE6F2EFC67
session object is new: true

```

同样，如果我们增加该值，会看到输出

```
Count is: 1

session object id is: 74E551B3F2E36B74C09885DE6F2EFC67
session object is new: false

```

真正的魔法来了。现在，我们将删除 localhost 的 cookies 并增加 count 的值。查看输出

```
Count is: 2

session object id is: 74E551B3F2E36B74C09885DE6F2EFC67
session object is new: false

```

现在，如果我们删除 cookie，服务器会将我标识为“会话对象是新的”，给我一个 false。这是因为现在您的会话 id 正在通过网址传递。这就是为什么它被命名为“网址编码”。现在把它和脸书联系起来。即使您删除了 cookies，您也不需要再次登录，您的脸书页面将会打开。