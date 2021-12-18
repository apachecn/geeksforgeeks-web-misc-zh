# 目标值和目标条目之间的差异方法

> 原文:[https://www . geesforgeks . org/object-value-and-object-entries-methods/](https://www.geeksforgeeks.org/difference-between-object-values-and-object-entries-methods/)

对象是继承所有 javascript 对象的父类，这两个方法是对象类的静态方法，因为它们是由对象类的类名调用的。

**Object.values()方法:**在循环中，按照与 for…相同的顺序，Object.values()方法返回一个对象的可枚举属性值数组。这是唯一的区别:循环中的 for…也枚举原型链中的属性。

**语法:**

```html
Object.values(object)
```

*   **参数:**这个对象是可枚举的，它有自己的属性，应该返回这些属性的值。
*   **返回类型:**值数组

**示例:**用户可以通过按 *ctrl + shift + I* 打开控制台进入 chrome 网页浏览器。

## 超文本标记语言

```html
<script>
    let fullname = {
        firstname: "geeks",
        middlename: "for",
        lastname: "geeks",
    };
    let name = Object.values(fullname);
    console.log(name);
</script>
```

**输出:**

```html
["geeks", "for", "geeks"]
```

**对象.条目()方法:**

此方法返回对象的可枚举字符串键属性的键和值的数组。它的工作方式类似于在循环中用 for…进行迭代，只是循环中的 for…也枚举了原型链中的属性。

**语法:**

```html
Object.entries(object)
```

*   **参数:**返回对象自己的可枚举字符串键属性[键，值]对。
*   **Return:** 这是给定对象的字符串键属性[键，值]对的数组。

**示例:**

## 超文本标记语言

```html
<script>
    let fullname = {
        firstname: "geeks",
        middlename: "for",
        lastname: "geeks",
    };
    let name = Object.entries(fullname);
    console.log(name);
</script>
```

**输出:**

```html
[["firstname", "geeks"], 
 ["middlename", "for"], 
 ["lastname", "geeks"]]
```

**object . value 和 object.entries 的区别方法:**

<figure class="table">

| 对象。价值 | 对象。进入 |
| --- | --- |
| It returns an array of values for a specific object. | It returns an array of key-value pairs. |
| It only returns the values of all keys that exist in an object. | It returns two keys and their existing values. |

</figure>