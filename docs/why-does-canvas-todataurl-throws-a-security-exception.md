# 【canvas.toDataURL()为什么会抛出安全异常？

> 原文:[https://www . geesforgeks . org/why-canvas-todaytaul-throws-a-security-exception/](https://www.geeksforgeeks.org/why-does-canvas-todataurl-throws-a-security-exception/)

**canvas . todaytaull():**canvas . todaytaull()方法返回 web 资源的 URI(统一资源标识符)。它由以类型参数指定的格式描述的图像组成，该参数的默认值为巴布亚新几内亚。

**语法:**

```html
Canvas.toDataURL(type, encoderOptions);

```

*   **类型:**它是一个可选属性，包含关于图像格式的 DOMString 注释。它的默认值是巴布亚新几内亚。
*   **编码选项:**它由 0 到 1 之间的数值组成，用于指示各种图像格式要使用的图像质量。它的默认值是 0.92。

**安全异常:**如果画布元素不是原点干净的，即如果其原点干净标志没有设置，则抛出安全异常。(假)。换句话说，如果画布元素包含外来内容，那么安全性就岌岌可危，并且会出现 SECURITY_ERR 异常。当画布用于绘制不遵循与原点相关的规则且不使用 CORS(跨原点资源共享)机制的数据时，它就会被污染。受污染的帆布被认为是不安全的。尝试从画布中检索图像数据将导致安全异常指示的失败。除了 toDataURL()，调用 toBlob()和 getImageData()等方法也会导致类似的错误。
这些例外用于保护用户，防止他们的私人数据在未经他们事先许可的情况下被泄露。因为图像可以用来从网站获取信息，所以使用异常是必须的。

**示例:**产生异常的画布元素。

## java 描述语言

```html
function getBase64FromImageUrl(URL) {
    var img = new Image();
    img.src = URL;
    img.onload = function () {

        var canvas = document.createElement("canvas");
        canvas.width = this.width;
        canvas.height = this.height;

        var ctx = canvas.getContext("2d");
        ctx.drawImage(this, 0, 0);

        var dataURL = canvas.toDataURL("image/png");

alert(dataURL.replace(/^data:image\/(png|jpg);base64,/, ""));

    };
}
```

**输出:**当试图操纵画布上未经授权在代码中处理的图像时，会出现这种安全错误。这些错误是由服务器已批准的请求的“访问控制-允许-来源”标头引起的。由于图像属于另一个领域，大多数浏览器在访问它们时都会显示异常，导致严重的安全漏洞。

```html
Uncaught Security Error: Failed to execute ‘toDataURL’ on 
‘HTMLCanvasElement’: tainted canvases may not be exported.

```

**上述问题的解决方案:**图像具有一个称为 crossorigin 的属性，该属性在 HTML 中指定，并且通过将其与合适的 CORS 头部相结合，它可以从外部来源加载，以在画布中使用，表现得像属于当前来源。如果没有获得 CORS 的批准，画布就会变得有污点，并且没有从画布中提取数据的规定。因此，像 **toBlob()** 、**todaytaul()**或 **getImageData()** 这样的方法不能在不抛出安全错误的情况下使用。可以通过使用 Javascript 或 HTML 设置图像的 crossorigin 属性来防止这些错误

**示例:**

*   **HTML:**

```html
<img src="otherdomain.com"/>

```

*   **JavaScript:**

```html
  var image = new Image();
  image.crossOrigin = "Anonymous";
  ...

```

**注意:**只有当服务器响应上有以下访问控制-允许-起源头时，这种方法才能工作。否则，来自源' otherdomain.com '的映像将被跨源资源共享策略阻止加载。

因为问题是映像不属于当前域，所以可以创建一个服务器语言的代理，类似于在 HTTPS 内容上显示 HTTP 内容，为其提供一个安全的环境。