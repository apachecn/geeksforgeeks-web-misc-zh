# 如何指定标签绑定到哪个表单元素？

> 原文:[https://www . geeksforgeeks . org/如何指定标签绑定到哪个表单元素/](https://www.geeksforgeeks.org/how-to-specify-which-form-element-a-label-is-bound-to/)

HTML 中的[*标签*](https://www.geeksforgeeks.org/html-label-tag/) 标签允许我们点击标签，这又会被视为点击相应的输入类型。HTML 中的输入类型可以是单选按钮、复选框、电子邮件、日期、颜色等。用于 属性的[*指定标签绑定到哪个表单元素。*](https://www.geeksforgeeks.org/html-for-attribute/)

**语法:**

```html
<label for="element_id"> Label Content </label>
```

**示例 1:**

## HTML

```html
<!DOCTYPE html>
<html lang="en">
  <body style="text-align: center">
    <h1 style="color: green">GeeksforGeeks</h1>

    <h2>Label for attribute</h2>

    <p>Please click on the labels to select the radio button</p>

    <form>
      <label for="Student">Student</label>
      <input type="radio" name="Category" id="Student" value="Student" />
      <br />

      <label for="WorkingProfessional">
         Working Professional
      </label>
      <input
        type="radio"
        name="Category"
        id="WorkingProfessional"
        value="WorkingProfessional"/>
      <br />

      <label for="Retired">Retired</label>
      <input type="radio" name="Category" 
             id="Retired" value="Retired" />
      <br />
      <br />
      <input type="submit" value="Submit" />
    </form>
  </body>
</html>
```