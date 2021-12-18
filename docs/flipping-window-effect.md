# 翻转窗口效果

> 原文:[https://www.geeksforgeeks.org/flipping-window-effect/](https://www.geeksforgeeks.org/flipping-window-effect/)

翻转窗口是现代网页设计中使用的一种新效果。这种效果被用作展示部分、装载部分和展示横幅。该效果基于沿 X 轴和 Y 轴旋转的四个正方形。旋转的顺序可以不同，即可以是 XX、XY、YX 或 YY。

**方法:**方法是创建 4 个互相对齐的方块，形成一个大方块(窗口)。然后使用*@关键帧*沿着 X 轴和 Y 轴旋转这些小方块。我们使用了 YX 的交替序列，即；第一次沿 Y 轴旋转，第二次沿 X 轴旋转，以此类推。

**第一节:**在这一节中，我们创建了四个“span”标签，包装在一个“div”标签中。

*   **HTML 代码:**

    ## HTML

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Flipping Window Effect</title>
    </head>
    <body>
        <div class="geeks">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </div>
    </body>
</html>
```