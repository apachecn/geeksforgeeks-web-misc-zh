# 如何用量角器等待一个元素完全淡入？

> 原文:[https://www . geeksforgeeks . org/使用方法-量角器-等待元素完全淡入/](https://www.geeksforgeeks.org/how-to-use-protractor-to-wait-for-an-element-to-completely-fade-in/)

**简介:**量角器是为 AngularJS 应用开发的端到端测试框架。但是，它也适用于非角度 JS 应用程序。它像一个真正的用户一样，在一个真正的浏览器中运行与它交互的应用程序。在本文中，我们将使用量角器来检查一个元素是否已经完全淡入。

先决条件:[量角器的安装和设置](https://www.geeksforgeeks.org/angularjs-end-to-end-e2e-testing-protractor-installation-and-setup/)

**方法:**我们将创建一个基本的测试程序，在其中我们将检查元素是否已经完全淡入。所有量角器测试都将有一个包含配置的文件，这将是启动测试的初始文件。

下面是上述方法的逐步实现。

**第 1 步:**我们必须首先创建一个 **conf.js** 文件，该文件包含与量角器一起使用的配置。

## conf.js(通用报告格式)

```htmlhtml
exports.config = {

  // Define the capabilities to be passed
  // to the webdriver instance
  capabilities: {
    browserName: "chrome",
  },

  // Define the framework to be use
  framework: "jasmine",

  // Define the Spec patterns. This is relative
  // to the current working directory when
  // protractor is called
  specs: ["test.js"],
  SELENIUM_PROMISE_MANAGER: false,

  // Define the options to be used with Jasmine
  jasmineNodeOpts: {
    defaultTimeoutInterval: 30000,
  },

  // Define the baseUrl for the file
  baseUrl: "file://" + __dirname + "/",

  onPrepare: function () {
    browser.resetUrl = "file://";
  },
};
```

**第二步:**我们将创建名为**test.html**的 HTML 文件，该文件将包含要测试的元素。

## test.html

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <title>
        fade-in effect on page load using JavaScript
    </title>

    <script type="text/javascript">
        var opacity = 0;
        var intervalID = 0;
        window.onload = fadeIn;

        function fadeIn() {
            setInterval(show, 200);
        }

        function show() {
            var body = document.getElementById("fade-in");
            opacity = Number(window.getComputedStyle(body)
                .getPropertyValue("opacity"));
            if (opacity < 1) {
                opacity = opacity + 0.1;
                body.style.opacity = opacity
            } else {
                clearInterval(intervalID);
            }
        }
    </script>
</head>

<body>

    <!-- The element to be tested -->
    <div id="fade-in" style="opacity: 0;">
        Inner text
    </div>
</body>

</html>
```

**第三步:**我们将创建 **test.js** 文件。在这个文件中，我们将访问上面的 HTML 文件，然后等待元素完全淡入。浏览器是一个由量角器创建的全局变量，用于浏览器级命令，如使用 browser.get()方法导航。description 及其语法来自 Jasmine 框架，其中 description 是对测试的描述，同时它定义了测试的步骤。

## java 描述语言

```htmlhtml
describe("Protractor Demo App", function () {

    it("should have a title", async function () {

        // Disable waiting for Angular render update
        browser.waitForAngularEnabled(false);

        // Get the HTML file that has to be tested
        browser.get("test.html");

        // Get the fade in element
        let fadeIn = element(by.id("fade-in"));

        // Wait for the fade in process to complete
        await browser.driver.wait(
            async function () {
            return (await element.getCssValue("opacity")) === "1";
            },
            30000,
            "Taking too long to fade in"
        );

        expect(hiddenDiv.isDisplayed()).toBe(true);
    });
  });
```

**步骤 4:** 最后，我们将使用下面给出的命令运行配置文件。这将运行配置文件，测试将如下所示运行。

```htmlhtml
protractor conf.js
```

**输出:**

![](img/945edc12eaa3a842de918a1965321fb0.png)