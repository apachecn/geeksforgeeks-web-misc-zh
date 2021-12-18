# 通过 Azure 服务总线发送消息|发送消息和安排消息

> 原文:[https://www . geesforgeks . org/messaging-via-azure-service-bus-send message-and-schedule message/](https://www.geeksforgeeks.org/messaging-via-azure-service-bus-sendmessage-and-schedulemessage/)

在本节中，我们将简要讨论通过服务总线池跨 Azure 主题传输数据的数据传输方法。我们既可以发送普通消息，也可以发送基于时间表的消息。我们将逐一介绍这两种基本类型的消息传递。

**Azure 服务总线:** Microsoft Azure 服务总线是一种完全托管的云上企业集成消息服务，用于将云中运行的任何应用程序、设备和服务连接到任何其他应用程序或服务。该平台充当云上和任何设备上应用程序的消息传递主干。

**它是如何工作的？**使用消息在不同的应用程序和服务之间传输数据。消息是二进制格式的，可以包含 JSON、XML 或仅包含文本。这些消息被放在应用程序所连接的服务总线上，这样，所有或特定的用户通过这个应用程序，通过开放的套接字服务连接，可以接收通过服务总线传输的数据。

**消息类型:**通过 Azure 服务总线传输的数据消息可以分为两种主要类型，数据是需要按照特定的时间表发送，还是需要立即发送。这里我们将详细讨论这两个消息传递过程。每一个都有自己特定的方法来调用消息传递过程。

*   **Send Message Immediate:** The send() function call sends a message to the Azure Service Bus to which the current sender is connected to. This method makes a non-asynchronous call. You also have an asynchronous version to improve performance.

    **原型:**

    ```html
    send( IMessage message )
    ```

    **样本代码:**

    ```html
    public static async sendMessage(content: Message): Promise<string> {

        const serviceConnection = AzureServiceBus.createConnection();

        const client = serviceConnection.createQueueClient(""
                        + process.env.AZURE_SERVICEBUS_QUEUE);

        const sender = client.createSender();
        let response = "";

        try {
            const scheduledEnqueueTimeUtc 
                = moment().utc().add(1, "m").toDate();

            await sender.send( {body: JSON.stringify(content),
                            label: "MyTopic"});

            await client.close();
        } catch (error) {

        } finally {
            await serviceConnection.close();
        }

        return resp;
    }
    ```

*   **Schedule Message:** This method sends a timer-based message to the Azure Service Bus the invoking sender is connected with. It enqueues the message into the bus to scheduled time message, the message is delivered to the receiver end. This is currently asynchronous process for better performance.

    **原型:**

    ```html
    scheduleMessage( IMessage message, Instant scheduledEnqueueTimeUtc )
    ```

    **样本代码:**

    ```html
    public static async sendScheduleMessage(
            content: Message): Promise<string> {

        const serviceConnection = 
                AzureServiceBus.createConnection();

        const client = serviceConnection.createQueueClient(
                "" + process.env.AZURE_SERVICEBUS_QUEUE);

        const sender = client.createSender();
        let response = "";

        try {
            const scheduledEnqueueTimeUtc 
                = moment().utc().add(1, "m").toDate();

            const sequenceId = await sender.scheduleMessage(
                scheduledEnqueueTimeUtc,
                {body: JSON.stringify(content),
                label: "MyTopic"});

            response = sequenceId.toString();
            await client.close();
        } catch (error) {

        } finally {
            await serviceConnection.close();
        }

        return resp;
    }
    ```

    这将引发一个问题，即 sequenceId 值将变为“未定义”。Azure 门户提供了一个修复，即消息需要被编码，然后放入服务总线，以便获得正确的 sequenceId。

**Bug 修复:**

```html
import { DefaultDataTransformer }
            from "@azure/amqp-common";
...
...

const dt = new DefaultDataTransformer();

const sequenceId = await sender.scheduleMessage(
        scheduledEnqueueTimeUtc,
        {body: dt.encode(JSON.stringify(content)),
        label: "MyTopic"});

response = sequenceId.toString();
```

现在，您将收到正确的 sequenceId，如果将来需要，您可以使用下面的代码段来取消消息。

**取消消息:**该方法使用 scheduleMessage 调用提前删除了放置在服务总线中的消息。我们需要将调用期间返回的 sequenceNumber 作为该方法调用的唯一参数发送。如果消息已经被传递，那么我们会收到一个需要在 catch 中处理的错误消息 NotFound。

**原型:**

```html
cancelScheduledMessage( long sequenceNumber )
```

因此，我们已经介绍了如何通过使用上述两种方法来传递数据，并通过计划方式或非计划方式来放置数据请求。