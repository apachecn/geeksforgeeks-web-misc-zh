# 网络音频应用编程接口|音频节点数量输出属性

> 原文:[https://www . geesforgeks . org/web-audio-API-audio node-numberofoutputs-property/](https://www.geeksforgeeks.org/web-audio-api-audionode-numberofoutputs-property/)

**AudioNode.numberOfOutputs 属性**用于返回来自节点的输出数量。对于此属性，目标节点*音频目标节点*的值为 0。

**语法:**

```html
var numOutputs = audioNode.numberOfOutputs;
```

**返回值:**返回大于等于零的整数值。

**例 1:**

```html
<!DOCTYPE HTML> 
<html> 

<head> 
    <title> 
        Web Audio API | AudioNode numberOfOutputs property
    </title>
</head> 

<body> 

    <h1 style = "color:green;" > 
        GeeksforGeeks
    </h1>

    <h2>
        AudioNode numberOfOutputs property
    </h2>

    <script>

        // Create new Audio context
        const audioContext = new AudioContext();

        // Create an OscillatorNode 
        const oscillator = audioContext.createOscillator();
        const gainNode = audioContext.createGain();

        oscillator.connect(gainNode).connect(audioContext.destination);

        // Display the numberOfOutputs in console view
        console.log(oscillator.numberOfOutputs);
    </script>
</body>

</html>                    
```

**输出:**
![](img/43ab46909d21c5bbdbbfbb30348daa40.png)

**例 2:**

```html
<!DOCTYPE HTML> 
<html> 

<head> 
    <title> 
        Web Audio API | AudioNode numberOfOutputs property
    </title>
</head> 

<body> 

    <h1 style = "color:green;" > 
        GeeksforGeeks
    </h1>

    <h2>
        AudioNode numberOfOutputs property
    </h2>

    <script>

        // Create new Audio context
        const audioContext = new AudioContext();

        // Create an OscillatorNode 
        const oscillator = audioContext.createOscillator();
        const gainNode = audioContext.createGain();

        oscillator.connect(gainNode).connect(audioContext.destination);

        // Display the numberOfOutputs in console view
        console.log(gainNode.numberOfOutputs);
    </script>
</body>

</html>                   
```

**输出:**
![](img/43ab46909d21c5bbdbbfbb30348daa40.png)

**例 3:**

```html
<!DOCTYPE HTML> 
<html> 

<head> 
    <title> 
        Web Audio API | AudioNode numberOfOutputs property
    </title>
</head> 

<body> 

    <h1 style = "color:green;" > 
        GeeksforGeeks
    </h1>

    <h2>
        AudioNode numberOfOutputs property
    </h2>

    <script>

        // Create new Audio context
        const audioContext = new AudioContext();

        // Create an OscillatorNode 
        const oscillator = audioContext.createOscillator();
        const gainNode = audioContext.createGain();

        oscillator.connect(gainNode).connect(audioContext.destination);

        // Display the numberOfOutputs in console view
        console.log(audioContext.destination.numberOfOutputs);
    </script>
</body>

</html>                    
```

**输出:**
![](img/6da4e1c7733154f64c065d63c2000eb8.png)

**支持的浏览器:**下面列出了 *AudioNode.numberOfOutputs 属性*支持的浏览器:

*   谷歌 Chrome 14.0
*   Edge 12.0
*   Firefox 25.0
*   Safari 6.0
*   Opera 15.0