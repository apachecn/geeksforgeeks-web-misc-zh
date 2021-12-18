# 哑剧媒体类型

> 原文:[https://www.geeksforgeeks.org/mime-media-types/](https://www.geeksforgeeks.org/mime-media-types/)

**MIME 媒体类型**基本代表多用途互联网邮件扩展媒体类型。这些媒体类型最初是为了让电子邮件包含除纯文本以外的信息而创建的。这些媒体类型向我们展示了以下内容:

1.  如何将文本和附件合并成一封邮件或电子邮件。
2.  不同的项目是如何编码传输的。

MIME 基本上将电子邮件的格式扩展到:

1.  非 ASCII 字符集的文本
2.  非 ASCII 字符集的标题信息
3.  附件是除纯文本以外的信息，如音频、视频、应用程序等。

在今天的场景中，它不仅被电子邮件使用，还被许多网络服务器使用，以某种方式告诉网络浏览器向它们发送什么类型的数据。

MIME 基本上由两部分组成。

1.  主要类型
2.  子类型

这些被进一步构造成树。主类型用斜线分隔子类型。

主要类型的示例:

```htmlhtml
application, audio, font, image, message, text 
```

子类型示例:

```htmlhtml
html, xml, zip, pdf, xls 
```

媒体类型的一些常见示例如下:

```htmlhtml
1\. application/json
2\. audio/mpeg
3\. text/pdf 
```

在这里，斜线之前是主类型，斜线之后是子类型。

互联网指定号码管理局(IANA)是这些分类的标准化和公布的官方机构。

**Content-Disposition–**
原始 MIME 规范只描述邮件的结构，没有任何呈现风格。但是内容处理标题的添加描述了邮件呈现样式的结构。MIME 部分可以有以下几个部分。

1.  在线内容处理
2.  附件内容处置

以下示例摘自 RFC 2183，其中定义了标题:

```htmlhtml
Content-Disposition: attachment; filename=genome.jpeg;
  modification-date="Wed, 12 Feb 1997 16:29:51 -0500"; 
```

文件名可以按照 RFC 2231 的定义进行编码。在 HTTP 中，Content-Disposition: attachment 响应头通常用于提示客户端将响应正文呈现为可下载的文件。

当收到这样的响应时，网络浏览器将提示用户将其内容保存为文件，而不是在浏览器窗口中显示为页面，文件名参数建议使用默认文件名。