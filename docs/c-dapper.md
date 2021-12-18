# C# | Dapper

> 哎哎哎:# t0]https://www . geeksforgeeks . org/c-dapper/

要理解 Dapper，首先我们需要知道什么是 **ORM** 或者**对象关系映射器。**

**对象关系映射器(ORM) :**
对象关系映射是使用首选编程语言的面向对象范式编写查询的概念。ORM 用于使用我们首选的语言而不是 SQL 与 SQL 数据库进行交互。示例–ASP.NET 实体框架。因此，基本上，ORM 基于数据库查询创建对象。

现在，还有另一种叫做**微 ORM** 的东西，它是一个完整 ORM 的轻量级版本。它不具备完整 ORM 的所有繁重功能，节省了大量工作，但仍能完成数据库和我们首选编程语言之间的映射。 **Dapper** 就是 Micro ORM 的一个例子，其实它之所以被称为**Micro ORM 之王** 是因为它的速度快，工作轻松。

Dapper 的工作方式如下–

*   首先，它创建了一个*idbcconnection*对象，并允许我们编写查询来对数据库执行 CRUD 操作。
*   然后，它通过各种方法之一将查询作为其各种参数之一传递。

**Dapper 的参数:**

1.  ***【SQL】***–要执行的命令。
2.  ***参数***–命令参数(默认值=空)。
3.  ***命令超时*****–命令超时(默认=空)。**
4.  *****命令类型***-命令类型(默认为空)。**

****Dapper 的方法:****

****1。Execute :**
Execute 是从 IDbConnection 类型对象调用的方法，可以一次或多次执行命令，返回数据库表中受影响的行数。它可以执行存储过程、选择/插入/删除语句等。**

****示例:****

## **C#**

```html
string sql = "INSERT INTO Companies (CompanyName) 
                Values (@CompanyName);";

using (var connection = new SqlConnection(
    FiddleHelper.GetConnectionStringSqlServerW3Schools()))
{
    var affectedRows = connection.Execute(sql, 
              new {CompanyName = "GeeksforGeeks"});
}
```

****2。查询:**
查询是从 IDbConnection 类型对象调用的方法，可以执行查询并映射结果。** 

## **C#**

```html
string sql = "SELECT * FROM Companies";

using (var connection = new SqlConnection(
          FiddleHelper.GetConnectionStringSqlServerW3Schools()))
{
    var companies = connection.Execute(sql);
}
```

****3。QueryFirst :**
QueryFirst 是从 IDbConnection 类型对象调用的方法，可以执行查询并映射第一个结果。** 

## **C#**

```html
string sql = "SELECT * FROM Companies WHERE CompanyId = @CompanyId";

using (var connection = new SqlConnection(
     FiddleHelper.GetConnectionStringSqlServerW3Schools()))
{
    var company = connection.QueryFirst(sql, 
                           new {CompanyId = 1});
}
```

****注意:** *QueryFirstOrDefault* 方法是可以执行查询并映射第一个结果的方法，如果序列不包含元素，则为**默认值**。**

****4。query single:**
query single 是从 IDbConnection 类型对象调用的方法，它可以执行查询并映射第一个结果，如果序列中没有恰好一个元素，则会引发异常。** 

## **C#**

```html
string sql = "SELECT * FROM Companies WHERE CompanyId = @CompanyId";

using (var connection = new SqlConnection(
          FiddleHelper.GetConnectionStringSqlServerW3Schools()))
{
    var company = connection.QuerySingle(sql, 
                             new {CompanyId = 1});
}
```

****注意:***query singletordefault*方法是一种可以执行查询并映射第一个结果的方法，如果序列中不包含元素，则为**默认值**，如果序列中有多个元素，则为**抛出异常**。**