# SOAP 基础知识–简单对象访问协议

> 原文:[https://www . geesforgeks . org/basic of-soap-simple-object-access-protocol/](https://www.geeksforgeeks.org/basics-of-soap-simple-object-access-protocol/)

**简介:**
简单对象访问协议(SOAP)是节点间交换结构化数据的网络协议。它使用 [XML](https://www.geeksforgeeks.org/xml-basics/) 格式来传输消息。它工作在应用层协议之上，如用于符号和传输的 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 和 [SMTP](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) 。SOAP 允许进程在整个平台、语言和操作系统中进行通信，因为像 HTTP 这样的协议已经安装在所有平台上。
SOAP 是由鲍勃·阿特金森、唐·博克斯、戴夫·怀纳和莫森·阿尔-戈塞因于 1998 年在微软公司设计的。SOAP 由万维网联盟的 XML 协议工作组维护，直到 2009 年。

**消息格式:**

*   关于消息结构的信息和处理它的说明。*   应用程序定义的数据类型的编码指令。*   Information about [Remote Procedure Calls](https://www.geeksforgeeks.org/remote-procedure-call-rpc-in-operating-system/) and their responses.

    3.  **信封:**
        它指定 XML 消息是 SOAP 消息。SOAP 消息可以被定义为一个包含封装在信封中的头部和主体的 XML 文档。错误在邮件正文中。
    4.  **表头:**
        此部分不强制。但是当它存在时，它可以提供关于应用程序的关键信息。
    5.  **正文:**
        它包含正在传输的实际消息。错误包含在正文标签中。
    6.  **故障:**
        此部分包含应用程序的状态，也包含应用程序中的错误。此部分也是可选的。它在 SOAP 消息中不应出现多次。

    **示例消息:**

    ```html
    Content-Type: application/soap+xml
    <env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope">
        <env:Header>
            <m:GetLastTradePrice xmlns:m="Some-URI" />
        </env:Header>
        <env:Body>
            <symbol xmlns:p="Some-URI" >DIS</symbol>
        </env:Body>
    </env:Envelope>
    ```

    来源:[https://tools.ietf.org/html/rfc4227](https://tools.ietf.org/html/rfc4227)

    **Advantages of SOAP***   SOAP 是一种轻量级的数据交换协议，因为它基于 XML。*   SOAP 被设计成独立于操作系统和平台的。*   它建立在大多数系统中安装的 HTTP 之上。*   这是由 W3 联盟提出的，它就像一个网络管理机构。*   SOAP 主要用于网络服务和应用程序编程接口。