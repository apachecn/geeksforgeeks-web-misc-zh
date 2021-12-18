# 如何在不改变原数组的情况下拼接数组？

> 原文:[https://www . geeksforgeeks . org/如何在不改变原始阵列的情况下拼接阵列/](https://www.geeksforgeeks.org/how-to-splice-an-array-without-mutating-the-original-array/)

在本文中，我们将从一个数组中提取元素的范围，而不对其进行修改。在这里，突变意味着改变原始数组。有一个内置函数用于从数组中提取元素，但它会使数组发生变异。

**怎么了。splice()方法工作原理:**splice 方法用于从数组中提取元素的范围。需要三个参数**索引**、**要删除的项目数、**要追加的项目数组。 索引(第一个参数)是必需的，其余参数是可选的。这个方法在移除项目后会传回新的阵列，但也会变异原始阵列。下面的例子解释了它是如何变异原始的。

## java 描述语言

```
<script>// Creating an array 
let originalArr = ["c", "cpp", "java", "python", "javascript", "kotlin"];

// Extracting three items from the index 0
let extractedArr = originalArr.splice(0, 3);

// Printing the Extracted array
console.log("Extracted Array")
console.log(extractedArr)

// Printing the original Array
console.log("Original Array")
console.log(originalArr)</script>
```

**输出:**

```
Extracted Array

["c", "cpp", "java"]

Original Array

["python", "javascript", "kotlin"]
```

这里可以看到原始数组是通过拼接的方法进行变异的。我们将实现拼接方法提供的相同功能，但不改变原始数组。这里我们将讨论两种方法来实现这个功能第一种方法是使用 ***复制*** 的数组，第二种方法是使用 ***过滤*** 的方法。

**方法 1:** 使用数组的副本。在这种方法中，我们将创建原始数组的副本，然后使用拼接方法提取项目。要创建阵列的拷贝或克隆，我们可以使用扩展运算符或拼接方法。

**步骤:**

*   使用扩展运算符或切片方法创建阵列的克隆。
*   对克隆的数组应用拼接方法，并返回提取的数组

**例:**

## java 描述语言

```
<script>// Creating an array 
let originalArr = ["c", "cpp", "java", "python", "javascript", "kotlin"];

// Creating the clone of the array
let cloneArr = originalArr.slice(0);

// Or you can use spread Operator
// let cloneArr = [...originalArr]

// Ectract the array using splice method
let extractedArr = cloneArr.splice(0, 4);

// Printing the Extracted array
console.log("Extracted Array")
console.log(extractedArr)

// Printing the original Array
console.log("Original Array")
console.log(originalArr)</script>
```

**输出:**这里原阵没有变异。但是在较大的阵列中应用这种方法并不是一个好的做法，因为当我们创建阵列的克隆时，它的空间消耗会增加。

```
Extracted Array
["c", "cpp", "java", "python"]

Original Array
["c", "cpp", "java", "python", "javascript", "kotlin"]
```

**方法 2:** 采用过滤法。在这种方法中，我们使用过滤方法。filter 方法用于在对数组的元素应用一些条件后将其过滤掉。这个方法不会改变数组。

**语法:**

```
Array.filter((item, index)=>{ return index >= start 
&& index < howMany + start })
```

**例 1:**

## java 描述语言

```
<script>// Creating an array 
let originalArr = ["c", "cpp", "java", "python", "javascript", "kotlin"];

let start = 1;
let howMany = 3;

let extractedArr = originalArr.filter((item, index)=>{
  return index >= start && index < howMany + start ;
})

// Printing the Extracted array
console.log("Extracted Array")
console.log(extractedArr)

// Printing the original Array
console.log("Original Array")
console.log(originalArr)

</script>
```

**示例 2:** 原型形式。

## java 描述语言

```
<script>// Creating an array 
let originalArr = ["c", "cpp", "java", "python", "javascript", "kotlin"];

Array.prototype.mySplice = function(start, howMany){
  return this.filter((item, index)=>{
    return index >= start && index < howMany + start ;
  })
}

// Printing the Extracted array
console.log("Extracted Array")
console.log(originalArr.mySplice(1, 3))

// Printing the original Array
console.log("Original Array")
console.log(originalArr)
</script>
```

**输出:**

```
Extracted Array
["cpp", "java", "python"]

Original Array
["c", "cpp", "java", "python", "javascript", "kotlin"]
```