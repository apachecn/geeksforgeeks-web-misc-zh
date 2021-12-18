# 除了 NPM 装是什么意思？

> 原文:[https://www . geeksforgeeks . org/为 npm-install 保存的意义是什么/](https://www.geeksforgeeks.org/what-is-the-meaning-of-save-for-npm-install/)

**[NPM(节点包管理器)](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/)** 是 Node.js 中 JavaScript 运行时环境采用的默认包管理器，它有一个非常常用的命令 **npm install【包名】–save**。但事实是 **npm 安装【包名】**和 **npm 安装【包名】没有区别–在 npm 5.0.0 之后的更高版本中保存**。

在 npm 5.0.0 之前，有必要在包名后添加`--save`，因为它会将安装的包保存到依赖项部分的 package.json 文件中。如果您正在使用最新版本的 npm，请避免不必要的输入，并使用 **npm install [Package Name]** 而不是**NPM install[Package Name]`--save`**默认情况下，它会将已安装的包添加到 package.json 文件中的依赖列表中。

**NPM 有下面列出的几个命令:**

1.  **–save or-s:** When the following command is used with npm install, it will save all your installed core packages to the dependent part of the package.json file. The core dependencies are those packages, without which your application will not give the expected results. But as mentioned earlier, after NPM version 5.0.0, it is an unnecessary feature.

    ```
    npm install --save
    ```

2.  **–Save-prod or-p:** The following command was introduced in the later version of npm, and it will perform the same task as the `--save` command unless there is any other command, such as `-D` or `-O`.

    ```
    npm install --save-prod
    ```

3.  **–save-dev or-d:** Use the `--save-dev` or `-D` command to add the package you installed to the devDependency section of the package.json file. Development dependencies are packages that are only used for development purposes, and they will not affect the results of the application.

    ```
    npm install --save-dev
    ```

4.  **–save-optional or-o:** When using this command, install the packages that will be listed in the optional Dependency section of the package.json file. Optional dependencies are packages that are only used when using a specific function of the application, and these packages are not needed if the function is not used.

    ```
    npm install --save-optional
    ```

5.  **–Do not save:** When this command is used with npm install, it will not allow the installed package to be saved to the dependencies section.

    ```
    npm install --no-save
    ```

**注意:** NPM 提供了两个额外的选项来将依赖项保存到 package.json 文件中。

1.  **–Save-exact or-e:** This is an additional or optional command provided by npm, which will save the exact version of the installed software package configured at development time. It does not download dependencies from npm's default server-wide operator.

    ```
    npm install --save-exact
    ```

2.  **–save-bundle or-b:** When `--save-bundle` or `-B` is used, the following commands are also optional. This will also add the saved dependencies under the bundleDependency list.

    ```
    npm install --save-bundle
    ```