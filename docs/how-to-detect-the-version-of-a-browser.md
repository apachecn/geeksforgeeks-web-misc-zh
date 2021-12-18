# 如何检测浏览器的版本？

> 原文:[https://www . geesforgeks . org/如何检测浏览器版本/](https://www.geeksforgeeks.org/how-to-detect-the-version-of-a-browser/)

本文介绍了支持 JavaScript 的网络浏览器中浏览器检测的基本理论和技术。

**描述:**即使大部分脚本在支持 JavaScript 的 web 浏览器上工作，但有些东西在某些浏览器上是行不通的，即它们依赖于浏览器，在某些情况下，旧的 web 浏览器不支持某些脚本。
在某些情况下，了解客户的网络浏览器对于恰当地传递某些内容或信息变得非常重要。基本上，它允许您知道客户端网络浏览器的版本和名称，在这里，我们需要为不同的浏览器编写不同的功能，以便进行检测。

**浏览器检测:**主要有两个对象用于浏览器检测，具体如下:

*   navigator.app
*   navigator.appVersion

第一个对象的目的是确定网络浏览器，而第二个对象的目的是确定网络浏览器的版本。

例如，如果浏览器是 Mozilla Firefox，navigator.appName 将返回字符串“Mozilla Firefox”。如果是 Internet Explorer，则 navigator.appName 返回字符串“Microsoft Internet Explorer”。使用这两个对象，我们可以创建一个警告框来显示客户端正在使用的 web 浏览器，并且这个导航器对象包含有关 web 浏览器版本、名称等的所有信息。

**示例:**

## java 描述语言

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <script Language="JavaScript">
        var objappVersion = navigator.appVersion;
        var browserAgent = navigator.userAgent;
        var browserName = navigator.appName;
        var browserVersion = '' + parseFloat(navigator.appVersion);
        var browserMajorVersion = parseInt(navigator.appVersion, 10);
        var Offset, OffsetVersion, ix;

        // For Chrome 
        if ((OffsetVersion = browserAgent.indexOf("Chrome")) != -1) {
            browserName = "Chrome";
            browserVersion = browserAgent.substring(OffsetVersion + 7);
        }

        // For Microsoft internet explorer 
        else if ((OffsetVersion = browserAgent.indexOf("MSIE")) != -1) {
            browserName = "Microsoft Internet Explorer";
            browserVersion = browserAgent.substring(OffsetVersion + 5);
        }

        // For Firefox
        else if ((OffsetVersion = browserAgent.indexOf("Firefox")) != -1) {
            browserName = "Firefox";
        }

        // For Safari
        else if ((OffsetVersion = browserAgent.indexOf("Safari")) != -1) {
            browserName = "Safari";
            browserVersion = browserAgent.substring(OffsetVersion + 7);
            if ((OffsetVersion = browserAgent.indexOf("Version")) != -1)
                browserVersion = browserAgent.substring(OffsetVersion + 8);
        }

        // For other browser "name/version" is at the end of userAgent 
        else if ((Offset = browserAgent.lastIndexOf(' ') + 1) <
            (OffsetVersion = browserAgent.lastIndexOf('/'))) {
            browserName = browserAgent.substring(Offset, OffsetVersion);
            browserVersion = browserAgent.substring(OffsetVersion + 1);
            if (browserName.toLowerCase() == browserName.toUpperCase()) {
                browserName = navigator.appName;
            }
        }

        // Trimming the fullVersion string at 
        // semicolon/space if present 
        if ((ix = browserVersion.indexOf(";")) != -1)
            browserVersion = browserVersion.substring(0, ix);
        if ((ix = browserVersion.indexOf(" ")) != -1)
            browserVersion = browserVersion.substring(0, ix);

        browserMajorVersion = parseInt('' + browserVersion, 10);
        if (isNaN(browserMajorVersion)) {
            browserVersion = '' + parseFloat(navigator.appVersion);
            browserMajorVersion = parseInt(navigator.appVersion, 10);
        }
        document.write(''
            + 'Name of Browser = ' + browserName + '<br>'
            + 'Full version = ' + browserVersion + '<br>'
            + 'Major version = ' + browserMajorVersion + '<br>'
            + 'navigator.appName = ' + navigator.appName + '<br>'
            + 'navigator.userAgent = ' + navigator.userAgent + '<br>'
        );
    </script>
</head>

</html>
```

**输出:**

*   输出下方表示浏览器检测的输出为【Chrome】

    > 浏览器名称=镀铬
    > 完整版= 86.0.4240.183
    > 主要版= 86
    > 导航器. appName =网景
    > 航海家。用户代理= Mozilla/5.0(Windows NT 10.0；win 64x 64)
    > applebwebkit/537.36(KHTML，像壁虎一样)Chrome/86。0 .4240 .183 Safari/537.36

*   下图输出表示“Mozilla Firefox”

    > 浏览器检测的输出浏览器名称=火狐
    > 完整版= 5
    > 主版本= 5
    > 导航器。appName =网景
    > 导航器。用户代理= Mozilla/5.0(Windows NT 10.0；win 64x 64rv:80.0)
    > Gecko/20100101 Firefox/80.0

**结论:**本文从浏览器检测的理论入手，在后面解释了检测的浏览器检测方案和脚本。这在当前环境中非常有益，因为所有浏览器都支持这个应用程序。所以检测/找到浏览器，然后编写相应的代码。