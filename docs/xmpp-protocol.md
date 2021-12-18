# XMPP 协议

> 原文:[https://www.geeksforgeeks.org/xmpp-protocol/](https://www.geeksforgeeks.org/xmpp-protocol/)

XMPP 是可扩展消息存在协议的简称。这是一种通过网络传输 XML 元素的协议，以便近乎实时地交换消息和状态信息。该协议主要由即时消息应用程序使用，如 WhatsApp。

让我们深入了解单词 **XMPP** 的每个字符:

*   **X :** 表示可扩展。XMPP 是一个开源项目，可以根据需要进行更改或扩展。
*   **M :** XMPP 是为了实时发送消息而设计的。与其他协议相比，它具有非常高效的推送机制。
*   **P :** 决定你是否在线/离线/忙。它表示状态。
*   **P :** XMPP 是一个协议，也就是允许系统之间进行通信的一套标准。

这些是 XMPP 满足的任何即时通讯工具的基本要求:

1.  与其他用户发送和接收消息。
2.  检查并共享在线状态
3.  管理与其他用户的订阅。
4.  管理联系人列表
5.  阻止与特定用户的通信(接收消息、共享状态等)。

其他 XMPP 功能:

**去中心化–**
XMPP 基于客户端-服务器架构，即客户端不直接通信，而是借助作为中介的服务器进行通信。它是分散的，意味着没有像电子邮件一样集中的 XMPP 服务器，任何人都可以运行自己的 XMPP 服务器。

每个 XMPP 客户端都由 JID 标识。

```html
#JID
 {
   user,
   server,
   resource
}

```

例如，我是一个 whatsApp 用户，通过我的手机号码来识别我，所以

```html
   user = "8767898790"
   server = "whatsapp.com"
   resource = "mobile"

   JID : "8767898790@whatsapp.com/mobile"

```

**资源**用于应用程序支持移动以及桌面或网络应用程序的情况，因此在即时通讯应用程序仅支持单一资源的情况下，它可以是可选的。

**XMPP 实施–**

XMPP 的原始协议是[传输控制协议](https://www.geeksforgeeks.org/computer-network-tcpip-model/)，在长时间的 TCP 连接上使用开放的 XML 流。

在某些情况下，存在受限防火墙，XMPP(端口 5222)被阻塞，因此它不能用于受限防火墙后面的 web 应用程序和用户，为了克服这一点，XMPP 社区还开发了一个 HTTP 传输。
由于客户端使用 HTTP，大多数防火墙允许客户端毫无问题地获取和发布消息。因此，在 XMPP 使用的 TCP 端口被阻塞的情况下，服务器可以监听正常的 HTTP 端口，流量应该会顺利通过。

**参考资料:**
[xmpp . org](https://xmpp.org/rfcs/rfc3921.html)
[xmpp wiki](https://en.wikipedia.org/wiki/XMPP)