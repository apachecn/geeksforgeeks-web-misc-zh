# 免费在 Firebase 上托管 Flutter 网站

> 原文:[https://www . geeksforgeeks . org/hosting-flutter-web . on-firebase-for-free/](https://www.geeksforgeeks.org/hosting-flutter-website-on-firebase-for-free/)

Flutter 是一个用户界面开发软件开发工具包。Flutter 是谷歌维护的一个开源项目。它使软件开发人员能够用单一代码库为 IOS、Android、Web 和 Desktop 制作漂亮的本机编译应用程序。虽然开发 flutter 应用程序非常有趣，但向最终用户展示产品也很重要。最好的方法之一是在 firebase 主机上托管 flutter web 应用程序。

Firebase 也是一款护目镜产品，作为后端和服务提供给开发者。它主要用于开发和维护软件应用程序的后端。Firebase 提供多种服务，如实时数据库和 ML 工具包等，以帮助开发人员专注于应用程序的功能，而不是努力实现它。因此，这里我们将使用 firebase 宿主来托管我们的 flutter 应用程序。最重要的是，开始使用 firebase 不涉及任何费用。

### 先决条件:

*   将要主持的颤振项目。在这里，我们将主持一个互动故事应用。
*   Gmail 账户。
*   安装在计算机上的节点 JS。它将使我们能够安装 firebase CLI(命令行界面)。

现在，请按照以下步骤在 Firebase 上免费托管一个 flutter web 应用程序:

**第一步:在 firebase** 上新建一个项目

第一步是在 firebase 中创建一个项目。如果您还没有注册，请访问 firebase.google.com 并登录控制台。在这里，我们将创建一个新项目，并给它任何我们选择的名称。

<video class="wp-video-shortcode" id="video-534134-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126010246/1.1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201126010246/1.1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126010246/1.1.mp4)</video>

**第二步:创建颤振网络应用**

在这一步中，我们将创建我们已经准备好的 flutter 项目的 web 应用程序。我做了一个互动故事应用，可以根据用户的输入改变故事。为了创建 flutter 项目的 web 应用程序，我们将使用以下命令“ **flutter build web** ”。这将在 web 目录内的构建文件夹中创建一个轻盈流畅的 flutter web 应用程序。您甚至可以通过使用以下命令来检查构建是否有任何问题:

```html
flutter run -d chrome --release
```

<video class="wp-video-shortcode" id="video-534134-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126011642/1.2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201126011642/1.2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126011642/1.2.mp4)</video>

**第三步:注册 App**

在这一步中，我们将在已经创建的 firebase 项目中创建一个 web 实例，注册我们的 web 应用程序，并为 flutter web 应用程序生成一个名称(URL)。

<video class="wp-video-shortcode" id="video-534134-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126012148/1.3.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20201126012148/1.3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126012148/1.3.mp4)</video>

**第四步:添加火基 SKD**

现在我们将在 flutter 应用程序中添加 firebase 系统开发工具包。它帮助 firebase 识别 web 应用程序，跟踪其版本，跟踪其使用情况。这是通过在 index.html 页面的主体中添加两三个脚本来完成的。

<video class="wp-video-shortcode" id="video-534134-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126012151/1.4.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20201126012151/1.4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126012151/1.4.mp4)</video>

**第五步:安装 Firebase CLI**

在这一步中，我们将安装 firebase 命令行界面，让我们与 firebase 交互并使用它的功能。这是通过在终端中运行以下命令来完成的:

```html
npm install -g firebase-tools
```

<video class="wp-video-shortcode" id="video-534134-5" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126012238/1.5.mp4?_=5">[https://media.geeksforgeeks.org/wp-content/uploads/20201126012238/1.5.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126012238/1.5.mp4)</video>

**第六步:部署应用**

这是最后一步，我们将部署我们的 flutter web 应用程序到 firebase 主机。首先，我们需要运行命令**'火基地登录**'来确认我们与火基地连接。然后我们将通过运行命令“ **firebase inti** 来初始化进程。现在我们需要选择几个选项，您可以在下面的视频中看到。所有初始化步骤完成后，我们将命令‘**火基地部署**,或者是在火基地网站上给出的命令。这个命令将把所有的文件推送到托管服务器，它将返回给我们一个网址到我们已经成功托管的网络应用程序。在这种情况下，这是 https://gfg-flutter-story.web.app/,，如果你愿意，你可以看看这个。

<video class="wp-video-shortcode" id="video-534134-6" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126013728/acp.mp4?_=6">[https://media.geeksforgeeks.org/wp-content/uploads/20201126013728/acp.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126013728/acp.mp4)</video>

**完整视频，包含所有** **步骤。**

<video class="wp-video-shortcode" id="video-534134-7" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201126012854/videoplayback.mp4?_=7">[https://media.geeksforgeeks.org/wp-content/uploads/20201126012854/videoplayback.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201126012854/videoplayback.mp4)</video>