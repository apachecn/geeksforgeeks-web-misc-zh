# 如何从包含回车的字符串中获取原始内容？

> 原文:[https://www . geesforgeks . org/如何从包含回车符的字符串中获取原始内容/](https://www.geeksforgeeks.org/how-to-get-raw-content-from-a-string-including-carriage-return/)

字符串的原始内容包括回车，即它包含新的行转义序列。

**注意:**由“\n”和回车“\r”表示的换行非常不同。换行意味着将光标向前移动一行。回车意味着将光标移动到行首。Windows 编辑器在文本文件中仍然使用两者的组合作为' \r\n '。Unix 通常只使用“\n”。为简单起见，我们将换行符视为' \n '，即移动到下一行。

字符串到其原始形式的转换可以使用下面讨论的两种方法来完成:

**方法 1:使用 JSON.stringify()方法:**[JSON . stringify()](https://www.geeksforgeeks.org/javascript-json-stringify-with-examples/)方法用于将 JavaScript 对象或值转换为 JSON 字符串。以下示例显示了如何使用此方法获得原始内容:

## java 描述语言

```
<script>
// Define the original string
const str = 'Geeks\nFor\nGeeks';

console.log('Original String:');
console.log(str);
console.log('');

// Find the raw content
// using JSON.stringify()
console.log('Raw content:');
console.log(JSON.stringify(str));
</script>
```

**输出:**

```
Original String:
Geeks
For
Geeks

Raw Content:
"Geeks\nFor\nGeeks"
```

**方法 2:使用 string.replace()方法:**[string . replace()](https://www.geeksforgeeks.org/javascript-string-replace/)方法用于用另一个字符串或正则表达式替换给定字符串的一部分。原始字符串将保持不变。正则表达式用于替换字符串中需要的部分。正则表达式中的“g”参数确保所有的“\n”字符都转换为原始形式。

以下示例显示了如何使用此方法获得原始内容:

## java 描述语言

```
<script>
// Define the original string
const str = 'Geeks\nFor\nGeeks';

console.log('Original String:');
console.log(str);
console.log('');

// Find the raw content
// using JSON.stringify()
console.log('Raw content:');
console.log(str.replace(/\n/g, `\\n`));
</script>
```

**输出:**

```
Original String:
Geeks
For
Geeks

Raw Content:
"Geeks\nFor\nGeeks"
```