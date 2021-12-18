# 如何合并多个内联样式对象？

> 原文:[https://www . geesforgeks . org/如何合并多内联样式的对象/](https://www.geeksforgeeks.org/how-to-merge-multiple-inline-style-objects/)

多个内联样式可以通过两种方式合并，这两种方式描述如下:

**方法 1-使用扩散算子:**将…算子称为[扩散算子](https://www.geeksforgeeks.org/javascript-spread-operator/)。在这种情况下，扩展运算符将两个对象连接成一个新对象。下面是使用 spread 运算符合并多个内联样式的实现。

## java 描述语言

```html
import React from 'react';

const text= {
    color: 'green',
    fontSize: '50px'
,
    textAlign: 'center'
}
const background = {
    background: "#e0e0e0"
}

export default function App(){
    return (
      <div style={{...text,...background}}>
         <h1>GeeksforGeeks</h1>
      </div>
    )
}
```

**方法 2-使用 Object.assign():** 下面是使用 [Object.assign()](https://www.geeksforgeeks.org/object-assign-javascript/) 方法合并多个内联样式的实现。在这种情况下，文本和背景对象都被分配给一个新的空对象。

## java 描述语言

```html
import React from "react";

const text= {
    color: 'green',
    fontSize: '50px'
,
    textAlign: 'center'
}
;
const background = {
    background: "#e0e0e0"
};

export default function App() {
  return (
    <div style={Object.assign({}, text, background)}>
      <h1>GeeksforGeeks</h1>
    </div>
  );
}
```

**输出:**在这两种方法中，如果两个或多个对象具有相同的属性，则最右边的对象的属性将反映在输出中。

![](img/ad3f462bbc01180e349ac4de6f7bdca5.png)