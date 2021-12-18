# 如何从另一个数组中获取相同的值并赋给数组的对象？

> 原文:[https://www . geesforgeks . org/如何从另一个数组中获取相同的值并将其分配给数组对象/](https://www.geeksforgeeks.org/how-to-get-the-same-value-from-another-array-and-assign-to-object-of-arrays/)

要从另一个数组中获取相同的值并将其插入到数组的对象中，我们需要。

1.  比较两个数组的每个元素
2.  返回匹配的元素
3.  将元素或对象添加到数组的对象中

在进入代码之前，您可以阅读以下文章。它会帮助你更好地理解它，

*   [数组 forEach()方法](https://www.geeksforgeeks.org/es6-array-foreach-method/)
*   [阵推()法](https://www.geeksforgeeks.org/javascript-array-push-method/)
*   [数组包含()方法](https://www.geeksforgeeks.org/javascript-array-includes-method/)
*   [阵列滤波()方法](https://www.geeksforgeeks.org/es6-array-filter-method/)
*   [ES6 箭头功能](https://www.geeksforgeeks.org/arrow-functions-in-javascript/)

**方法 1:** 使用 forEach()和 push()，包括数组的()方法。

## java 描述语言

```html
<script>
  // Define first array
  let arr1 = [1, 2, 3, 4, 5, 77, 876, 453];

  // Define second array
  let arr2 = [1, 2, 45, 4, 231, 453];

  // Create a empty object of array
  let result = []; 

  // Checked the matched element between two 
  // array and add into result array
  arr1.forEach( val => arr2.includes(val) && result.push(val) );

  // Print the result on console
  console.log( result );
</script>
```

**输出:**

```html
 1, 2, 4, 453
```

**方法 2:** 过滤()，推送()并包含数组的()。

## java 描述语言

```html
<script>
  // Define first array
  let arr1 = [1, 2, 3, 4, 5, 77, 876, 453];

  // Define second array
  let arr2 = [1, 2, 45, 4, 231, 453];

  / Checked the matched element between two array
  // and add into the result array
  let result = arr1.filter(val => arr2.includes(val) );

  // Print the result on console
  console.log( result );

</script>
```

**输出:**

```html
 1, 2, 4, 453
```