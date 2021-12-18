# Git

的介绍和安装

> 原文:[https://www . geesforgeks . org/introduction-and-installation-of-git/](https://www.geeksforgeeks.org/introduction-and-installation-of-git/)

**版本控制系统**

版本控制系统跟踪对项目文件所做的任何类型的更改，为什么要进行这些更改，以及对已修复的问题或引入的增强的引用。它允许开发团队管理和跟踪代码随时间的变化。它允许用户切换到文件的先前状态，比较版本，并帮助以更有效的方式识别文件中的问题。

**Git (A 版控制系统)**

Git 是实现版本控制思想的方法之一。是分布式版本控制系统( **DVCS** )

与使用中央服务器存储所有文件并支持团队协作的集中式版本控制系统不同，DVCS 只需借助桌面、命令行上可用的单一软件即可实现。因此，中央服务器的故障不会在 DVCS 造成任何问题。所以很多操作都可以在你离线的时候进行。

**Git 的优势**

*   ***自由开放源码:*** Git 是一个自由开放源码的软件系统，用户和程序员可以用它来编辑、修改或重用软件的源代码。它给了开发人员改进的机会
*   ***【即时备份:*** 数据可以即时检索，因为有多个副本可用。
*   ***高效低要求***
*   ***暂存区:*** 这是一个中间区域，在完成提交之前，可以对提交进行格式化和审查。我们可以管理文件的哪个版本需要哪些更改，并为不同的提交命令转移它们。

**安装 Git**

[窗口 Git](https://git-scm.com/download/win)

[转到 Mac OS X](https://git-scm.com/download/mac)

安装 git 后，我们可以相应地定制它的环境。定制应在任何给定的计算机上完成。Git 自带一个名为 **git config** 的工具，帮助设置配置变量，负责 git 的操作。为了将这些配置值设置为全局，请添加–global 选项，如果省略–global 选项，则您的配置是特定于当前 Git 存储库的。Git 可以将配置变量存储在以下三个不同的文件中:

*   ***/etc/gitconfig*** :是包含系统上每个用户和存储库配置的文件。由于它是系统范围的配置文件，要配置这些值，必须具有管理权限才能进行更改。**–可以使用系统**选项。
*   ***~/。gitconfig*** :该文件包含用户特定的值。**–可以使用全局**选项，并且可以配置系统上的所有存储库。
*   ***配置文件(当前存储库)*** :特定于单个存储库(当前)。**–本地**选项可用于配置。(如果未使用选项，则默认情况下为本地选项)。

**注意:**无论何时使用 Git，都只使用 Git UI 工具(Git bash、Gitk 等)。设置您的身份也很重要，因为 git 在每次提交时都会使用这些信息。

**设置用户名**

```html
$ git config --global user.name "Geek1234"
```

**设置您的电子邮件 id**

```html
$ git config --global user.email geek1234@xyz.in
```

**设置文本编辑器**

默认情况下，git 使用系统的默认编辑器。这可以通过以下方式配置:

```html
$ git config --global core.editor 
"'C:/Program Files/Notepad++/notepad++.exe' -multiInst -nosession" 
```

```html
$ git config --global core.editor vim
```

也可以使用其他编辑器，如 emacs、崇高文本编辑器等。您需要遵循特定的说明来使用它设置编辑器。

**设置合并工具**

默认情况下，Git 不提供用于将冲突更改集成到工作树中的合并工具。我们可以通过启用以下设置来设置默认合并工具。

```html
$ git config --global merge.tool vimdiff 
```

**列出 git 设置**

您可以使用***git config–list***列出您的设置

```html
$ git config --list
```

该命令将产生以下输出:

```html
user.name=Geek1234
user.email=geek1234@xyz.in
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
```