# 如何用 Golang 搭建一个简单的 Web 服务器？

> 原文:[https://www . geesforgeks . org/如何用 golang 构建一个简单的网络服务器/](https://www.geeksforgeeks.org/how-to-build-a-simple-web-server-with-golang/)

[Golang](https://www.geeksforgeeks.org/go-programming-language-introduction/) 是一种过程编程语言，非常适合构建简单、可靠、高效的软件。

### 使用 Golang 创建网络服务器:

### 初始化项目

创建一个包含. go 文件的项目文件夹，例如*服务器. go.*

**目录结构:**

![](img/4a4db344715cc65b2e605401e42a0585.png)

**文件:**

## **去**

```
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {

    // API routes
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello world from GfG")
    })
    http.HandleFunc("/hi", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hi")
    })

    port := ":5000"
    fmt.Println("Server is running on port" + port)

    // Start server on port specified above
    log.Fatal(http.ListenAndServe(port, nil))
}
```

**使用以下命令运行服务器(确保您在项目目录中):**

```
go run server.go
```

****注意:**每当 server.go 文件发生变化时，您必须使用 Ctrl + C 停止服务器，并通过相同的命令重新启动。** 

****控制台:****

**![](img/a781ebd57f70b0de2bce4ea5b07b469f.png)**

**打开所需的 web 浏览器和这些 URL 中的任何一个，以验证服务器是否正在运行:**

```
[http://localhost:5000/](http://localhost:5000/) or [http://localhost:5000/hi](http://localhost:5000/hi)
```

****输出:****

**![](img/0ac9b66905add1e5b143c4684edd507a.png) ![](img/6b8b3fc338827deb487d33128cb3eab4.png)**

### **服务静态文件:**

**用所有静态文件创建一个静态文件夹。
示例目录结构:**

**![](img/17597fbbdbb9222fbb2e5de06169c444.png)**

### **静态文件示例:**

*   **[GfG 标志](https://media.geeksforgeeks.org/wp-content/uploads/20200921155935/gfglogo-300x39.png)**
*   **index.html 文件**

## **超文本标记语言**

```
<html>
  <head>
    <title>Home</title>
  </head>
  <body>
    <h2>Home page</h2>
  </body>
</html>
```

*   **about.html 文件**

## **超文本标记语言**

```
<html>
  <head>
    <title>About</title>
  </head>
  <body>
    <h2>about page!</h2>
  </body>
</html>
```

**现在编辑 ***服务器文件:*****

## **去**

```
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {

    // API routes

    // Serve files from static folder
    http.Handle("/", http.FileServer(http.Dir("./static")))

    // Serve api /hi
    http.HandleFunc("/hi", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hi")
    })

    port := ":5000"
    fmt.Println("Server is running on port" + port)

    // Start server on port specified above
    log.Fatal(http.ListenAndServe(port, nil))

}
```

****验证是否提供静态文件:****

**![](img/c1a744b5e5febbdd78fd8d4cfd713d1c.png) ![](img/19eb5dc3705347dfe9c180adcbb9e82b.png) ![](img/11c6c894c1749af807e085f29ba084f1.png)**