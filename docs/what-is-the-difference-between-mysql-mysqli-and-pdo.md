# 【MySQL、MySQL 和 PDO 有什么区别？

> 原文:[https://www . geesforgeks . org/MySQL-MySQL-和-pdo 之间的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-mysql-mysqli-and-pdo/)

为了理解 MySQL、MySQL 和 PDO 之间的区别，我们必须分别了解它们。
这些不过是用来访问 MySQL 数据库和表的 PHP 的 API。开发人员可以为他们的项目选择其中的任何一个，但是，必须知道 MySQLi 不能与 PHP 7 及其更新版本一起使用。但是，开发人员可以将 MySQLi 与 PHP 5 一起使用，这种方式现在已经被弃用了。

让我们了解更多关于它们的信息:

*   **MySQL:** 这是主要的扩展，旨在帮助 PHP 应用程序从 MySQL 数据库发送和接收数据。然而，从 PHP 7 及其更新版本开始，MySQL 的使用已经被弃用和删除。这就是为什么不建议在新项目中使用它，这也是为什么 MySQLi 和 PDO 扩展现在被更多使用的原因。
*   **MySQL:**MySQL 中的‘I’代表改良。因此，这也被称为 MySQL 的改进版本。它有许多新特性，将在本文后面介绍。
*   **PDO–PHP 数据对象:**使用 PDO 的主要优势在于它支持并提供了访问 11 个不同数据库的统一方法。

PDO 支持的数据库有:

*   库弗德
*   微软 SQL 服务器
*   火鸟/Interbase
*   国际商用机器公司
*   Informix
*   关系型数据库

*   神谕
*   ODBC 和 DB2
*   一种数据库系统
*   SQLite
*   4D

但是，PDO 不允许使用 MySQL 服务器当前版本中的所有可用功能。例如，PDO 不允许支持 MySQL 的多语句。

**对比 MySQL、MySQL 和 PDO:**

*   与数据库的连接
*   错误处理
*   数据提取
*   应用编程接口支持
*   安全

**与数据库的连接:**

*   **MySQL:** 连接数据库的 MySQL 代码是:

    ```
    <?php

    // Add the hostname, username and password of the database
    $connection_link = mysql_connect("host", "username", "password");

    // Select query for the database
    mysql_select_db("database_name", $connection_link);

    // Set the charset, UTF-8 to be used for projects
    mysql_set_charset('UTF-8', $connection_link);

    ?>
    ```

*   **MySQL:**以 MySQL 为例，只有一行代码。用户使用数据库的用户名、密码和名称实例化一个 MySQLi 实例。

    ```
    <?php

    // Database credentials
    $mysqli_db = new mysqli('host', 'username', 'password', 'database_name');

    ?>
    ```

*   **PDO:** In case of PDO, a new PDO object must be created.

    ```
    <?php

    // Credentials required for connection
    $pdo = new PDO('mysql:host=host; dbname=database_name; charset=utf8',
                'username', 'password'); 

    ?>
    ```

    使用 PDO 的一个很大的优点是，它使得将项目切换到另一个数据库变得更简单。因此，唯一要做的就是更改连接字符串和新数据库不支持的那些查询。

**错误处理:**错误处理是对应用程序、编程或通信错误的检测和解决。错误处理有助于保持程序执行的正常流程，因为程序中的错误被优雅地处理，从而使程序运行良好。

*   **MySQL:**

    ```
    <?php

    $my_result = mysql_query("SELECT * FROM table", $connection_link)
            or die(mysql_error($connection_link));
    ?>
    ```

    “die”方法用于 MySQL 中的错误处理，但它被认为不是一种很好的错误处理方法。这是因为 die 突然结束脚本，然后向屏幕显示错误。这会使数据库容易受到黑客攻击。

*   **MySQL:**MySQL 中的错误处理如果简单一点。MySQL::$ error(MySQL _ error)返回最后一个错误的字符串描述。

    ```
    <?php

    if (!$mysqli->query("SET a=1")) {
        printf("Errormessage: %s\n", $mysqli->error);
    }

    ?>
    ```

*   **PDO:** PDO has the best error handling method out of these three. This is because of the availability of the try-catch block. Also, there are some error modes that can be used for error handling.
    *   **PDO::ERRMODE_SILENT:** 用于检查每个结果，然后检查$db- > errorInfo()获取错误详细信息。
    *   **PDO::ERRMODE_WARNING:** 警告不会停止脚本。这提供了运行时警告，而不是致命错误。
    *   **PDO::ERRMODE_EXCEPTION:** 它抛出异常，显示 PDO 引发的错误。它不应该在您的代码中抛出 PDOException。当它没有被捕获时，它的行为很像 or die(mysql_error())。但是它可以捕捉这些 PDOException，并按照我们的意愿进行处理。

    我们可以如下设置这些错误模式:

    ```
    <?php
    $db->setAttribute( PDO::ATTR_ERRMODE, PDO::ERRMODE_SILENT );
    $db->setAttribute( PDO::ATTR_ERRMODE, PDO::ERRMODE_WARNING );
    $db->setAttribute( PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION );
    ?>
    ```

    现在，可以按如下方式添加 try/catch 方法:

    ```
    <?php

    try {

        // Incorrect query
        $db->query('hello');
    }

    catch (PDOException $ex) {

        // $ex->getMessage();

         // Message to be displayed in
         // case of such an error
        echo "An Error has occurred";
    }

    ?>
    ```

    使用 try/catch 方法的一个优点是，我们可以设置一个正常的错误消息显示给用户，而不是异常消息，因为这对于一般用户来说可能很难理解。

**取数:**

*   **MySQL:** 一般的编程循环，如 for，或 while 循环可以用于这种目的。假设数据库中有一个名为“data”的表，我们希望从该表的每一行输出用户名。While 循环可以用下面的方式来做这个工作。

    ```
    <?php

    $my_result = mysql_query('SELECT * from data')
            or die(mysql_error());

    $num_rows = mysql_num_rows($my_result);

    while($row = mysql_fetch_assoc($my_result)) {
        echo $row['field1'];
    }

    ?>
    ```

*   **MySQL:**MySQL 也为此使用了一个循环。然而，代码会有点不同。

    ```
    <?php

    while($row = $my_result->fetch_assoc()) {
        echo $row['username'] . '\n';
    }

    ?>
    ```

*   **PDO:** PDO has many in-built statements that help in such cases.
    *   **PDOStatement::fetchAll():**它以数组的形式返回结果，包含所有的结果行。
    *   **PDOStatement::fetchColumn():**它从结果集的下一行获取一列。
    *   **PDOStatement::fetchObject():**这首先获取下一行，然后将其作为对象返回。
    *   **PDOStatement::setFetchMode():**它设置语句的默认提取模式。

    该查询还用于获取数据，因为它返回一个 PDOStatement 对象，该对象可用于通过使用 foreach 和 for 循环直接获取数据。

    ```
    <?php

    // Select query
    $stmt = $db->query('SELECT * FROM `data_table`');

    // fetchAll is used
    $my_results = $stmt->fetchAll(PDO::FETCH_ASSOC); 
    ?>
    ```

**API 支持:**说到 API 支持，PDO 提供了一种面向对象的方法。MySQL 提供了一种过程化的方式，与 MySQL 非常相似。这就是为什么来自 MySQL 背景的开发人员更喜欢使用 MySQL 的原因。然而，面向对象的程序员更喜欢 PDO，因为它与大量数据库兼容。
因此，面向对象的程序员更喜欢 PDO，而程序程序员更喜欢 MySQL 和 MySQL。

**安全性:**数据库安全性用于保护数据库及其包含的信息免受黑客及其攻击。黑客通常使用 SQL 注入来破坏数据库。因此，必须确保注射的安全性。

PDO 和 MySQLi 都提供了 SQL 注入安全性。

假设一名黑客试图使用 POST 方法通过“名字”HTTP 查询参数注入一个 SQL 注入:

```
$_POST['firstname'] = "'; DELETE FROM users; /*"
```

如果注入溢出，它将“原样”添加到查询中。因此，它将删除用户表中的所有行。

在 PDO，人工逃生是为了增加安全性。

```
$name = PDO::quote($_POST['name']);
$pdo->query("SELECT * FROM users WHERE name = $name");
```

PDO::quote()和 mysqli _ real _ escape _ string()之间的区别在于，前者会转义字符串和引号，而后者只会转义字符串，并且必须手动添加引号。