# XML |属性

> 原文:[https://www.geeksforgeeks.org/xml-attributes/](https://www.geeksforgeeks.org/xml-attributes/)

**先决条件:** [XML |基础知识](https://www.geeksforgeeks.org/xml-basics/)
XML 属性是 XML 元素的一部分。在 XML 元素中添加属性可以提供更精确的元素属性，也就是说，它增强了 XML 元素的属性。
**语法:**

```
<element_name attribute1 attribute2 ... > Contents... </element_name>
```

在上面的语法中，element_name 是元素的名称，可以是任何名称。属性 1，属性 2，…是具有唯一属性名的 XML 属性。然后在内容部分，可以写入任何消息，最后，元素名称结束。
下面给出了一些示例来说明上面的语法:
**示例 1:**

## 可扩展标记语言

```
<text category = "message">Hello Geeks</text>
```

在上例中，XML 元素是文本，**类别**是属性名，**消息**是属性值，属性名及其值总是成对出现。使用属性名时不使用任何引号，但属性值使用单引号(')或双引号(" ")。
**例 2:**

## 可扩展标记语言

```
<text category = "message" purpose ="Greet">Hello Geeks</text>
```