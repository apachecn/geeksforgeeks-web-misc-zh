# 如何在 Chrome 中创建粘性表头？

> 原文:[https://www . geeksforgeeks . org/如何在 chrome 中创建粘性表格标题/](https://www.geeksforgeeks.org/how-to-create-sticky-table-headers-in-chrome/)

向下滚动表格时，表格的标题固定在屏幕顶部，称为粘性表格标题。当视图中的原始标题丢失时，它们用于帮助查看者了解列中数据的用途。它消除了在表格中上下滚动以获取正在读取的数据的引用的不便。在这里，我们将看到如何在表中创建粘性表头。

**方法:**方法是将表格标题上的 position 属性设置为粘性，以便它们在向下滚动表格时保持固定在顶部。

**例:**

```htmlhtml
<!DOCTYPE html>
<html>

<head>
    <title>
        How to create sticky table 
        headers In Chrome?
    </title>

    <style>
        th {
            padding: 5px;
            background-color: #4cb96b;
            position: -webkit-sticky;
            position: sticky;
            top: 0;
        }
    </style>
</head>

<body>
    <p>
        Below is a table which has 
        sticky table headers
    </p>

    <table width="100%">
        <thead>
            <th>CHARACTER</th>
            <th>ENCODED FORM</th>
        </thead>
        <tbody style="text-align: center;">
            <tr>
                <td>backspace</td>
                <td>%08</td>
            </tr>
            <tr>
                <td>tab</td>
                <td>%09</td>
            </tr>
            <tr>
                <td>linefeed</td>
                <td>%0A</td>
            </tr>
            <tr>
                <td>c return</td>
                <td>%0D</td>
            </tr>
            <tr>
                <td>space</td>
                <td>%20</td>
            </tr>
            <tr>
                <td>!</td>
                <td>%21</td>
            </tr>
            <tr>
                <td>“</td>
                <td>%22</td>
            </tr>
            <tr>
                <td>#</td>
                <td>%23</td>
            </tr>
            <tr>
                <td>{content}lt;/td>
                <td>%24</td>
            </tr>
            <tr>
                <td>%</td>
                <td>%25</td>
            </tr>
            <tr>
                <td>&</td>
                <td>%26</td>
            </tr>
            <tr>
                <td>‘</td>
                <td>%27</td>
            </tr>
            <tr>
                <td>(</td>
                <td>%28</td>
            </tr>
            <tr>
                <td>)</td>
                <td>%29</td>
            </tr>
            <tr>
                <td>*</td>
                <td>%2A</td>
            </tr>
            <tr>
                <td>+</td>
                <td>%2B</td>
            </tr>
            <tr>
                <td>,</td>
                <td>%2C</td>
            </tr>
            <tr>
                <td>–</td>
                <td>%2D</td>
            </tr>
            <tr>
                <td>.</td>
                <td>%2E</td>
            </tr>
            <tr>
                <td>/</td>
                <td>%2F</td>
            </tr>
            <tr>
                <td>0</td>
                <td>%30</td>
            </tr>
            <tr>
                <td>1</td>
                <td>%31</td>
            </tr>
            <tr>
                <td>2</td>
                <td>%32</td>
            </tr>
            <tr>
                <td>3</td>
                <td>%33</td>
            </tr>
            <tr>
                <td>4</td>
                <td>%34</td>
            </tr>
            <tr>
                <td>5</td>
                <td>%35</td>
            </tr>
            <tr>
                <td>6</td>
                <td>%36</td>
            </tr>
            <tr>
                <td>7</td>
                <td>%37</td>
            </tr>
            <tr>
                <td>8</td>
                <td>%38</td>
            </tr>
            <tr>
                <td>9</td>
                <td>%39</td>
            </tr>
        </tbody>
    </table>
</body>

</html>
```

**输出:**

**说明:**
**位置:粘性**属性用于使表头相对于表体固定。切记粘性不适用于<标签和>或<标签，但可以与<和>一起使用。因此，我们将<>的位置设置为粘性，并将其设置为深色背景，否则透明度会使表格的其他数据在向下滚动时在标题后面可见。top 属性设置为 0，使标题固定在顶部。