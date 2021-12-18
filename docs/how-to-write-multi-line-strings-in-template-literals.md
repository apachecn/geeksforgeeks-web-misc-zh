# 如何在模板文字中写入多行字符串？

> 原文:[https://www . geesforgeks . org/如何编写多行模板字符串/](https://www.geeksforgeeks.org/how-to-write-multi-line-strings-in-template-literals/)

[模板文字](https://www.geeksforgeeks.org/javascript-template-literals/)是在 ES6 中引入的，因此，我们以现代的方式使用字符串。通常在定义字符串时，我们在 JavaScript 中使用双引号/单引号(“”或“”)。但是在模板文字中，我们使用 backtick(` `)。

让我们看看如何在模板文本中编写多行字符串。

**示例 1:** 我们通过模板文字编写多行字符串。

## HTML

```
<script>
    const multilineString = `How 
    are you
    doing
    I am fine`;

    console.log(multilineString);
</script>
```

**输出:**

```
How      
are you  
doing    
I am fine
```

**示例 2:** 如果您使用双引号/单引号来编写多行字符串，那么我们使用换行符(\n)。在每个换行符(\n)后使用一个额外的反斜杠(\)，这个反斜杠告诉 JavaScript 引擎字符串还没有结束。

## HTML

```
<script>
    var multilineString = 
    "How \n\
    are you \n\
    doing \n\
    I am fine";

    console.log(multilineString);
</script>
```

**输出:**

```
How 
are you
doing
I am fine
```