# 网页振动 API |导航器.振动()方法

> 原文:[https://www . geesforgeks . org/web-振动-API-navigator-振动-method/](https://www.geeksforgeeks.org/web-vibration-api-navigator-vibrate-method/)

**navigator . vibrant()**方法使用设备上的*振动硬件*，如果存在这样的硬件的话。如果设备不支持振动，那么这种方法不会受到影响。如果调用此方法时振动模式已经开始，则之前的模式将停止，而新的模式将开始。

如果我们在方法中放入无效的参数，那么它将不会振动，并且它将返回 false，否则它将返回 true。如果振动距离我们的模式太长，那么它就会被截断。最大长度取决于实现。

**语法:**

```html
*var* successBool = window.navigator.vibrate( *pattern* );
```

**参数:**该方法接受单参数**模式**，为振动和暂停间隔提供模式。振动值和间隔值都是交替的，并且值以毫秒为单位。我们可以提供单个值或一组值。将 0、空数组或全零数组作为参数传递将会取消任何当前正在进行的振动。

**返回值:**成功返回真，否则返回假。

下面的例子说明了超文本标记语言振动应用编程接口中的导航器振动()方法:

**例 1:**

```html
// To check that is vibration API supported
if (navigator.vibrate) {
    window.navigator.vibrate(200);
}
```

**输出:**

```html
Vibrates for 200 milliseconds
```

**例 2:**

```html
// To check that is vibration API supported
if (navigator.vibrate) {
    window.navigator.vibrate(0);
}
```

**输出:**

```html
Will cancel any currently ongoing vibration pattern
```

**例 3:**

```html
// To check that is vibration API supported
if (navigator.vibrate) {
    window.navigator.vibrate([100, 30, 100, 30, 100, 30, 200, 
                     30, 200, 30, 200, 30, 100, 30, 100, 30, 100]);
}
```

**输出:**

```html
Vibrate 'SOS' in Morse
```

**支持的浏览器:**Web 振动 API Navigator.vibrate()方法支持的浏览器如下:

*   谷歌 Chrome 32 或以上
*   Firefox 16 或更高版本