# 网络音频应用编程接口|音频上下文输出延迟属性

> 原文:[https://www . geesforgeks . org/web-audio-API-audio context-output latency-property/](https://www.geeksforgeeks.org/web-audio-api-audiocontext-outputlatency-property/)

**音频上下文**接口具有**输出延迟**属性，该属性提供当前音频上下文输出延迟的近似值。这个时间在浏览器请求主机系统启动缓冲器和缓冲器中的第一个样本被音频输出设备实际处理的时间之间。

**语法:**

```
var latency = audioCtx.outputLatency;
```

**返回值:**

```
A double value is returned in seconds
```

**例 1:**

```
<!DOCTYPE html>
<html>

<head>
    <title>
        AudioContext outputLatency property
    </title>
</head>

<body>
    <center>
        <h1 style="color:green">
        GeeksforGeeks
        </h1>
        <h2>AudioContext outputLatency property</h2>
        <script>
            const audioCtx = new AudioContext();
            console.log(audioCtx.outputLatency);
        </script>
    </center>
</body>

</html>
```

**输出:**

```
undefined
```

**支持的浏览器:**