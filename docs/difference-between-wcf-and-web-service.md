# WCF 和网络服务的区别

> 原文:[https://www . geeksforgeeks . org/wcf 与 web 服务的区别/](https://www.geeksforgeeks.org/difference-between-wcf-and-web-service/)

**WCF(Windows Communication Foundation):**WCF，顾名思义，就是统一的。用于开发面向服务的应用程序。它允许您开发可以使用不同通信机制进行通信的应用程序。它是为其他微软分布式技术创建的，被认为是分布式计算的未来。由于其灵活性，它使端点的开发变得更加容易。它支持各种编程语言和平台。它基于 SOAP，并以 XML 形式返回数据。它可以托管在不同的场景中，这些场景包括各种服务，如 WAS、IIS、托管 Windows 等。以下代码将用于在 WCF 建立服务:

```
[ServiceContract]  
public interface ITest  
{    
 [OperationContract]    
 string ShowMessage(string strMsg);  
}  
public class Service: ITest  
{    
 public string ShowMessage(string strMsg)    
```

**网络服务:**网络服务，顾名思义，是一个客户端-服务器应用程序，允许客户端和服务器应用程序之间的通信。它基本上是一个专门为执行某一组任务而设计的软件模块。该服务专门用于使应用平台和技术独立。有两种类型的网络服务，包括 SOAP 网络服务和 RESTful 网络服务。以下代码将用于在 Web 服务中构建服务:

```
[WebService]  
public class Service: System.Web.Services.WebService  
{  
 [WebMethod]  
 public string Test(string strMsg)    
    {    return strMsg; 
    }  
}  
```

#### **WCF vs 网络服务**

<figure class="table">

| 

***【WCF】***

 | 

***Web Service***

 |
| --- | --- |
| It is used to send data asynchronous messages from one service endpoint to another. | Used to exchange data between applications or systems. |
| The protocols used by this channel include HTTP, TCP and MSMQ, named Pipers. | The protocols used in the channel include HTTP and JMS. |
| It aims to provide a manageable method for creating network services and network service clients. | It is designed to perform or execute a certain group of tasks. |
| It provides a runtime environment for services, allowing you to expose CLR types as services and use other services as CLR types. | Service-oriented allows you to expose the functions of existing code through the network so that other applications can use the functions of your program. |
| Its features include service-oriented, reliable and queued messages, multiple transmission, encoding and interoperability supporting multiple message modes, etc. | Its features include loose coupling, support for document exchange, support for RCF (remote procedure call), synchronization or asynchrony, language independence and interoperability, etc. |
| It is more flexible because this service can be hosted in different types of applications. | Poor flexibility, because it can only be accessed through HTTP. |
| Such services can be hosted on IIS, WAS and Windows services. | Such a service can only be hosted on the IIS server. |
| 它使用数据合同序列化程序. | 它使用 XmlSerializer . |
| Its extension is ". svc”。 | Its extension is ". asmx”。 |
| Compared with web services, it is more reliable, fast and robust, so it is considered to be beneficial to the development of real-time applications. | Compared with WCF, it is unreliable and slow. |
| Support duplex operation and multithreading. | Duplex operation and multithreading are not supported. |
| It also supports robust security, trustworthy messaging and transaction processing. | Only security services are supported. |

</figure>