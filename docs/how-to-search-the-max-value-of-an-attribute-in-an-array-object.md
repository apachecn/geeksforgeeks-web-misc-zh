# 如何搜索数组对象中某个属性的最大值？

> 原文:[https://www . geesforgeks . org/如何搜索数组中对象的最大属性值/](https://www.geeksforgeeks.org/how-to-search-the-max-value-of-an-attribute-in-an-array-object/)

可以通过两种方式搜索对象数组中属性的最大值，一种是遍历数组，另一种是使用 **Math.max.apply()** 方法。

**示例 1:** 在此示例中，遍历数组，并针对数组的每个索引比较对象的所需值。

```html
// Array of object
var arr = [
    {
      a: 10,
      b: 25
    },
    {
        a: 30,
        b: 5
    },
    {
        a: 20,
        b: 15
    },
    {
        a: 50,
        b: 35
    },
    {
        a: 40,
        b: 45
    },
  ];

  // Returns max value of 
  // attribute 'a' in array
  function fun(arr){
    var maxValue = Number.MIN_VALUE;

    for(var i=0;i<arr.length;i++){
        if(arr[i].a>maxValue){
        maxValue = arr[i].a;
       }
    }
    return maxValue;
  }

  var maxValue = fun(arr);
  console.log(maxValue);
```

**输出:**

```html
50
```

**示例 2:** 在本例中，我们使用**数学最大应用()**函数来查找属性的最大值。它有两个参数:

1.  这
2.  类似数组的对象

**语法:**

```html
Math.max.apply(thisArg, [ argsArray])
```

**更多信息**可在[https://developer.mozilla.org/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)找到

```html
var arr = [
    {
      a: 10,
      b: 25
    },
    {
        a: 30,
        b: 5
    },
    {
        a: 20,
        b: 15
    },
    {
        a: 50,
        b: 35
    },
    {
        a: 40,
        b: 45
    },
  ];

  var maxValue = Math.max.apply(null, 
    arr.map(function(o) { return o.a; }));

  console.log(maxValue);
```

**输出:**

```html
50
```