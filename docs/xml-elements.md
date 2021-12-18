# XML |元素

> 原文:[https://www.geeksforgeeks.org/xml-elements/](https://www.geeksforgeeks.org/xml-elements/)

XML 元素是 XML 文档的基本构造块。它被用作存储文本元素、属性、媒体对象等的容器。每个 XML 文档至少包含一个元素，该元素的范围由开始和结束标记分隔，或者在元素为空的情况下，它由一个空标记分隔。

**语法:**

```
<element-name attributes> Contents...</element-name>
```

*   **元素-名称:**是元素的名称。
*   **属性:**属性用于定义 XML 元素属性，这些属性之间用空格隔开。它将名称与一个值相关联，该值是一个字符串。

**示例:**

```
name="Geeks"
Here, Geeks represents the value of attribute

```

**定义 XML 元素的规则:**下面给出了一些创建 XML 元素的规则:

*   包含字母数字值或字符元素。但是名称中只需要三个特殊字符，即连字符、下划线和句点。
*   名称区分大小写。意思是小写字母有不同的意思，大写字母有不同的意思。例如，address、Address、aDDress 是不同的名称。
*   元素的开始和结束标记都需要相同。
*   作为容器的元素可以包含文本或元素

**空元素:**XML 文档中不包含内容的元素称为空元素。XML 中空元素的基本语法如下:

```
<elements-name attributename/>
```

**示例 1:** 下面是一个使用 XML 元素描述大学生地址的 XML 文档示例。

```
<?xml version = “1.0”?>
<contactinfo>
    <address category = “college”>
        <name>G4G</name>
        <College>Geeksforgeeks</College>
        <mobile>2345456767</mobile>
    </address>
</contactinfo>
```

**输出:**

```
      G4G
      Geeksforgeeks
      2345456767

```

**例 2:**

```
<?xml version = "1.0"?>
<student>
    <_personal_details = "Personal Details">
        <name>xyz</name>
        <father_name>abc</father_name>
    </personal_details>
    <edu_details = "Educational Details">
        <hsc_perc>80%</hsc_perc>
        <ssc_perc>98%</ssc_perc>
    </edu_details>
</student>
```

**输出:**

```
      xyz 
      abc
      80%
      98%
```