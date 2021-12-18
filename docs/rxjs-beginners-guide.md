# RxJs–初学者指南

> 原文:[https://www.geeksforgeeks.org/rxjs-beginners-guide/](https://www.geeksforgeeks.org/rxjs-beginners-guide/)

你有没有想过如何在只有 4GB 内存的设备上打开一个 10GB 的文件？或者说，只要你一按 play，网飞 app 就能在你的手机上播放云托管的 4K 电影？在具有 4GB 内存的设备上，10GB 的文件实际上是无限的。您的设备如何加载无限的东西？

它必须将文件以小块的形式加载到内存中，读取它们，并在将更多数据加载到内存之前丢弃它们。它必须流式传输数据，并以小块的形式进行处理。

## 什么是流？

该流是潜在无限的数据集合。这是一系列超时的数据。它可以被认为是传送带上一次处理一个项目。

```
Stream = Array + Infinity
```

由于数据可能是无限的，我们信任的循环不会对它们有效。您不能编写从零到无穷大的 for 循环来处理整个流。

## java 描述语言

```
for (let i = 0; i < infinite; i++) {
  const element = stream[i];
}
```

问题是我们如何知道何时停止它。这就是“可观察”进入画面的地方。

## 看得见的

Observables 可能是无限集合，一次异步返回值一个。即在返回的一个值和下一个值之间可能会经过一段时间。

```
Observable = Array + Infinity + Asynchronous
// OR
Observable = Promise + Returns many times
```

```
————— Value 1 ————— Value 2 ————— Value 3 ————— Value 4 —————|—>
```

在这方面，它们与**承诺**非常相似。承诺可以在一段时间后返回一个值。Observables 返回潜在的无限值，每个值之间会经过一段时间。

## java 描述语言

```
// Two states => resolve, reject
const promise = new Promise(resolve, reject);

promise
.then((data) => console.log("Data came back:" + data)) // Success
.catch((err) => console.error("No, Ew David", err)); // Error
```

承诺有两种可能的状态:解决、拒绝，或者换句话说:完成、错误。

## java 描述语言

```
const observable = from([1, 2, 3, 4]);

// Three states => next, complete, error
observable.subscribe({
  next: (value) => console.log("Next value:", value),
  complete: () => console.log("Infinity is Done!!! ¯\_(ツ)_/¯ "),
  error: (err) => console.log("No, Ew Binod", err),
});
```

Observables 为同一个概念增加了一个额外的状态:下一个，完成，错误。JavaScript 中最流行的可观察库之一是[rjs](https://rxjs.dev/guide/overview)。RxJS 令人敬畏的不仅仅是 Observables 的概念，还有大量的**运营商**。这些操作符可以对 Observables 采取行动，从而允许以声明方式轻松编写复杂的异步代码。

## RxJs 运算符

在 RxJS 中，运算符是接受一个可观测值作为输入，对其运行一些转换，并返回新的转换后的可观测值作为输出的函数。这些操作符(大部分)是纯的、无副作用的函数；也就是说，它们不会以任何方式改变即将到来的可观测值。这使得操作员可链接或可管道化；允许将应用程序中的异步逻辑分解成可管理的小块。

RxJs 将其操作符分为几类，但最常用的操作符是**创建操作符**和**转换操作符**。在本指南中，我们将探讨如何创建一个可观察的，如何转换，以及如何消费由可观察的数据发出。

### 创建运算符:of

这是从静态数据创建可观测值的最简单方法。这是一个易于使用的包装器，它接受任何数据序列作为输入，并返回一个随时可用的可观察值。这个操作符可以方便地启动一个全新的可观察管道。

## java 描述语言

```
of(10, 20, 30).subscribe(
  next => console.log('next:', next),
  err => console.log('error:', err),
  () => console.log('the end'),
);
```

**输出:**

```
'next: 10'
'next: 20'
'next: 30'
the end
```

### 创建运算符:从

该运算符类似于“of ”,但它适用于可迭代数据，即它接受数据集合并返回一个可观察值，该值一次发出集合中的每个值。这个运算符的真正力量来自于它也可以接受异步项，如生成器、承诺和其他可观察项。

## java 描述语言

```
from([10, 20, 30]).subscribe(
  next => console.log('next:', next),
  err => console.log('error:', err),
  () => console.log('the end'),
);

console.log('----------')

const promise = fetchDataFromServer();
from(promise).subscribe(
  next => console.log('next:', next),
  err => console.log('error:', err),
  () => console.log('the end'),
);
```

**输出:**

```
'next: 10'
'next: 20'
'next: 30'
the end
----------
'next: {msg: "Hello world!"}'
the end
```

### 转换运算符:映射

这个操作符和**数组#图很像。**它接受由可观察对象发出的每个新值，对其进行转换，并将其传递给管道中的下一个运算符。这就是《溪流与可观》的概念基础开始闪耀的地方。

当同样的问题可以用**数组#地图**解决时，为什么还要经历学习这个全新概念的麻烦呢？当我们无法将整个数据集加载到一个数组中时(即数据实际上是无限的)，观察值就变得非常有用。或者当我们没有整个数据集可供前期使用时。如中所示，数据集是异步的，新值通过网络缓慢传入。或者很多时候我们都有这两个问题的意思，实际上无限的数据通过网络慢慢地一次输入几个值。

## java 描述语言

```
// Another RxJS creation operator that
// starts at 0 and emits 1000 values
range(1, 1000)
.pipe(map(x => x * 10))
.subscribe(
  next => console.log('next:', next),
  err => console.log('error:', err),
  () => console.log('the end'),
);
```

**输出:**

```
'next: 10'
'next: 20'
'next: 30'
....
....
....
'next: 10000'
the end
```

RxJs 操作符几乎总是纯的/无副作用的，并且它们一次使用一个发出的值。这使得有效处理无限数据集变得非常容易。由于该功能没有副作用，系统不必保留当前未处理的项目。即每次只有一个项目保存在存储器中。

### 转换运算符:合并映射

该运算符与**映射**非常相似，但其转换函数返回异步数据(Observables 或 Promises)。这使得处理许多对服务器或数据库的异步调用变得非常容易，甚至允许我们将这些调用并行化。

## java 描述语言

```
range(1, 1000).pipe(mergeMap(pageNum =>
    fetchBulkDataFromServer({pageNum: pageNum})))
.pipe(map(bulkData=>`Page Num ${bulkData.page}
    retuned ${bulkData.items.length} items`))
.subscribe(
    next => console.log('next:', next),
    err => console.log('error:', err),
    () => console.log('the end'),
);
```

**输出:**

```
'next: Page Num 1 retuned 100 items'
'next: Page Num 2 retuned 90 items'
'next: Page Num 3 retuned 70 items'
'next: Page Num 4 retuned 100 items'
....
....
'next: Page Num 1000 retuned 30 items'
the end
```

当**合并映射**在异步数据(可观测值)上进行映射时，它通过并行映射多个可观测值显著加快了速度。它接受第二个参数“并发计数”，该参数定义了并行运行多少个可观测值。在不使用 Observables 的情况下实现这种级别的并行异步处理并不是一件简单的任务，并且很容易导致难以调试的并发错误。

## java 描述语言

```
const maxParallelApiCalls = 50;
range(1, 1000).pipe(mergeMap(pageNum =>
    fetchBulkDataFromServer({pageNum: pageNum}),
maxParallelApiCalls)).pipe(map(bulkData =>
    `Page Num ${bulkData.page} retuned
    ${bulkData.items.length} items`))
.subscribe(
    next => console.log('next:', next),
    err => console.log('error:', err),
    () => console.log('the end'),
);
```

**输出:**

```
'next: Page Num 7 retuned 10 items'
'next: Page Num 12 retuned 8 items'
'next: Page Num 38 retuned 12 items'
'next: Page Num 3 retuned 70 items'
....
....
'next: Page Num 1000 retuned 30 items'
the end
```

在上面的例子中，RxJs 同时开始处理 50 个可观测值，并按照它们完成的顺序发出这些可观测值返回的数据。因此，无论哪一个应用编程接口调用首先返回，它的数据都会被传送到下一个操作符。这是异步数据如何被**合并映射**并行化的时间线可视化。

```
<Start> — Value 1 —————————————————————————————————|—>
<Start> ————————————————————— Value 2 —————————————|—>
<Start> ——————————— Value 3 ———————————————————————|—>
<Start> —————————————————————————————— Value 4 ————|—>
<Start> —————————————————Value 5 ——————————————————|—>
——————————————————————— Merge ————————————————————————
<Start> — Value 1 —— Value 3 —— Value 5 —— Value 2 —— Value 4 —|—>
```

**结论:**上面的例子涵盖了本初学者指南中的几个 Operators，但是 RxJS 还有很多，适用于各种各样的用例。查看[他们的文档](https://rxjs.dev/api)了解更多信息。

**参考:** [https://rxjs.dev/api](https://rxjs.dev/api)