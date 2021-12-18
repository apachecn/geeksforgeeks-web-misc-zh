# local storage 值的最大大小是多少？

> 原文:[https://www . geeksforgeeks . org/local storage-values 的最大大小是多少/](https://www.geeksforgeeks.org/what-is-the-max-size-of-localstorage-values/)

目前 localStorage 只支持字符串作为值，对象在存储到 localStorage 之前需要转换为 JSON 字符串。使用本地存储存储的数据不会发送回服务器(与 cookies 不同，)。所有的数据都保存在客户端，因此对于值的长度有一个定义的限制，根据我们使用的浏览器，我们目前可以存储从 **2 MB** 到 **10 MB** 大小的数据。

**语法:**

```
localStorage.setItem ( 'abc', 10 ); 
// this integer 10 gets converted to a string "10" 
// and then stored in localStorage variable named "abc".

```

**代码:**

这段代码用于计算 localStorage 变量的大小。

```
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
  <script>
    //this script is to find the size of localStorage

    function func1(num) 
    {
        return new Array((num * 1024) + 1).join('a')
    }

    // Determine the size of localStorage if it's not set

    if (!localStorage.getItem('size')) {
    var i = 0;
    try {
        // Test up to 10 MB
        for (i = 0; i <= 10000; i += 250) {
            localStorage.setItem('test', func1(i));
        }
        } catch (e) {
        localStorage.removeItem('test');
        localStorage.setItem('size', i ? i - 250 : 0);
        }
    }

// when window is loaded this function is
// called and the size of localStorage is calculated    
window.onload = function calculate(){
    var el = document.getElementById('size');        
    el.innerHTML = localStorage.getItem('size');
}

  </script>
</head>
<body>
<div >
     localStorage limit in your Browser is 
     <span id="size">...</span> KBs.
</div>
</body>
</html>
```

**输出:**

```
localStorage limit in your Browser is 5000 KBs.
```

**爆炸:**

这段 javascript 代码将通过添加不断增加长度的字符串来运行，直到浏览器引擎抛出异常。此后，它将清除测试数据，并在本地存储中设置一个大小键，以千字节(KBs)为单位存储本地存储的大小。

**参考:**[https://www . geeksforgeeks . org/html-DOM-storage-setitem-method/](https://www.geeksforgeeks.org/html-dom-storage-setitem-method/)