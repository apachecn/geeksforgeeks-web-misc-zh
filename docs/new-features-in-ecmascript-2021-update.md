# ECMAScript 2021 更新新功能

> 原文:[https://www . geesforgeks . org/new-features-in-ecmascript-2021-update/](https://www.geeksforgeeks.org/new-features-in-ecmascript-2021-update/)

ECMAScript 是 JavaScript 语言的一部分，主要用于网络技术、构建网站或网络应用程序。ECMAScript 正在成长为世界上使用最广泛的通用编程语言之一。它主要用于网络浏览器的嵌入，也用于服务器和嵌入式应用。

ECMAScript 的新更新将于今年 7 月发布。引入新的改进是为了让 JavaScript 更强大，也让开发人员更容易工作。它提供了新的功能、完成复杂工作的简单方法等等。

**新更新:****ECMAScript 2021**新增 JavaScript 功能如下:

**1。逻辑赋值运算符:**逻辑赋值运算符引入了新的运算符，将逻辑运算符和赋值表达式结合在一起。

*   **And & Equals (&&=):** It assigns when the value is truthy.

    **上一版本:**

    ```
    let x = 1;
    if(x){
      a = 10;
    }
    ```

    **输出:**

    ```
    x = 10
    ```

    **新版本:**

    ```
    let x = 1;
    x &&= 10;
    ```

    **输出:**

    ```
    x = 10
    ```

*   **OR & Equals (||=):** It assigns when the value is falsy. The assignment operation happens only if x is a falsy value.  If x contains 1 which is a truthy value, assignment does not happen. Here x contains 0 therefore assignment happens.

    **上一版本:**

    ```
    let x = 0;
    x = x || 10;
    ```

    **输出:**

    ```
    x = 10
    ```

    **新版本:**

    ```
    let x = 0;
    x ||= 10
    ```

    **输出:**

    ```
    x = 10
    ```

*   **Nullish coalescing & Equals (??=):** Symbol ?? is a nullish coalescing operator in JavaScript. It checks if a value is null or undefined.

    ```
    let x;
    let y = 10;
    x ??= y;
    console.log(x);
    console.log(y);
    ```

    **输出:**x 的值未定义，因此计算右侧表达式并将 x 设置为 10。

    ```
    10
    10
    ```

**2。数字分隔符:**为了提高可读性和分隔数字组，数字文字使用下划线作为分隔符。

```
// A billion dollar that I want to earn
const money = 1_000_000_000;

const money = 1_000_000_000.00;
```

它也可以用于二进制、十六进制、八进制。

**3。字符串**[**replace all()**](https://www.geeksforgeeks.org/javascript-string-replaceall-method/)**:**如果我们想替换字符串中一个子字符串的所有实例，那么这个新方法 **replaceAll()** 非常有用。

```
const s = "You are reading JavaScript 2021 new updates.";
console.log(s.replaceAll("JavaScript", "ECMAScript"));
```

**输出:**

```
You are reading ECMAScript 2021 new updates.
```

**4。promise . any:****promise . any()**方法返回一个承诺，一旦其中一个承诺被解决，该承诺就会被解决。它是**[**promise . all()**](https://www.geeksforgeeks.org/javascript-promise-all-method/)方法的反面，等待所有承诺解决后再解决。**

**当所有承诺都被拒绝时会发生什么，该方法会抛出一个带有拒绝原因的**聚合错误**异常。我们已经在 try-catch 块中编写了代码。**

```
const promiseOne = new Promise((resolve, reject) => {
  setTimeout(() => reject(), 1000);
});

const promiseTwo = new Promise((resolve, reject) => {
  setTimeout(() => reject(), 2000);
});

const promiseThree = new Promise((resolve, reject) => {
  setTimeout(() => reject(), 3000);
});

try {
  const first = await Promise.any([
    promiseOne, promiseTwo, promiseThree
  ]);
  // If any of the promises was satisfied.
} catch (error) {
  console.log(error);
  // AggregateError: If all promises were rejected
}
```

****输出:****

```
await is only valid in async functions and the top-level bodies of modules
```

****5。私有类方法:**私有方法只在类内有作用域，所以在类外是不可访问的。**

****上一版本:****

```
class GfG {
  showMe() {
    console.log("I am a geek")
  }
  #notShowMe() {
    console.log("Hidden informations")
  }
}

const gfg = new GfG()

gfg.showMe()
gfg.notShowMe() 
```

****输出:**错误如下。这是因为 **notShowMe()** 现在是 GfG 类内部的私有方法，只能通过类内部的公共方法访问。**

```
gfg.notShowMe is not a function
```

****新版本:****

```
class GfG {
  showMe() {
    console.log("I am a geek");
  }
  #notShowMe() {
    console.log("Hidden informations");
  }
  showAll() {
    this.showMe()
    this.#notShowMe();
  }
}

const gfg = new GfG();
gfg.showAll();
```

****输出:**我们在 GfG 类内部创建了一个名为 **showAll()** 的新公共方法。从这个公共方法中，我们可以访问私有方法 **#notShowMe()** ，由于我们的新方法是公共的，我们得到了以下结果。**

```
I am a geek
Hidden informations
```

****6。Private Getters 和 setter:**就像 private 方法一样，现在我们可以制作 getter 和 setter，这样它们只能在类内部或者通过创建的实例来访问。**

```
class GfG {
  get #Name() {
    return "GeeksforGeeks"
  }

  get viewName() {
    return this.#Name
  }
}

let name = new GfG();
console.log(name.viewName);
```

****输出:****

```
 GeeksforGeeks
```