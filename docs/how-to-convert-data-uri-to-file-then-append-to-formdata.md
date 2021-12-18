# 如何将 URI 数据转换为文件，然后追加到表单数据？

> 原文:[https://www . geesforgeks . org/如何将数据 uri 转换为文件，然后追加到表单数据/](https://www.geeksforgeeks.org/how-to-convert-data-uri-to-file-then-append-to-formdata/)

数据 URI 是一个 base64 编码的字符串，代表一个文件(即，您可以在网页中插入文件的内容，而不是指定文件的网址)。当浏览器遇到 URI 时，它会解码并构建原始文件。数据 uri 是网络上最常用的图像。当一个网页想要另一个网页的文件时，该文件的 URI 可以方便地由 FormData 对象共享，该对象可以将 URI 作为(键，值)对，并使用 XMLHttpRequest 发送它。

**示例:**

```
Input: 1\. DataURI for a file.
       2\. fileName. // To store the file
Output: fileName - [ObjectFile]
```

**程序:**此过程可分 3 步完成。

*   **第一步:**数据 URI 作为输入。URI 可以直接作为输入给出，或者在 canvas 对象的情况下，可以使用 canvas.toDataURL 函数(类型[可选]，图像质量值 0 到 1[可选])获得。
*   **步骤 2:** 数据 URI 被转换成 Blob(二进制大对象-以二进制格式存储任何类型的数据，如图像、音频和视频)对象文件。
*   **步骤 3:** Blob 对象文件追加到 FormData 对象实例{key : value}中。

**示例:**假设“gif”类型的图像有一个数据 URI。
**输入:** URI 为一个图像。
**程序:**

```
<script type="text/javascript">
    var inputURL ="";

    var blobObject = blobCreationFromURL(inputURL);

    // Create Blob file from URL
    function blobCreationFromURL(inputURI) {

        var binaryVal;

        // mime extension extraction
        var inputMIME = inputURI.split(',')[0].split(':')[1].split(';')[0];

        // Extract remaining part of URL and convert it to binary value
        if (inputURI.split(',')[0].indexOf('base64') >= 0)
            binaryVal = atob(inputURI.split(',')[1]);

        // Decoding of base64 encoded string
        else
            binaryVal = unescape(inputURI.split(',')[1]);

        // Computation of new string in which hexadecimal
        // escape sequences are replaced by the character 
        // it represents

        // Store the bytes of the string to a typed array
        var blobArray = [];
        for (var index = 0; index < binaryVal.length; index++) {
            blobArray.push(binaryVal.charCodeAt(index));
        }

        return new Blob([blobArray], {
            type: inputMIME
        });
    }

    var fdataobj = new FormData();

    // Create formdata object and append the object
    // file to the name 'Blob file'
    fdataobj.append("Blob File", blobObject);

    // FormData object content is displayed in alert box.
    for (var pair of fdataobj.entries()) {
        alert('GeeksforGeeks\n' + pair[0] + '–' + pair[1])
    }
</script>
```

**输出:**FormData 对象的输出将作为名称和‘对象文件’值对显示在告警框中。可以使用 JavaScript 的 FileReader 对象来读取目标文件，该对象将读取目标文件，并且可以使用任何 JavaScript 显示技术来显示。
T3】