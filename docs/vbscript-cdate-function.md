# VBScript CDate()函数

> 原文:[https://www.geeksforgeeks.org/vbscript-cdate-function/](https://www.geeksforgeeks.org/vbscript-cdate-function/)

**VBScript CDate 函数**用于将有效的日期和时间表达式转换为日期类型。它返回正确的日期顺序。它根据系统的区域设置识别日期格式。

**注意:**我们也可以使用 **IsDate** 功能来确定日期是否可以转换为日期或时间。

**语法:**

```html
CDate(date)
```

**参数:**该函数接受单个 a 参数，如上所述，如下所述。

*   **Date:** Required attribute. It specifies any valid date expression.

**示例 1:** 以下示例说明了 VBScript CDate 函数。

## VBScript

```html
<%
  gfg=CDate("May 6, 2020")
  response.write(gfg)
%>
```

**输出:**

```html
5/6/2020
```

**示例 2:** 下面的代码说明了如何用分隔符将数字转换为日期:

## VBScript

```html
<%
  gfg=CDate(#4/22/10#)
  response.write(gfg)
%>
```

**输出:**

```html
4/22/2010
```