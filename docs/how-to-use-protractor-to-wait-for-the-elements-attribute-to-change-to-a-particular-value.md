# 如何使用量角器等待元素的属性变为特定值？

> 原文:[https://www . geeksforgeeks . org/如何使用量角器-等待元素-属性-更改为特定值/](https://www.geeksforgeeks.org/how-to-use-protractor-to-wait-for-the-elements-attribute-to-change-to-a-particular-value/)

**简介**:量角器是为 AngularJS 应用开发的端到端测试框架，不过，它也适用于非 Angular JS 应用。它像一个真正的用户一样，在一个真正的浏览器中运行与它交互的应用程序。在本文中，我们将使用量角器来检查如何等待元素的属性更改为特定的值？

**先决条件:** [量角器](https://www.geeksforgeeks.org/angularjs-end-to-end-e2e-testing-protractor-installation-and-setup/)的安装和设置

**方法:**我们将创建一个基本的测试程序，在其中我们将检查如何等待元素的属性更改为特定的值？所有量角器测试都将有一个包含配置的文件，这将是启动测试的初始文件。

下面是上述方法的逐步实现。

**第一步:**我们首先要创建一个 conf.js 文件，该文件由将要与量角器一起使用的配置组成。

## java 描述语言

```html
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

**步骤 2:** 我们将创建名为 test.html 的 HTML 文件，该文件将创建一个新的选项卡。

## java 描述语言

```html
<!DOCTYPE html>
<html>

<body>
    <input type="text" id="text" name="name" 
        placeholder="Enter your Name" required>

    <script>
        setTimeout(() => {
            document.getElementsByName('name')[0]
                .placeholder = 'Test text change';
        }, 5000)
    </script>
</body>

</html>
```

**第三步:**我们将创建 test.js 文件。在这个文件中，我们将访问上面的 HTML 文件，然后等待元素的属性更改为特定的值。浏览器是一个由量角器创建的全局变量，用于浏览器级命令，如使用 browser.get()方法导航。description 和 it 语法来自 Jasmine 框架，其中 description 是对测试的描述，而它定义了测试的步骤。

## java 描述语言

```html
describe('Protractor Demo App', function () {
    it("should wait for attribute's value to change to a particular value",
         async function () {

        var EC = protractor.ExpectedConditions;
        // Disable waiting for Angular render update
        await browser.waitForAngularEnabled(false)

        // Get the HTML file that has to be tested
        await browser.get('test.html');

        // Get the test Element
        var testElement = element(by.id('text'));

        // Waits for the attribute's value to change
        // to a particular value
        await browser.wait(async function() {
            return await testElement.getAttribute('placeholder') ===
            'Test text change';}, 10000, 'Takes time to load');
    });
});
```

**步骤 4:** 最后，我们将使用下面给出的命令运行配置文件。这将运行配置文件，测试将如下所示运行。

```html
protractor conf.js
```

**输出:**

![](img/945edc12eaa3a842de918a1965321fb0.png)