# NPM 剧本简介

> 原文:[https://www.geeksforgeeks.org/introduction-to-npm-scripts/](https://www.geeksforgeeks.org/introduction-to-npm-scripts/)

[**NPM**](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/)**是节点包管理器。它是世界上最大的软件注册中心。该注册表包含超过 800，000 个代码包。许多开源开发者使用 npm 来共享软件。许多组织也使用 npm 来管理私人开发。**

**“npm 脚本”是**文件的脚本字段中的条目。“脚本”字段包含一个对象，您可以在其中指定要公开的各种命令和脚本。这些可以使用以下命令执行-****

```html
**npm run <script-name>**
```

****NPM 脚本被用来自动完成缩小 CSS、丑化 JavaScript、构建项目等任务。NPM 脚本功能多样且简单，通过学习更少的工具，我们可以在网络项目中自动完成任务。****

****例如，这是我们的 package.json 文件。****

```html
**{
  "name": "example",
  "scripts": {
    "test": "echo 'hello world'"
  }
}**
```

****并且可以使用以下命令运行它–****

```html
**npm run test**
```

****当我们有重复的任务并且必须自动化它们时，这非常有用。****

******NPM 脚本内另一个 NPM 脚本:******

```html
**{
  "name": "example",
  "scripts": {
    "start": "npm run lite",
    "lite": "lite-server" 
  }
}**
```

****所以通过使用 npm start，它将运行另一个命令 npm run lite，lite 是 lite-server。所以运行的命令是 npm run lite-server，这将导致节点服务器运行。****

****Web 开发和部署需要大量重复的任务，因此需要自动化这些任务的工具。****

****这里有一些可以自动化的任务。****

******CSS 任务:******

*****   Compile SAS or less into CSS.*   Run Autoprefixer to add the required supplier prefix.*   Zoom out: Delete unnecessary characters (spaces, line breaks, comments) from the source code without affecting the function.*   series****

******JavaScript Tasks:******

*   ****Js hint: Check JavaScript code for errors and potential problems (static code analysis).****
*****   series*   Ugliness: reduce+cartoon (reduce local variables to a single letter).*   Check the errors again.****

******构建项目:******

*****   You can build a project consisting of all file and folder requirements and several dependencies.*   吕惠民、李日华、李日华、李日华、李日华、李日华、李日华、李日华、李日华、李日华、李日华、李日华、李日华、李日华。****

******图像压缩&浏览器同步:******

*****   Compress images using imagemin.*   When using onchange, watch to complete the change, the browser will automatically render it.****