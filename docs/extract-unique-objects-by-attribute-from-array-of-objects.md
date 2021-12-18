# 从对象数组中按属性提取唯一对象。

> 原文:[https://www . geesforgeks . org/extract-从对象数组中按属性提取唯一对象/](https://www.geeksforgeeks.org/extract-unique-objects-by-attribute-from-array-of-objects/)

给定一个对象数组，任务是通过属性返回唯一的对象。

**示例:**

```html
Input: 
[ { name: 'Geeks', id: 10 },
  { name: 'GeeksForGeeks', id: 10 },
  { name: 'Geeks', id: 20 },
  { name: 'Geeks', id: 10 } ]
Output:
[ { name: 'Geeks', id: 10 }, 
  { name: 'GeeksForGeeks', id: 10 } ]

```

**方法:**假设名称是区分对象的属性，如果多个对象同名，则需要 id 号最小的对象。使用地图存储对象，并检查是否看到类似的对象。

*   初始化一个空映射。
*   使用筛选方法迭代数组。
*   检查地图中是否有与当前对象同名的条目。
*   —如果为真:即存在同名条目，则检查其 id 是否小于当前对象的 id。
*   ——如果为真:即当前对象的 id 小于地图返回的对象的 id，则删除地图条目，输入当前对象并返回真。
*   ——如果为 false:即当前对象的 id 大于地图返回的对象的 id，则返回 false。
*   —-如果为假:即地图中没有同名条目，则将当前对象输入地图。
*   打印唯一的对象。

**示例:**

```html
<script>
objects = [{
    name: 'Geeks',
    id: 10
}, {
    name: 'GeeksForGeeks',
    id: 10
}, {
    name: 'Geeks',
    id: 20
}, {
    name: 'Geeks',
    id: 10
}];

let mymap = new Map();

unique = objects.filter(el => {
    const val = mymap.get(el.name);
    if(val) {
        if(el.id < val) {
            mymap.delete(el.name);
            mymap.set(el.name, el.id);
            return true;
        } else {
            return false;
        }
    }
    mymap.set(el.name, el.id);
    return true;
});

console.log(unique);
</script>
```

**输出:**

```html
[ { name: 'Geeks', id: 10 }, 
  { name: 'GeeksForGeeks', id: 10 } ]

```

时间复杂度:O(n)
空间复杂度:O(n)