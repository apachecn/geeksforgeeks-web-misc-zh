# 如何指定表单数据在提交给服务器时应该如何编码？

> 原文:[https://www . geesforgeks . org/如何指定表单数据在提交给服务器时应该如何编码/](https://www.geeksforgeeks.org/how-to-specify-how-form-data-should-be-encoded-when-submitting-to-server/)

HTML 表单提供了三种编码方法。

*   应用程序/x-www-form-urlencoded
*   Part/Form-Data
*   Text/normal

**1。**[**application/x-www-form-URL encoded:**](https://www.geeksforgeeks.org/understanding-html-form-encoding-url-encoded-and-multipart-forms/)这是默认方法，如果没有指定则应用。在该方法中，空格被转换为“ **+** ”符号，特殊字符被转换为 ASCII 十六进制值，所有其他字符保持不变。

**示例:**

## HTML

```htmlhtml
<!DOCTYPE html>
<html>
<body>
   <!--create form to show the implementation of 
    encode type = application/x-www-form-urlencoded  -->
  <form  action="https://www.geeksforgeeks.org/" method="post" 
         enctype="application/x-www-form-urlencoded">
    <label for="fname">First name:</label>
    <input type="text" id="fname" name="fname">
    <br><br>
    <label for="lname">Last name:</label>
    <input type="text" id="lname" name="lname">
    <br><br>
    <input type="submit" value="Submit">
  </form>

</body>
</html>
```