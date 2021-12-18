# 地图内索引()功能

> 原文:[https://www.geeksforgeeks.org/index-inside-map-function/](https://www.geeksforgeeks.org/index-inside-map-function/)

在 JavaScript 中， **map()** 方法处理数组元素，该方法借助调用函数获得的结果为数组中的每个数组元素创建一个新数组。在 **map()** 方法中使用索引来声明数组中每个元素的位置，但它不会改变原始数组。

**语法:**

```html
array.map(function(currentelement, index, arrayobj) {

  // Returns the new value instead of the item

});

```

**参数:**索引内部函数接受三个参数，如上所述，如下所述:

*   **当前值:***当前值*是 map()中必需的参数，是当前元素的值。
*   **索引:***索引*是可选的参数映射()，它是所提供的当前元素的数组索引。
*   **arrayobj:***arrayobj*是 map()中的可选参数，是当前元素所属的数组对象。

以下示例说明了**地图内部索引()**功能:

**例 1:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
           "width=device-width, initial-scale=1">
</head>

<body style="text-align:center;">

    <h1 style="color:green;padding:13px;">
        GeeksforGeeeks
    </h1>

    <h3>Index inside map() Function</h3>

    <script>
        var student = ["Arun", "Arul", 
            "Sujithra", "Jenifer", "Wilson"];

        student.map((stud, index) => {
            alert("Hello... " + stud + "\n");

            var index = index + 1;

            alert("Your Position in Top 5"
                + " Rank is " + index + "\n");
        });
    </script>
</body>

</html>
```

**输出:**
![](img/61bf18c2b6cd2fd2d65588675634afd3.png)

**例 2:**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">

    <meta name="viewport" content=
        "width=device-width, initial-scale=1">
</head>

<body style="text-align:center;">

    <h1 style="color:green;padding:13px;">
      GeeksforGeeeks
    </h1>

    <h3>Index inside map() Function</h3>

    <script>
        var webname = ["welcome", "to",
                    "GeeksforGeeeks"];

        webname.map((web, index) => {
            document.write(web + "<br>");
        });

        // check in console
        webname.map((web, index)
            => console.log(web, index));
    </script>
</body>

</html>
```

**输出:**

```html
welcome
0
to
1
GeeksforGeeeks
2
```

**支持的浏览器:**地图内索引()功能支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧