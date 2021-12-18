# DOM(文档对象模型)

> 原文:[https://www.geeksforgeeks.org/dom-document-object-model/](https://www.geeksforgeeks.org/dom-document-object-model/)

**示例:**在这个示例中，我们使用 HTML 元素 id 来查找 DOM HTML 元素。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
  <h2>GeeksforGeeks</h2>
  <!--In this e.g. We find HTML Elements by Id in DOM -->
  <p id="intro">A Computer Science portal for geeks.</p>

<p>This example illustrates the <b>getElementsById</b> method.</p>

  <p id="demo"></p>

  <script>
    const element = document.getElementById("intro");

    document.getElementById("demo").innerHTML =
      "GeeksforGeeks introduction is: " + element.innerHTML;
  </script>
</body>

</html>
```

**输出:**

![](img/469bf0f9bc4a630977aecf5a05a5899e.png)

在这篇文章中，我们将讨论文档对象模型及其属性和用于操作文档的方法。

文档对象模型(DOM)是用于 **HTML** 和 **XML** 文档的 ***编程接口*** 。它定义了文档的**逻辑结构**以及访问和操作文档的方式。

**注**:之所以叫逻辑结构，是因为 DOM 没有指定对象之间的任何关系。

DOM 是一种以结构化的层次方式表示网页的方式，这样程序员和用户就可以更容易地浏览文档。使用 DOM，我们可以使用 Document 对象提供的命令或方法，轻松地访问和操作标签、标识、类、属性或元素。

**为什么需要 DOM？**

HTML 用来**构造**网页，Javascript 用来给我们的网页添加**行为**。当一个 HTML 文件被加载到浏览器中时，javascript 无法直接理解 HTML 文档。因此，创建了一个相应的文档(DOM)。 **DOM 基本上是相同的 HTML 文档的表示，但是使用了不同的对象格式**。Javascript 很容易解释 DOM，即 javascript 无法理解 HTML 文档中的标签(< h1 > H < /h1 >)但可以理解 DOM 中的对象 h1。现在，Javascript 可以通过使用不同的函数来访问每个对象(h1、p 等)。

**DOM 的结构** : DOM 可以认为是一棵树或者森林(不止一棵树)。术语**结构模型**有时用于描述文档的树状表示。DOM 结构模型的一个重要属性是 ***结构同构*** :如果使用任意两个 DOM 实现来创建同一文档的表示，它们将创建相同的结构模型，具有完全相同的对象和关系。

**为什么叫对象模型？**
使用对象对文档进行建模，模型不仅包括文档的结构，还包括文档的行为以及文档的对象，这些对象由 HTML 中具有属性的相似标记元素组成。

**DOM 的属性**:我们来看看文档对象可以访问和修改的文档对象的属性。

![](img/1e65687343857b235bfbd86fe06ae125.png)

1.  **窗口对象:**窗口对象始终位于层次结构的顶部。
2.  **文档对象:**当一个 HTML 文档被加载到一个窗口中时，它就变成了一个文档对象。
3.  **表单对象:**由 ***表单*** 标签表示。
4.  [**链接对象**](https://www.geeksforgeeks.org/html-dom-link-object/) **:用 ***链接*** 标签表示。**
5.  [**锚点对象**](https://www.geeksforgeeks.org/html-dom-anchor-object/) **:** 它由 ***a href*** 标签表示。
6.  **表单控件元素:**:表单可以有很多控件元素，如文本字段、按钮、单选按钮和复选框等。

**文档对象的方法**:

1.  **write(“字符串”):**在文档上写入给定的字符串。
2.  [**getElementById()**](https://www.geeksforgeeks.org/html-dom-getelementbyid-method/)**:**返回具有给定 Id 值的元素。
3.  [**getElementsByName()**](https://www.geeksforgeeks.org/html-dom-getelementsbyname-method/)**:**返回所有具有给定名称值的元素。
4.  [**getElementsByTagName():**](https://www.geeksforgeeks.org/html-dom-getelementsbytagname-method/)返回所有具有给定标签名的元素。
5.  [**getElementsByClassName()**](https://www.geeksforgeeks.org/html-dom-getelementsbyclassname-method/)**:**返回所有具有给定类名的元素。

**例**:

## 超文本标记语言

```html
<table>
  <ROWS>
    <tr>
      <td>Car</td>
      <td>Scooter</td>
    </tr>
    <tr>
      <td>MotorBike</td>
      <td>Bus</td>
    </tr>
  </ROWS>
</table>
```

![](img/796e92fcd241cad9a11beb103da9d83b.png)

**什么 DOM 不是？**

1.  文档对象模型不是一个**二进制描述**，它没有在其接口中定义任何二进制源代码。
2.  文档对象模型不用于描述 XML 或 HTML 中的**对象**，而 DOM 将 XML 和 HTML 文档描述为对象。
3.  文档对象模型不是由一组**数据结构**表示的；它是一个指定对象表示的接口。
4.  文档对象模型不显示文档中对象的**关键度，即它没有文档中哪个对象适合上下文，哪个不适合上下文的信息。**

**DOM 的级别**:

1.  **0 级:**提供一组低级接口。
2.  **级别 1:** DOM 级别 1 可以分为两部分来描述: **CORE** 和 **HTML** 。
    *   **CORE** 提供了可以用来表示任何结构化文档的低级接口。
    *   **HTML** 提供了可以用来表示 HTML 文档的高级接口。
3.  **2 级:**由 6 个规格组成: **CORE2** 、**view**、 **EVENTS** 、 **STYLE** 、**traversation**和 **RANGE** 。
    *   **CORE2** :扩展了 DOM 级别 1 指定的 CORE 的功能。
    *   **view**:view 允许程序动态访问和操作文档内容。
    *   **EVENTS** : Events 是当用户对网页做出反应时，由浏览器执行的脚本。
    *   **STYLE** :允许程序动态访问和操作样式表的内容。
    *   **遍历**:允许程序动态遍历文档。
    *   **RANGE** :允许程序动态识别文档中的内容范围。
4.  **3 级:**由五个不同的规格组成: **CORE3** 、 **LOAD and SAVE** 、 **VALIDATION** 、 **EVENTS** 和 **XPATH** 。
    *   **CORE3** :扩展了 DOM 二级指定的 CORE 的功能。
    *   **LOAD 和 SAVE** :允许程序将 XML 文档的内容动态加载到 DOM 文档中，并通过序列化将 DOM document 保存到 XML 文档中。
    *   **VALIDATION** :允许程序动态更新文档的内容和结构，同时保证文档保持有效。
    *   **事件**:扩展了 DOM Level 2 指定的事件的功能。
    *   **XPATH** : XPATH 是一种可以用来访问 DOM 树的路径语言。

**DOM 操作示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
  <title>DOM manipulation</title>
</head>

<body>
  Enter Value 1 <input type="text" id="val1" />
  <br />
  <br />
  Enter Value 2<input type=".text" id="val2" />
  <br />
  <br />
  <button onclick="getAdd()">Click To Add</button>
  <br />
  <p id="result"></p>

  <!-- Javascript code inside body tag -->
  <script type="text/javascript">
    function getAdd() {
      //it will fetch the value of input with id val1
      const num1 = Number(document.getElementById("val1").value);

      //It will fetch the value of input with id val2
      const num2 = Number(document.getElementById("val2").value);

      //addition
      const add = num1 + num2;

      console.log(add);

      //displaying the result in paragraph using dom
      document.getElementById("result").innerHTML = "Addition : " + add;

      //it will change the color of paragraph with red
      document.getElementById("result").style.color = "red";
    }
  </script>
</body>

</html>
```

**输出:**

![](img/d1efa9b00f201bb944976f760afaf28f.png)

**参考文献:**

1.  [https://codescracker.com/js/js-dom-levels.htm](https://codescracker.com/js/js-dom-levels.htm)
2.  [https://www.w3.org/TR/DOM-Level-3-Core/introduction.html](https://www.w3.org/TR/DOM-Level-3-Core/introduction.html)

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。