# 如何检查同一天的两个时间戳？

> 原文:[https://www . geeksforgeeks . org/如何检查两个时间戳的同一天/](https://www.geeksforgeeks.org/how-to-check-for-two-timestamp-for-the-same-day/)

给定两个时间戳，那么我们必须找出这些时间是否是同一日期。这里我们可以使用 [JavaScript 日期对象](https://www.geeksforgeeks.org/javascript-date/)。

**示例:**

```html
Input: TimeStamp1 = 20-04-2020 , 16:04:55 and 
       TimeStamp2 = 20-04-2020 , 10:22:42 

Output: These dates are of same date
```

```html
Input: TimeStamp1 = 20-04-2020 , 16:04:55 and 
       TimeStamp2 = 20-04-2019 , 10:22:42

Output: These timestamps are not on the same date.
```

*   **说明:**这些时间戳是同一日期，即 20-04-2020 在 JavaScript 对象中，这个日期可以转换。

```html
var D1 = new Date(2020, 04, 20, 16, 04, 55)
var D2 = new Date(2020, 04, 20, 10, 22, 42)
```

**方法 1:** 首先检查两个日期的年、月、日。如果都相等，那么我们可以说这两个日期相等。你查看这篇文章[T3【JavaScript 获取日期方法】T4](https://www.geeksforgeeks.org/javascript-get-date-methods/)。为了得到年份我们有 [**getFullYear()方法**](https://www.geeksforgeeks.org/javascript-date-getfullyear-function/) ，对于月份我们有 [**getMonth()方法**](https://www.geeksforgeeks.org/javascript-date-getmonth-method/) ，对于日期我们有 [**getDate()方法**](https://www.geeksforgeeks.org/javascript-date-getdate-function/) 。

*   **示例:**

## java 描述语言

```html
<script type = "text/javascript" >

    // Function to check whether timestamp are on same day
    const TimeStampAreOnSameDay = (d1, d2) =>
        d1.getFullYear() === d2.getFullYear() &&
        d1.getMonth() === d2.getMonth() &&
        d1.getDate() === d2.getDate();

    // To set two dates to two variables
    var d1 = new Date(2020, 4, 20, 16, 4, 55);
    var d2 = new Date(2020, 4, 20, 10, 22, 42);

    var result = TimeStampAreOnSameDay(d1 , d2);

    //To display the final result
    if (result === true)
        document.write("Time Stamp " + d1 + " and "
                       + d2 + " is of same day.");
   else
    document.write("Time Stamp " + d1 + " and "
                       + d2 + " is of different day.");
</script>
```

**输出:**

```html
*Time Stamp Wed May 20 2020 16:04:55 GMT+0530 (India Standard Time) and*
*Wed May 20 2020 10:22:42 GMT+0530 (India Standard Time) is of same day.*
```

**方法二:** 你要通过 [**<u>setHours()方法</u>**](https://www.geeksforgeeks.org/javascript-date-sethours-function/) 将小时、分、秒全部设置为 0，然后两者进行比较。

*   **示例:**

## java 描述语言

```html
<script type = "text/javascript" >

    // Function to check whether timestamp are on same day
    const TimeStampAreOnSameDay = (d1, d2) =>
        d1.setHours(0,0,0,0) === d2.setHours(0,0,0,0);

    // To set two dates to two variables
    var d1 = new Date(2020, 4, 20, 16, 4, 55);
    var d2 = new Date(2020, 4, 21, 10, 22, 42);

    var result = TimeStampAreOnSameDay(d1 , d2);

    //To display the final result
    if (result === true)
    document.write("Time Stamp " + d1 + " and "
                    + d2 + " is of same day.");
    else
    document.write("Time Stamp " + d1 + " and "
                    + d2 + " is of different day.");

</script>
```

**输出:**

```html
Time Stamp Wed May 20 2020 00:00:00 GMT+0530 (India Standard Time) and
Thu May 21 2020 00:00:00 GMT+0530 (India Standard Time) is of different day.
```