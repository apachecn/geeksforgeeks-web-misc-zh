# 如何使用包含对象的数组，并根据对象的属性检查对象？

> 原文:[https://www . geesforgeks . org/如何使用包含和检查对象的数组来对抗对象的属性/](https://www.geeksforgeeks.org/how-to-use-array-that-include-and-check-an-object-against-a-property-of-an-object/)

**Array.includes()方法:**在 JavaScript 中，includes()方法用于确定数组中是否存在特定元素。元素存在时返回 ***真*** ，元素不存在时返回 ***假*** 。

**语法:**

```
array_name.includes(searchElement, ?fromIndex)
```

**参数:**

*   **搜索元素:**数组中要搜索的元素。
*   **fromIndex:** 要从中搜索元素的索引。这是一个可选参数。

**例:**

## 超文本标记语言

```
<!DOCTYPE html>
<html lang="en">

<body>
    <h2>
        Checking if the countries 
        array contains Japan --->
        <span id="ans"></span>
    </h2>
    <h2>
        Checking for Japan in the countries 
        array from index 2 --->
        <span id="ans2"></span>
    </h2>

    <script>
        let countries = ["India", "Japan", 
            "Canada", "Germany", "Australia"];

        // 1st Output
        let ans = document.querySelector("#ans");
        let output = countries.includes("Japan");
        ans.append(output);

        // 2nd Output 
        let ans2 = document.querySelector("#ans2");
        let output2 = countries.includes("Japan", 2);
        ans2.append(output2);
    </script>
</body>

</html>
```