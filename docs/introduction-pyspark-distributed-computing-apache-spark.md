# PySpark 简介|使用 Apache Spark 的分布式计算

> 原文:[https://www . geesforgeks . org/introduction-py spark-distributed-computing-Apache-spark/](https://www.geeksforgeeks.org/introduction-pyspark-distributed-computing-apache-spark/)

数据集变得越来越庞大。事实上，数据的增长速度超过了处理速度。因此，涉及大数据和高计算量的算法通常在分布式计算系统上运行。分布式计算系统包括并行运行进程并进行通信(如果需要)的节点(联网计算机)。

**MapReduce**–用于分布式计算的编程模型被称为 MapReduce。地图缩减模型包括两个阶段，地图和缩减。

1.  **映射**–映射器处理输入数据的每一行(以文件的形式)，并产生键值对。

    ```html
    Input data → Mapper → list([key, value])
    ```

2.  **减少**–减少器处理键值对列表(在映射器功能之后)。它输出一组新的键值对。

    ```html
    list([key, value]) → Reducer → list([key, list(values)])
    ```

**Spark**–Spark(Apache 开发的开源大数据处理引擎)是一个集群计算系统。与其他集群计算系统(如 Hadoop)相比，它更快。它提供了 Python、Scala 和 Java 中的高级 API。平行作业在 Spark 中很容易写。我们将介绍 PySpark (Python + Apache Spark)，因为这将使学习曲线更平坦。要在 linux 系统上安装 Spark，按照[这个](https://spark.apache.org/docs/0.9.0/python-programming-guide.html)进行操作。要在多集群系统中运行 Spark，请遵循[中的](https://www.pdf-archive.com/2017/06/10/settinguphdfsclusteron3nodes/settinguphdfsclusteron3nodes.pdf)。我们将看到如何创建 RDDs(Spark 的基本数据结构)。

**RDDs(弹性分布式数据集)**–RDDs 是不可变的对象集合。因为我们使用的是 PySpark，所以这些对象可以有多种类型。这些将变得更加清晰。

**SparkContext**–为了在 Spark 中创建独立的应用程序，我们首先定义一个 SparkContext–

```html
from pyspark import SparkConf, SparkContext
conf = SparkConf().setMaster("local").setAppName("Test")
# setMaster(local) - we are doing tasks on a single machine
sc = SparkContext(conf = conf)
```

**RDD 变换**–现在，创建了一个 SparkContext 对象。现在，我们将创建 rdd，并在上面看到一些转换。

```html
# create an RDD called lines from ‘file_name.txt’
lines = sc.textFile("file_name.txt", 2)

# print lines.collect() prints the whole RDD
print lines.collect()
```

使用 Spark 的一个主要优点是它不会将数据集加载到内存中，lines 是指向 **'file_name.txt'** '的指针？文件。

**一个简单的 PySpark 应用程序，用于计算给定图形的每个顶点的度数**–

```html
from pyspark import SparkConf, SparkContext
conf = SparkConf().setMaster("local").setAppName("Test")
# setMaster(local) - we are doing tasks on a single machine
sc = SparkContext(conf = conf)
def conv(line):
    line = line.split()
    return (int(line[0]), [int(line[1])])
def numNeighbours(x, y):
    return len(x) + len(y)
lines = sc.textFile('graph.txt')
edges = lines.map(lambda line: conv(line))
Adj_list = edges.reduceByKey(lambda x, y: numNeighbours(x, y))
print Adj_list.collect()
```

**了解以上代码**–

1.  我们的文本文件采用以下格式–(每行代表一个有向图的边)
    1 2
    1 3
    2 3
    3 4
    。。
    。。
    。。PySpark
2.  大型数据集可能包含数百万个节点和边。
3.  前几行设置了迷你图上下文。我们从中创建了一个 RDD **线条**。
4.  然后，我们将**线**从 RDD 变换到**边** RDD。conv 函数？表格(1，2)、(1，3)、(2，3)、(3，4)每一行的 cts 和键值对存储在**边** RDD 中。
5.  在此之后， **reduceByKey** 聚合对应于特定键的所有键对，**numneghbours**函数用于在单独的 RDD **Adj_list** 中生成每个顶点的度数，其形式为(1，2)、(2，1)、(3，1)……

**运行代码**–

1.  上述代码可以通过以下命令运行–

    ```html
    $ cd /home/arik/Downloads/spark-1.6.0/
    $ ./bin/spark-submit degree.py

    ```

2.  您可以在第一行使用您的 Spark 安装路径。

我们将看到更多关于如何使用 Spark 在机器集群中运行 MapReduce 任务的内容，以及其他 MapReduce 任务。

**参考文献**–

1.  [http://lintool . github . io/spark tutorial/](http://lintool.github.io/SparkTutorial/)
2.  [https://spark.apache.org/](https://spark.apache.org/)

本文由 **Arik Pamnani** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。