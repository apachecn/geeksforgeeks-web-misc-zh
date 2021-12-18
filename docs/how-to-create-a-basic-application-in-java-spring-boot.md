# 如何在 Java Spring Boot 中创建一个基本应用程序

> 原文:[https://www . geeksforgeeks . org/如何在 java 中创建基本应用程序-spring-boot/](https://www.geeksforgeeks.org/how-to-create-a-basic-application-in-java-spring-boot/)

[Spring MVC](https://www.geeksforgeeks.org/introduction-to-spring-framework/) 是 Spring 广泛使用的模块，用于创建可扩展的[网络应用程序](https://www.geeksforgeeks.org/how-to-choose-a-technology-stack-for-web-application-development/)。但是 spring 项目的主要缺点是配置非常耗时，对于新开发人员来说有点难以承受。如果您是初涉春天的人，让应用程序做好生产准备需要一些时间。解决办法是 [Spring Boot](https://www.geeksforgeeks.org/introduction-to-spring-boot/) 。Spring Boot 建在春天的顶端，包含了春天的所有特征。在本文中，我们将看到如何创建一个基本的 spring boot 应用程序。

**Spring Initializr** 是一个基于 web 的工具，使用它我们可以很容易地生成 Spring Boot 项目的结构。它还为元数据模型中表达的项目提供了各种不同的特性。这个模型允许我们配置 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 支持的依赖列表。在这里，我们将使用 spring 初始化器创建一个应用程序的结构，然后使用一个 [IDE](https://www.geeksforgeeks.org/what-will-be-the-best-java-ides-in-2020/) 来创建一个示例 GET 路径。因此，要做到这一点，需要遵循以下步骤:

1.  转至[弹簧初始化器](https://start.spring.io/)
2.  按照要求填写细节。对于本申请:

    > 项目:Maven
    > 语言:爪哇
    > Spring Boot: 2.2.8
    > 打包:JAR
    > Java: 8
    > 依赖项:春网

3.  单击生成，它将下载初始项目。
    [![](img/d4782728746ced3a1f69ea3b8c61fe8c.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200519020753/spring-io.jpg)
4.  Extract the zip file. Now open a suitable IDE and then go to *File*->*New*->*Project from existing sources*->*Spring-boot-app* and select pom.xml. Click on import changes on prompt and wait for the project to sync.
    [![](img/938bf65050c80f1ce86dbf17ba3d2b23.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200519021758/importproject.jpg)

    **注意:**在 Maven 的导入项目窗口中，确保选择了与创建项目时选择的 JDK 相同的版本。

5.  转到*src*->*main*->*java*->*com . gfg . spring . boot . app*，创建一个名为
    的 Java 类作为 Controller，并添加注释 *@RestController* 。现在创建一个 GET 应用编程接口，如下所示:

```
@RestController
public class Controller {

    // One syntax to implement a
    // GET method
    @GetMapping("/")
    public String home()
    {
        String str
            = "<html><body><font color=\"green\">"
              + "<h1>WELCOME To GeeksForGeeks</h1>"
              + "</font></body></html>";
        return str;
    }

    // Another syntax to implement a
    // GET method
    @RequestMapping(
        method = { RequestMethod.GET },
        value = { "/gfg" })

    public String info()
    {
        String str2
            = "<html><body><font color=\"green\">"
              + "<h2>GeeksForGeeks is a Computer"
              + " Science portal for Geeks. "
              + "This portal has been "
              + "created to provide well written, "
              + "well thought and well explained "
              + "solutions for selected questions."
              + "</h2></font></body></html>";
        return str2;
    }
}
```

9.  This application is now ready to run. Run the *SpringBootAppApplication* class and wait for the Tomcat server to start.

    [![](img/093e5180d109d63d4fd76cdf5ca54c15.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200526012811/gfg_server_running.jpg)

    **注意:**Tomcat 服务器的默认端口是 8080，可以在 *application.properties* 文件中更改。

10.  现在进入浏览器，输入网址 **localhost:8080** 。观察输出，现在对**本地主机:8080/gfg** 执行同样的操作

**输出:**
运行上述应用程序时，会生成以下输出:

<video class="wp-video-shortcode" id="video-414815-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200526135420/output7.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200526135420/output7.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200526135420/output7.mp4)</video>

**结论:**按照上面的步骤，我们创建了一个简单的 [RESTful](https://www.geeksforgeeks.org/rest-api-introduction/) 路线，其中包含一些消息。为了使应用程序更加复杂，添加了更多的 RESTful 路由来执行服务器上的 CRUD 操作。