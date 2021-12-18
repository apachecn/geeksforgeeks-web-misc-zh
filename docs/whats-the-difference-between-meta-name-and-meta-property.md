# 元名和元属性有什么区别？

> 原文:[https://www . geeksforgeeks . org/meta-name 和 meta-property 的区别是什么/](https://www.geeksforgeeks.org/whats-the-difference-between-meta-name-and-meta-property/)

**[元数据:](https://www.geeksforgeeks.org/html-meta-tag/)**
元数据是关于数据的信息。所以基本上，元标签为您提供了 HTML 文档上的信息。所以基本上这个标签是一个空标签，这意味着它只有一个开始标签，没有结束标签。HTML 文档中元标签的数量取决于 HTML 文档，它不影响 HTML 文档的物理外观。
元标签始终在标签内部。所以基本上你可以在 body 标签中使用 meta 属性，但是它应该包含 property 元素。

```html
Various Types of HTML attributes:
```

1.  **名称属性**
    这个属性基本上是用来说明房产名称的。
2.  **Http-等效属性**
    这个属性基本上是用来获取一个 Http 响应消息头的。
3.  **作者**
    基本上是用来指定文档作者的名字。
4.  **描述**
    它基本上显示了特定 HTML 页面的描述
5.  **内容属性**
    该属性用于特定的属性值

**元属性:**
元属性只是类似于元标签，只有当我们谈论不同版本的 HTML 时，差异才会出现。元属性来自 RDFa。所以基本上，元属性用于链接主体标签中的元素，只要它们包含属性标签，并且主体标签基本上是主要的父标签，然后我们使用元属性链接主体标签中的另一个标签。

```html
<meta property="og:title" content="Main Title">
<meta property="og:description" content="About  the description">
```

并且完全允许同时使用 Rfda 的属性和 html5 的名称属性。

只有在没有提供 HTML % %的名称属性的情况下，您才能将微数据的 itemProp 属性与 RFDA 的属性一起使用。

```html
<meta itemprop="description" 
      property="og:description" 
      content="About the  description" />
```

**元标签和元属性的区别:**
基本上元名称是 HTML 文档中使用非常频繁的常用名称。那么基本上什么是元属性呢？。属性属性来自 HTML5 中的 RDFa。所以基本上你可以在同一个元标签上一起使用元属性

```html
<meta name="description" 
      property="og:description" 
      content="description about the content" />
```