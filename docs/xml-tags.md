# XML |标记

> 原文:[https://www.geeksforgeeks.org/xml-tags/](https://www.geeksforgeeks.org/xml-tags/)

XML 标签是 XML 文档的重要特征。它类似于 HTML，但 XML 比 HTML 更灵活。它允许创建新标签(用户定义的标签)。XML 文档的第一个元素叫做根元素。简单的 XML 文档包含开始标记和结束标记。XML 标签区分大小写，即<root>和<root>两个标签是不同的。XML 标签用于定义 XML 文档中元素的范围。
**XML 标签的属性:**XML 标签有很多属性，下面讨论:</root></root> 

*   每一个 XML 文档都必须有一个根标签来封装这个文档。根标签的名称不必是根。根标签的名称可以是任何可能的标签名称。
    **例:**

## 超文本标记语言

```
<root>
    <name>GeeksforGeeks</name>
    <address>
        <sector>142</sector>
        <location>Noida</location>
    </address>
</root>
```

*   XML 文档必须有开始标记，所以第一个开始标记称为根标记。开始标签以< bracket followed by tag name or element name and close with >括号开始。
    **例:**

## 超文本标记语言

```
<Name>GeeksforGeeks
<address>Noida
```

*   由开始标记开始的标记必须以带有正斜杠(结束标记)的相同标记结束，或者换句话说，每个 XML 文档必须以结束标记结束。结束标记以< followed by / and its pair tag name ended with >
    **开头，例如:**

## 超文本标记语言

```
<Name>GeeksforGeeks</Name>
<address>Noida</address>
```