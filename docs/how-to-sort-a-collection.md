# 如何对一个集合进行排序？

> 原文:[https://www.geeksforgeeks.org/how-to-sort-a-collection/](https://www.geeksforgeeks.org/how-to-sort-a-collection/)

我们将讨论如何对集合中的项目进行排序。为此使用了 [sort()](https://www.geeksforgeeks.org/collect-js-sort-method/) 方法。集合接受可能包含数字、字符串或对象的数组的输入。

**语法:**

```
collect(array).sort()
```

**参数:**它以数组为参数，转换成集合，然后根据其元素的值进行排序。

我们可以通过两种方式使用 Collection.js 方法对集合进行排序，这两种方法都在下面提到和描述:

*   [**采集所有()方法**](https://www.geeksforgeeks.org/collect-js-all-method/)
*   [**Collect.js sortByDesc()方法**](https://www.geeksforgeeks.org/collect-js-sortbydesc-method/)

[**Collect.js all()方法:**](https://www.geeksforgeeks.org/collect-js-all-method/)**[all()](https://www.geeksforgeeks.org/collect-js-all-method/)函数返回底层数组中集合所代表的所有元素。JavaScript 数组首先被转换成一个集合，然后该函数被应用于该集合。**

****语法:****

```
sorted_collection.all()
```

****例 1** :这里 collect = require('collect.js ')用于将 [collect.js](https://github.com/ecrmnn/collect.js) 库导入文件。**

## **超文本标记语言**

```
<script>

    const collect = require('collect.js'); 
    const arr = [8, 2, 14, 26, 21, 17, 19]
    const collection = collect(arr);

    const sorted = collection.sort();

    console.log(sorted.all());
</script>
```

****输出:****

```
[2, 8, 14, 17, 19, 21, 26]
```

****示例 2:** 我们也可以使用一些算法对集合进行降序排序。我们可以为此传递一个回调函数。**

## **超文本标记语言**

```
<script>

    const collect = require('collect.js'); 
    const arr = [8, 2, 14, 26, 21, 17, 19]
    const collection = collect(arr);

    const descending_sort = collection.sort((a, b) => b - a);

    console.log(descending_sort.all());

</script>
```

****输出:****

```
[26, 21, 19, 17, 14, 8, 2]
```

**[**JavaScript sortByDesc()方法**](https://www.geeksforgeeks.org/collect-js-sortbydesc-method/) **:** 如果元素是对象，那么我们可以使用 [sortByDesc()](https://www.geeksforgeeks.org/collect-js-sortbydesc-method/) 方法进行排序，该方法使用一个键作为参数对元素集合进行降序排序。**

****语法:****

```
collect(array).sortByDesc(key)
```

****参数:****

*   ****数组:**它以数组为输入，要转换成集合**
*   ****键:**是对元素进行降序排序的参数**

****例 1:****

## **超文本标记语言**

```
<script>
    const collect = require('collect.js');
      const arr = ['Science', 'Welcome',
                 'Computer', 'GeeksforGeeks']

    const collection = collect(arr);

    const descending_sort = collection.sortByDesc();
    console.log(descending_sort);
</script>
```

****输出:****

```
Collection { items: [ 'Welcome', 'Science', 'GeeksforGeeks', 'Computer' ] }
```

****示例 2:** 我们还可以传递一个对象数组，并使用对象的一个属性作为关键字来对集合的元素进行排序。**

## **超文本标记语言**

```
<script>  
    const collect = require('collect.js');

    let Employee = [
        {
            name: 'Shyam',
            id: 21
        },
        {
            name: 'Aditya',
            id: 48
        },
        {
            name: 'Chris',
            id: 12
        }
    ];  
    const collection = collect(Employee);

    const sort_id = collection.sortByDesc('id')
    console.log(sort_id);
</script>
```

****输出:****

```
Collection {
 items: [
   { name: 'Aditya', id: 48 },
   { name: 'Shyam', id: 21 },
   { name: 'Chris', id: 12 }
 ]
}
```