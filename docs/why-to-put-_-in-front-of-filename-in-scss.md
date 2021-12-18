# 为什么在 SCSS 文件名前面加“_”？

> 原文:[https://www . geesforgeks . org/why-to-put-_-in-filename-in-SCS/](https://www.geeksforgeeks.org/why-to-put-_-in-front-of-filename-in-scss/)

当我们在 SCSS 文件前面加上“_”时，这意味着它对 SCSS 是偏袒的。当编译器得到任何以“_”开头的 SCSS 文件时，它会忽略该文件。如果您想将 SCSS 的这个部分包含在样式中，您必须使用@import。使用分音的优势在于，您可以使用样式文件来组织您的代码，并且所有文件都将在一个文件中编译。部分 SCSS 的目的是保持你的风格分成逻辑部分。
最后，我们希望一个 SCSS 文件已经被编译，而我们可以有许多逻辑部分的 SCSS 文件。

**语法:**

```
@import filename;
```

**注意:**导入时我们不放“_”，只放文件名。

**示例 1:** 让我们创建一个 colors 文件 _colors.scss

```
$first-color: blue;
$second-color: yellow;

// let's include it in main
// SCSS file, style.scss

@import "colors"; 
body {
  color: $first-color;
  background: $second-color;
}
```

**输出:**

```
body {
  color: blue;
  background: yellow; 
}

```

**示例 2:** 让我们创建一个颜色文件

```
$font: arial;
$color: red;

// Let's include it in main
// SCSS file, style.scss

@import "font";
body {
  font: 100% $font;
  color: $color;
}
```

**输出:**

```
body {
  font: 100% arial;
  color: red;
}

```