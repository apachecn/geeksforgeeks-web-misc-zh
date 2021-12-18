# 如何等待承诺完成后再返回函数的变量？

> 原文:[https://www . geeksforgeeks . org/如何在返回函数变量之前等待承诺完成/](https://www.geeksforgeeks.org/how-to-wait-for-a-promise-to-finish-before-returning-the-variable-of-a-function/)

在这里，promise 是从异步函数返回的对象，回调方法可以基于前一个函数的结果添加到该对象中。它是为像队列或函数链一样的函数的背靠背执行而完成的。所以当函数在队列中时，跟随它的函数必须等待前一个函数的结果。为此，有两种流行的方法描述如下。

*   **[使用 setTimeout()功能](https://www.geeksforgeeks.org/java-script-settimeout-setinterval-method/)**
*   **[使用异步或等待()功能](https://www.geeksforgeeks.org/async-await-function-in-javascript/)**

**setTimeout()函数的使用:**为了等待承诺完成后再返回变量，可以用 setTimeout()设置函数，让函数等待几毫秒。

下面程序将举例说明方法:
**程序:**

```
<script>
const wait=ms=>new Promise(resolve => setTimeout(resolve, ms));

function failureCallback(){
    console.log("This is failure callback");
}

wait(4*1000).then(() => {
    console.log("waited for 4 seconds");
    throw new Error("error occurred");
}).catch(() => {
    failureCallback();
});

wait(2*1000).then(() => console.log("waited for 2 seconds"));                    
</script>
```

**输出:**

```
waited for 2 seconds
waited for 4 seconds
This is failure callback

```

**使用异步或等待()函数:**如果无法指定 setTimeout()中所需的确切时间，可以使用该方法。async 关键字用于创建异步函数，该函数返回被拒绝或被解决的承诺。当从该函数中抛出一个未捕获的异常或以其他方式解决该异常时，承诺将被拒绝。在异步函数中使用 await 关键字来暂停其执行并等待承诺。

下面程序将说明方法:
**程序:**

```
<script>
//This function returns promise after 2 seconds
var first_function = function() {
console.log("Entered first function");
return new Promise(resolve => {
    setTimeout(function() {
    resolve("\t\t This is first promise");
    console.log("Returned first promise");
    }, 2000);
});
};
//This function executes returns promise after 4 seconds
var second_function = function() {
console.log("Entered second function");
return new Promise(resolve => {
    setTimeout(function() {
    resolve("\t\t This is second promise");
    console.log("Returned second promise");
    }, 4000);
});
};

var async_function = async function() {
console.log('async function called');

const first_promise= await first_function();
console.log("After awaiting for 2 seconds," +
"the promise returned from first function is:");
console.log(first_promise);

const second_promise= await second_function();
console.log("After awaiting for 4 seconds, the" + 
"promise returned from second function is:");
console.log(second_promise);
}

async_function();                 
</script>                    
```

**输出:**

```
async function called
Entered first function
Returned first promise
After awaiting for 2 seconds, the promise returned from first function is:
                 This is first promise
Entered second function
Returned second promise
After awaiting for 4 seconds, the promise returned from second function is:
                 This is second promise

```