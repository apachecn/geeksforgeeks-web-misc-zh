# 弹性搜索|查询和过滤器的区别

> 原文:[https://www . geeksforgeeks . org/elastic search-查询和筛选器之间的差异/](https://www.geeksforgeeks.org/elasticsearch-differences-between-queries-and-filters/)

[**Elasticsearch**](https://www.geeksforgeeks.org/elasticsearch-search-engine-an-introduction/) 是基于 Apache Lucene 的全文搜索和分析引擎。Elasticsearch 使对来自多个来源的数据执行数据聚合操作以及对存储的数据执行非结构化查询(如模糊搜索)变得更加容易。

**弹性搜索文档看起来像:**

```
{
  "first_name": " Kumar",
  "last_name":"Gaurav",
  "email":"kumar@gmail.com",
  "dob":"04-11-1995",
  "country":"India"
}
```

在版本 2 之前，弹性搜索分别执行查询和过滤，之后它们将两者结合起来，产生更有效的搜索结果。因此，首先我们讨论这两个主题，然后，我们将它们相互比较。

**查询:**查询计算每个文档与查询的相关性，并为其分配相关性分数，该分数随后用于按相关性对匹配的文档进行排序。这种相关性的概念非常适合全文搜索，在全文搜索中很少有完全“正确”的答案。该查询还会提出如下问题:

*   这份文件的匹配程度如何？
*   弹性搜索的创建日期是什么？
*   lat_lon 场到指定点的距离是多少？

查询的典型用途是查找与全文搜索最匹配的文档，包含单词 run，但也可能匹配 run、running、jog 或 sprint，包含单词 quick、brown 等。

**过滤器:**大多数过滤器子句的输出是与过滤器匹配的文档的简单列表。它计算速度快，易于在内存中缓存，每个文档仅使用 1 位。这些缓存的过滤器可以为后续请求有效地重用。过滤器会询问每个文档的是或否问题，并用于包含精确值的字段:

*   创建日期是否在 2013–2014 年范围内？
*   状态字段是否包含术语“已发布”？
*   lat_lon 场是否在指定点的 10 公里范围内？

**注:**查询子句和过滤子句性质相似，但用途略有不同。

**要点:**查询不仅仅是查找匹配的文档，还要计算每个文档的相关程度，这通常会让查询比过滤器更重。此外，查询结果不可缓存。得益于倒排索引，一个只匹配几个文档的简单查询可能比跨越数百万个文档的缓存过滤器表现得更好。但是，一般来说，缓存过滤器的性能会优于查询，并且会始终如一。过滤器的目标是减少查询必须检查的文档数量

**查询和过滤器的区别:**

<figure class="table">

| query | filter |
|  |  |
| The query speed is slow, and it returns the calculated score of how well the document matches the query. | Filters are faster because they only check whether documents match. |
| The query produces a non-boolean value. | The filter generates a Boolean value. |
| Using filters after executing queries is faster than other queries. | However, it is not worthwhile to use the filtered query. |
| The query is not cacheable. | Filters can be cached. |

</figure>

**注意:**版本 2 的 Query 和 filter 合并后表现更好的结果，运行一个查询然后设置一个 Filter 会帮助你得到你想要的实际结果。