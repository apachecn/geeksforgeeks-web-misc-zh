# 使用 Apache 服务器设置 AWS EC2 实例

> 原文:[https://www . geesforgeks . org/AWS-ec2-instance-setup-with-Apache-server/](https://www.geeksforgeeks.org/aws-ec2-instance-setup-with-apache-server/)

**亚马逊网络服务(AWS):**
亚马逊网络服务(AWS)是一个安全的云服务平台，提供计算能力、数据库存储、内容交付和其他功能，帮助企业扩展和增长。了解数百万客户目前如何利用 AWS 云产品和解决方案构建具有更高灵活性、可扩展性和可靠性的复杂应用程序。

首先，我们必须了解云计算及其服务。

**云计算:**
用最简单的话来说，[云计算](https://www.geeksforgeeks.org/cloud-computing/)是指将数据和程序存储和访问到托管在互联网上的远程服务器上，而不是计算机的硬盘或本地服务器上。云计算也被称为基于互联网的计算。
云计算架构:
云计算架构是指云计算所需的组件和子组件。这些组件通常指:

1.  前端(胖客户端、瘦客户端)
2.  后端平台(服务器、存储)
3.  基于云的交付和网络(互联网、内部网、互联网间)。

**AWS 云产品**
亚马逊 Web Services 提供了一系列全球基于云的产品，包括计算、存储、数据库、分析、网络、移动、开发人员工具、管理工具、物联网、安全和企业应用。这些服务有助于组织更快地行动、降低信息技术成本和扩大规模。AWS 受到最大的企业和最热门的初创公司的信任，可为各种工作负载提供动力，包括网络和移动应用程序、游戏开发、数据处理和仓储、存储、归档和许多其他工作负载。

现在，我们将学习如何在亚马逊网络服务(AWS)上创建一个在云上工作的帐户，它将遵循支付你获得的系统，这意味着你为你使用的服务付费，这些服务是存储、服务器等。
以下是创建 AWS 账户的步骤:

**第一步:**先去网站“https://aws.amazon.com/”

![](img/e6e95afb8b9415725fdd80248178c84b.png)

**第二步:**然后去登录，点击创建新账户它会为你创建一个新账户然后填写所有详细信息

![](img/41514708d7e9016dec92415e9955884a.png)

**第三步:**点击继续后，屏幕将显示如下所示，首先您必须填写您的全名，然后是公司名称或大学名称(如果您是学生)，然后填写您的电话号码、国家、您自己的地址、城市、州和您所在地区的邮政编码。单击创建帐户并继续。

![](img/2b4f5f368cb528f09ae64140adb11a3a.png)

**第四步:**之后它会向你要你的 ATM 号码扣 2 个 Rs，扣 2 个 Rs 就可以退了，它会从你的账户上扣 2 个 Rs，检查你开的账户是不是原账户还是假账户。。

![](img/b537fab936ad2522edfe25f0688fe098.png)

**第 5 步:**填写完毕，所有详细信息点击安全提交

![](img/c528c43ab1c611aa0f46fda37a5b48c5.png)

第六步:完成上述所有程序后，创建帐户，但不激活激活帐户，我们应该去电子邮件，有一封邮件从自动气象站激活帐户。

现在如何在云上安装 Apache 网络服务器，或者我们可以简单地说，如何在云上创建一个实例或虚拟机。

现在我们应该知道什么是 Web 服务器了吧？

[](https://www.geeksforgeeks.org/web-servers-work/)**网络服务器基本上是简单的计算机程序，当使用网络客户端请求时，它们会分发网页。运行该程序的机器通常称为服务器，web 服务器和 server 这两个名称几乎可以互换使用。**

**之后，我们有一个问题，什么是 Apache web 服务器？**

**Apache HTTP 服务器，俗称 Apache，是一个免费的开源跨平台网络服务器，超过 60%的公司使用 Apache 网络服务器进行网站托管和维护。**

****第一步:**在 AWS 上创建账户后，我们必须寻找左上角的服务，它会显示亚马逊上的所有服务。**

**![](img/482a7b056f0fc2494d71e9f4d711f320.png)**

****第二步:**之后，我们要去 EC2 (Elastic compute cloud)，这是亚马逊上的一种服务。**

****EC2:** 弹性计算是云服务提供商在需要时随时随地提供灵活计算能力的能力。**

**![](img/3fd783ffc1dbc66f0cbb2922208a48a3.png)**

****步骤 3:** 然后点击启动实例。在这里，我们创建实例意味着我们在云中创建一个虚拟机。**

**![](img/fc99fa9e7e54d6561b6d1e24e3a79e62.png)**

****第四步:**之后在这里选择一个默认选择的亚马逊机器图像(AMI)红帽你必须选择它，因为其他的都是付费服务。**

**现在，我们有了一个称为 AMI 的术语，即亚马逊机器映像是一种特殊类型的虚拟设备，用于在亚马逊弹性计算云中创建虚拟机。**

**![](img/1bbc54a63bcecb35028d71df40e6d98c.png)**

****步骤 5:** 选择实例类型。将其设为默认，因为其他实例类型不是免费的，您必须为此付费，并且实例类型取决于您选择的 AMI。**

**![](img/0cb2b0e6e7f8a6b6a52bafd3686d77e3.png)**

****步骤 6:** 现在配置安全组并添加一些规则**

**1:输入类型:- HTTP，然后 Source = anywhere
2:输入类型:- HTTPS，然后 Source = anywhere**

**这里的源是多余的任何地方，这意味着可以从任何地方访问网络服务器，不需要特定的 IP(互联网协议)或特定的系统，转到审查和启动实例。**

**![](img/d9f0ecc7f73ef4fa07a12595e79da144.png)**

****第 7 步:**点击启动后**

**![](img/3755d733f282268d8464680477ba5ce4.png)**

****第 8 步:**点击启动后，这里有一个键对的选项。选择“创建
新密钥对”并命名密钥对。**

**![](img/31702c81bb8dbb4d3990c1c27609908a.png)**

****步骤 9:** 将密钥对下载到本地系统。下载它，因为当我们必须将本地系统连接到服务器时，这个密钥对告诉我们哪个服务器将连接到我们的本地系统。**

**![](img/bb65040ea7ef244d49f229f21fb9f71e.png)**

****第 10 步:**然后点击启动按钮**

**![](img/e75b44f49664dee1afab90a260f7ebeb.png)**

****步骤 11:** 创建 AS 实例以查看该实例，单击查看实例。它将显示所有实例。**

**![](img/6a10e791657cb3b6804d84c7c83a19cf.png)**

****步骤 12:** 创建一个实例。**

**![](img/2a310de9e642f5fc7ab606116914b1fc.png)**

****步骤 13:** 要删除实例，右键单击该实例并选择终止。
。
![](img/ab59317fb14e195d4b397100f46c1a08.png)**

****第 14 步:**会要求删除实例，点击删除。**

**注意:**

> **不要忘记终止或停止实例，因为它是付费服务，所以他们将根据使用这些服务的时间收费。**