# 阿帕奇 POI 介绍

> 原文:[https://www.geeksforgeeks.org/apache-poi-introduction/](https://www.geeksforgeeks.org/apache-poi-introduction/)

Apache POI 是一个开源的 java 库，用于创建和操作基于 Microsoft Office 的各种文件格式。使用兴趣点，应该能够对以下文件格式执行创建、修改和显示/读取操作。例如，Java 不提供使用 excel 文件的内置支持，所以我们需要为这项工作寻找开源 API。

Apache POI 提供了基于 Office Open XML (OOXML)标准和微软的 OLE2 标准来操作各种文件格式的 Java API。Apache POI 版本可在 Apache 许可证(V2.0)下获得。

**Apache POI 的一些重要特性如下:**

*   Apache POI provides stream-based processing, which is suitable for large files and requires less memory.
*   Archie poi can handle spreadsheets in xls and xlsx formats.
*   Apache POI includes Excel '97(-2007) file format, that is, HSSF implementation of XLS.
*   For Excel 2007 OOXML (. Xlsx) file format.
*   Apache POI HSSF and XSSF API provide mechanisms for reading, writing or modifying excel spreadsheets.
*   Apache POI also provides SXSSF API, which is an extension of XSSF and can handle very large excel worksheets.
*   SXSSF API requires less memory, and is suitable for processing very large spreadsheets, with limited heap memory.
*   There are two models to choose from-event model and user model. Events require less memory, because excel files are read in tokens and need to be processed. The user model is more object-oriented and easy to use.
*   Apache POI provides excellent support for other excel functions, such as using formulas, creating cell styles, fonts, headers and footers, data validation, images, hyperlinks and so on by filling colors and borders.

**阿帕奇 POI 常用组件**

1.  **HSSF(恐怖电子表格格式)**:用于 MS-Excel 文件 xls 格式的读写。
2.  **XSSF (XML 电子表格格式)**:用于 MS-Excel 的 xlsx 文件格式。
3.  **POIFS(不良混淆实现文件系统)**:这个组件是所有其他 POI 元素的基本因素。它用于显式读取不同的文件。
4.  **HWPF(恐怖文字处理器格式)**:用于 MS-Word 文档扩展文件的读写。
5.  **HSLF(恐怖幻灯片版式格式)**:用于阅读、创建和编辑 PowerPoint 演示文稿。

**环境**

Apache POI 运行时依赖关系:如果您正在处理一个 maven 项目，您可以使用下面的代码行集将 POI 依赖关系包含在 pom.xml 文件中。

```html
<dependency> 
    <groupId>org.apache.poi</groupId> 
    <artifactId>poi</artifactId> 
    <version>3.9</version> 
</dependency> 
```

现在，为了在 eclipse 中添加这个，转到

```html
Window -> Show View -> Other -> Maven -> Maven Repositories
```

如果你没有使用 maven，那么你可以从 [POI 下载](http://poi.apache.org/download.html)页面下载 maven jar 文件。运行示例代码至少要包含以下 jar 文件:

*   然后-3.10-结束。恰恰相反
*   then-ooxml-3.10-结束。恰恰相反
*   commons-codec-1.5。冲突

*   XML API-1。0 .b 2 的位置。恰恰相反
*   StAX API-1。0 .1 .恰恰相反

本文由 [**潘卡吉·库马尔**](https://www.linkedin.com/in/prakuj/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。