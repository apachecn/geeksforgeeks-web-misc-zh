# 如何在 Rails 应用中实现 PostgreSQL 数据库？

> 原文:[https://www . geeksforgeeks . org/how-implement-PostgreSQL-database-in-rails-application/](https://www.geeksforgeeks.org/how-to-implement-postgresql-database-in-rails-application/)

在本文中，我们将研究 PostgreSQL 在 rails 应用程序中的实现。众所周知，数据库是任何网络应用程序中非常重要的一部分，这就是为什么今天像 Flipkart、Amazon、网飞这样的现代网络应用程序所有的网站都使用数据库。

在继续之前，我们需要稍微了解一下什么是数据库，以及什么是 PostgreSQL 数据库。

**数据库:**就像是用来管理数据的软件。像插入新数据、删除现有数据、更新现有数据等等。数据库有关系数据库和非关系数据库两种类型。

**PostgreSQL:** PostgreSQL 是一个关系数据库，其中数据库数据以表格格式存储，即行和列的方式。PostgreSQL，也称为 Postgres，是一个免费的开源关系数据库管理系统。

### 先决条件:

*   [安装 PostgreSQL](https://www.geeksforgeeks.org/install-postgresql-on-windows/)
*   [安装红宝石](https://www.geeksforgeeks.org/how-to-install-ruby-on-windows/)
*   [安装导轨](https://www.geeksforgeeks.org/how-to-install-ruby-on-rails-on-windows-and-linux/)

### 实施:

安装所有必备项目后，您必须创建新的 rails 应用程序。为此，请使用以下命令:

```
$ rails new my_postgresql_app
$ cd my_postgresql_app
```

现在你必须打开 **my_postgresql_app** 项目任意 IDE 并移动 **config/database.yml** ，你会看到默认情况下 rails 应用程序支持 **sqlite3** 数据库，但是 rails 也支持不同类型的数据库，比如 postgresql、MySQL 等。

因此，要在 rails 应用程序中添加 PostgreSQL 数据库，我们必须在我们的项目 ***中添加 **pg gem** 文件，并从 *gemfile* 中删除**gem“SQLite 3”、“~>1.4”**。***

```
***gem 'pg'***
```

在 *gemfile* 中添加 pg gem 后，在终端上运行给定的命令。

```
$ bundle install
```

此命令安装实现 PostgreSQL 数据库所需的所有文件。

接下来，我们必须移动到 ***config/database.yml 文件*** ，从该文件中删除所有现有数据，并添加新数据以连接到 PostgreSQL。

```
development:
  adapter: postgresql
  encoding: unicode
  database: database_name_development
  pool: 5
  host: localhost
  username: postgres_user_name
  password: postgres_password

test:
  adapter: postgresql
  encoding: unicode
  database: database_name_test
  pool: 5
  username: postgres_user_name
  password: postgres_password

staging:
  url: <%= ENV['DATABASE_URL'] %>

production:
  url: <%= ENV['DATABASE_URL'] %> 
```

在 *config/database.yml 文件*中添加数据后，您必须运行给定的命令。

```
$ rails db:create
```

现在，您已经成功地将 rails 应用程序与 PostgreSQL 数据库连接起来了。