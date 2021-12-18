# 开发中有哪些环境变量？

> 原文:[https://www . geesforgeks . org/什么是开发中的环境变量/](https://www.geeksforgeeks.org/what-are-environment-variables-in-development/)

**环境变量是一个广泛使用的术语，但它实际上意味着什么，甚至为什么会存在？**

**技术定义:**环境变量是一个动态设置的值，在整个程序中使用，并决定每个设备上程序的属性。它们是程序执行环境的一部分。
例如，一个程序可以从环境变量中获取特定键的值，比如 Proxy，如果代理变量存在，它可以在发出网络请求时通过代理隧道。

环境变量的好处是–

*   安全
*   易于维护和自适应代码

让我们借助另一个例子来理解它。想象一下，你得到了一个像付费天气 API 服务一样的付费服务，并得到了一个用于身份验证的秘密令牌，它包含在你的天气项目中。

例如，JavaScript 中的环境变量可以是这样的:

```html
const weather_api_key = "YourVeryUsefulAndSecretToken";
```

现在，你像我们大多数人一样为这个项目建立了一个公共存储库。但是等等，这意味着任何人都可以在他们的项目中使用你的钥匙，而你却要为此付费。**这是个大问题！**

**那么，你应该停止将你的项目保存在公共存储库中吗？**

**不！**您应该始终尝试将您的项目添加到 Github 或类似的 VCS 服务中，以增强您的投资组合。我们只需要一种方法将这个**秘密密钥**从普通代码中分离出来，并在代码中使用。答案是**环境变量。**

**环境变量**是在本地设置或托管服务上设置的一组键值对，而不是直接包含在普通代码中，可以在您的代码中使用，

例如，

<figure class="table">

| 天气关键字 | youverusefulandsecrettoken |
| 数据库关键字 | secretd 数据库密钥 |
| _ email support | abc@xyz.com |

</figure>

我们可以在代码中包含这些键，以便在代码中使用它们各自的值。例如，在 JavaScript 中:

```html
const weather_api_key = process.env.weather_key;
```

其中 weather_key 指的是实际的令牌值，即“yourryusefulandsecrettoken”

编辑并添加。环境或其他带有环境变量的文件。gitignore 文件，这样它就不会被 git 跟踪。现在，您可以将这些代码推送到您的存储库中，而无需担心任何安全问题！

环境变量解决了安全问题，但它还有另一个好处。环境变量确保**自适应代码。**
例如，如果代码在网站上必须显示支持电子邮件的任何地方使用上述名为 *support_email* 的环境变量。后来由于某些原因你想改变它。在这种情况下，您只需要在环境变量配置中更改它。如果它是一个简单的代码，到处修改它将是一个乏味的任务。

根据您的操作系统和托管服务，设置环境变量会有所不同，因此请从特定于服务的文档或指南中获取帮助。环境变量的范围通常在整个操作系统中是全局的，但是也有一些方法可以为您的项目设置特定的环境变量。[查看这篇关于在 Node JS 中设置环境变量的文章。](https://www.geeksforgeeks.org/setting-up-environment-variables-in-node-js-in-a-platform-independent-way/)