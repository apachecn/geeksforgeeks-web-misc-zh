# AWS Lambda 简介

> 原文:[https://www.geeksforgeeks.org/introduction-to-aws-lambda/](https://www.geeksforgeeks.org/introduction-to-aws-lambda/)

**AWS Lambda** 是一个新的计算系统，它提供了多种好处，比如**实时数据处理和定制后端服务。**

有这么多关于 AWS Lambda 的信息，如果没有介绍，很难知道它是什么。

### AWS Lambda

下面是关于这个系统的常见问题的分类介绍，以帮助一个人确定这是否是正确的选择。

1.  **What is AWS Lambda?**

    AWS Lambda 是一个亚马逊[无服务器计算系统](https://medium.com/@pmuens/aws-fundamentals-what-is-lambda-32d17a89dda2)，运行代码并自动管理底层计算资源。它让一个人可以自动运行代码来响应多种类型的事件，比如来自亚马逊 API 网关的 HTTP 请求、亚马逊 DynamoDB 中的表更新以及状态转换。它还使人能够用定制逻辑扩展到其他 AWS 服务，甚至创建自己的后端服务。

    该服务通过在高可用性计算机基础设施上运行代码来工作。然后，它执行该计算资源的所有管理职责，例如:

    *   提供服务器和操作系统的维护，
    *   自动扩展和管理人员的容量供应，
    *   处理安全补丁部署
    *   代码监控
    *   记录

    用户端唯一需要做的工作就是提供代码让它运行。

2.  **How Does AWS Lambda Work?**

    虽然 AWS Lambda 一开始看起来很混乱，但事实并非如此。事实上，这只是一个简单的过程:

    *   首先将代码上传到 AWS Lambda。
    *   从那里，设置代码从其他 AWS 服务、HTTP 端点或移动应用程序触发。AWS Lambda 将仅在代码被触发时运行代码，并且还将仅使用运行代码所需的计算资源。用户只需为使用的计算时间付费。
3.  **AWS Lambda 有哪些优势？**
    AWS Lambda 为用户提供了多种福利。在决定 AWS Lambda 是否是正确的选择时，您应该知道以下 3 个最大的好处:
    *   **不需要用户管理任何服务器。**由于 AWS Lambda 自动运行用户的代码，所以用户不需要管理服务器。只需编写代码并上传到 Lambda。
    *   **它使用户能够轻松扩展。** AWS Lambda 运行代码来响应每个触发器，因此用户的应用程序会自动缩放。代码也在并行进程中运行，每个进程都单独触发，因此伸缩是根据工作负载的大小精确完成的。
    *   **实惠。**有了 AWS Lambda，当代码没有运行时，人们不用支付任何费用。用户只需为每 100 毫秒的代码执行和他的代码被实际触发的次数付费。
4.  **你能用 AWS Lambda 构建什么？**
    AWS Lambda 可以建造各种各样的东西。以下是它的几个用例的快速列表:
    *   数据处理
    *   实时文件处理
    *   数据有效性
    *   过滤
    *   整理
    *   实时流处理
    *   第三方应用编程接口请求
5.  **How Much Does AWS Lambda Cost?**
    As previously mentioned, with AWS Lambda user only pays for what he uses, factoring in the number of requests and duration of the execution of the code. Lambda considers a request to be each time it starts executing in response to a trigger such as an event notification or an [invocation volume](https://dashbird.io/features/aws-lambda-serverless-monitoring/).

    代码的持续时间从代码开始执行的时刻开始计算，直到它返回或终止。

    如果不确定 AWS Lambda 是否是正确的选择，有一个**免费等级选项可以尝试**。该选项包括每月 100 万次免费请求，以及每月 40 万 GB 秒的计算时间。

**参考资料:**
要了解更多关于 AWS Lambda 的信息，请查看亚马逊方便的 [AWS Lambda 常见问题解答](https://aws.amazon.com/lambda/faqs/)