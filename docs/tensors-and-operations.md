# 张量和运算

> 原文:[https://www.geeksforgeeks.org/tensors-and-operations/](https://www.geeksforgeeks.org/tensors-and-operations/)

在这篇文章中，我们将讨论张量及其运算。

**简介:** TensorFlow.js 是一个用 JavaScript 中的张量定义和运行计算的库。张量是向量和矩阵向更高维度的推广。

**张量:**张量流. js 中数据的中心单位是 **tf。张量**–一组形成一维或多维数组的值。 **tf。张量**与多维数组非常相似。

一 **tf。张量**还包含以下属性:

*   **秩:**定义张量包含多少维。
*   **形状:**定义数据每个维度的大小。
*   **数据类型:**定义张量的数据类型。

**注:**我们将“维度”一词与等级互换使用。有时在机器学习中，
张量的“维数”也可以指特定维数的大小(例如，形状矩阵[10，5]是秩为 2 的张量或二维张量)。第一维的维数是 10。这可能会令人困惑，但我们在这里放这个注释，因为您可能会遇到这个术语的双重用途)。

一 **tf。张量**可以用 **tf 从数组中创建。张量()**方法。

## Java Script 语言

```html
// Create a rank-2 tensor (matrix) matrix
// tensor from a multidimensional array
const a = tf.tensor([[1,2], [3,4]]);
console.log('shape:', a.shape);
a.print();

// Or you can create a tensor from a
// flat array and specify a shape.
const shape = [2, 2];
const b = tf.tensor([1,2,3,4], shape);
console.log('shape:', b.shape);
b.print();
```

**输出:**

```html

shape: 2,2
Tensor
    [[1, 2],
     [3, 4]]
shape: 2,2
Tensor
    [[1, 2],
     [3, 4]]
```

默认情况下， **tf。张量**将有一个**浮动 32**T4】数据类型。 **tf。张量**也可以用 bool、int32、complex64 创建，并使用数据类型:

## Java Script 语言

```html
const a = tf.tensor([[1,2], [3,4]], [2,2], 'int32');
console.log('shape:', a.shape);
console.log('dtype', a.dtype);
a.print();
```

**输出:**

```html
shape: 2, 2
dtype int32
Tensor
    [[1, 2],
     [3, 4]]
```

TensorFlow.js 还提供了一套方便的方法来创建随机张量、用特定值填充的张量、来自 **HTMLImageElement** s 的张量等等。

**改变张量的形状:**一个 **tf 中的元素数。张量**是其形状中尺寸的乘积。因为经常会有多个相同大小的形状，所以能够重塑一个 **tf 通常是有用的。张量**到另一个同样大小的形状。这可以通过**重塑()**方法来实现。

## Java Script 语言

```html
const a = tf.tensor([[1,2], [3,4]]);
console.log('a shape:', a.shape);
a.print();
const b = a.redshape([4,1]);
console.log('b shape:', b.shape);
b.print();
```

**输出:**

```html
a=array([1, 2, 3, 4])
```

**从张量中获取值:**你也可以从 **tf 中获取值。张量**使用 th **e 张量数组()**或**张量数据()**方法:

## Java Script 语言

```html
const a = tf.tensor([[1,2], [3,4]]);

// Returns the multi-dimensional array of values
a.array().then(array => console.log(array));

// Returns the flattened data that backs the tensor
a.data().then(data => console.log(data));
```

**输出:**

```html
Tensor 
    [1, 2, 3, 4]
```

我们还提供了这种方法的同步版本，使用起来更简单，但会在应用程序中引起性能问题。您应该总是更喜欢生产应用程序中的同步方法。

## Java Script 语言

```html
const a = tf.tensor([[1,2],[3,4]]);

// Returns the multi dimensional array of values
console.log(a.arraySync());

// Returns the flattened data that backs the tensor
console.log(a.dataSync());
```

**输出:**

```html
a = [1, 2, 3, 4]
```

**操作:**虽然张量允许你存储数据，但操作(ops)允许你操作这些数据。TensorFlow.js 提供了多种适用于线性代数和机器学习的操作，可以在 tensors 上执行。

**示例:**计算 **tf 中 al 元素的 x^2。张量:**

## Java Script 语言

```html
const x = tf.tensor([1,2,3,4]);

// Equivalent to tf.square(x)
const y = x.square();  
y.print();
```

```html
Output for the above code:
y=x([1, 4, 9, 16 ] )
```

**例:**添加两个 **tf 的元素。张量**元素方式:

## Java Script 语言

```html
const a = tf.tensor([1,2,3,4]);
const b = tf.tensor([10,20,30,40]);

// Equivalent to tf.add(a,b)
const y = a.add(b);
y.print();
```

**输出:**

```html
numpy = array([ 11, 22, 33, 44 ])
```

因为张量是不可变的，所以这些运算不会改变它们的值。相反，操作返回总是返回新的 **tf。张量** s。

**内存:**使用 WebGL 后端时， **tf。Tensor** 内存必须明确管理(让一个 **tf.tensor** 超出其要释放的内存范围是不够的**)。**

**摧毁 tf 的记忆。张量，可以使用 **dispose()** 方法或者 **tf.dispose()** :**

**在应用程序中将操作链接在一起是非常常见的。持有对所有中间变量的引用来处理它们会降低代码的可读性。为了解决这个问题，TensorFlow.js 提供了一个 **tf.tidy()** 的方法，清理所有 **tf。张量**是函数执行后不返回的，类似于函数执行时清理局部变量的方式:**

## **Java Script 语言**

```html
const a = tf.tensor([[1,2],[3,4]]);
const y = tf.tidy(() => {
const result = a.square().log().neg();
return result;
});
```

****输出:****

> **在本例中，将自动处理 square()和 log()的结果。neg()的结果不会被公开，因为它是 tf.tidy()的返回值。**

**您还可以获得 TensorFlow.js 跟踪的 Tensors 数量:**

## **Java Script 语言**

```html
console.log(tf.memory());
```

****输出:****

```html
It will display a message on the console while debugging.
e.g 
console.log("Hello World");
Now if we run this using --   node helloworld.js
It will print---   Hello World
```

**由 **tf.memory()** 打印的对象将包含当前分配了多少内存的信息。**