# 哪个标签用来查找 XML 的版本和语法？

> 原文:[https://www . geesforgeks . org/哪个标签用于查找 xml 和语法的版本/](https://www.geeksforgeeks.org/which-tag-is-used-to-find-the-version-of-xml-and-syntax/)

可扩展标记语言是一种标记语言，它定义了一个规则集，用于以人类可读和机器可读的两种格式对文档进行编码。XML 的设计目标集中在互联网上的简单性、通用性和可用性。XML 被设计成能够自我描述以及存储和传输数据。这是一种文本数据格式，通过 Unicode 为不同的人类语言提供了强大的支持。虽然 XML 的设计侧重于文档，但是该语言被广泛用于表示任意数据结构，例如 web 服务中使用的数据结构。在本文中，我们将了解用于查找 XML 版本及其语法的标签。我们将使用 DOM 来找到 XML 的一个版本。

[DOM(文档对象模型)](https://www.geeksforgeeks.org/dom-document-object-model/)表示一个完整的 HTML 或 XML 文档，作为文档树的根。它有许多属性，如 xmlVersion、编码等。

**XML 版本:**作为 XML 声明的一部分，指定此文档版本号的属性。如果没有声明，并且该文档支持“XML”特性，则该值为“1.0”。

**语法:**

```html
<?xml version="1.0" encoding="UTF-8"?>
```

哪里，

*   这一行表示 XML 序言或 XML 声明。
*   它是一个可选行，即它可以在 XML 文档中使用，也可以不使用。然而，如果使用的话，它应该是第一行。
*   版本=“1.0”是当前使用的 XML 版本。有各种版本的 XML 可供使用。
*   encoding =“UTF-8”指定在编写 XML 文档时使用的字符编码，例如,“是”代表法语等等。它的默认值是“UTF-8”。
*   该声明区分大小写。例如，“xml”应该是小写的。

**示例 1:** 本示例描述了 XML 版本。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
$doc = new DOMDocument;
$doc->loadXML('<?xml version="1.0" encoding="ISO-8859-1"?><from>John</from>');
$version = $doc->xmlVersion; // 1.0
$encoding = $doc->encoding; // ISO-8859-1
echo "Version is:", $version;
echo "\r\n";
echo "encoding is:", $encoding;
?>
```

**输出:**

```html
Version is:1.0
encoding is:ISO-8859-1
```

**示例 2:** 本示例描述了自定义标签，如“至”标签和“自”标签。

## 可扩展标记语言

```html
<?xml version="1.0" encoding="UTF-8"?>
<note>
<to>Students</to>
<from>Teacher</from>
<heading>Reminder</heading>
<body>Meeting with Parent</body>
<text>Progress Discussion</text>
</note>
```

**输出:**

![](img/de30e76f1e4f21dbfbb0815722bd1ca4.png)

**根元素的语法规则:**

每个 XML 文件都应该有一个或多个根元素，以避免出错。例如，下面的代码是错误的，因为它不包含根元素。

## 可扩展标记语言

```html
<to>Students</to>
<from>Teacher</from>
<subject>Regarding assignment submission</subject>
<text>All students will have to submit assignment by tomorrow.</text>
```

可扩展标记语言

**参考:**

*   [https://www.geeksforgeeks.org/xml-basics/](https://www.geeksforgeeks.org/xml-basics/)
*   [https://www.geeksforgeeks.org/xml-syntax/?ref=lbp](https://www.geeksforgeeks.org/xml-syntax/?ref=lbp)
*   [https://www . geesforgeks . org/如何解析和处理-html-xml-using-php/](https://www.geeksforgeeks.org/how-to-parse-and-process-html-xml-using-php/)