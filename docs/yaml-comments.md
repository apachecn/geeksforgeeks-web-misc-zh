# YAML 点评

> 原文:[https://www.geeksforgeeks.org/yaml-comments/](https://www.geeksforgeeks.org/yaml-comments/)

![](img/207b8d0a19f96a98aae476273510ee9b.png)

YAML _ 评论

注释用于阻止语句的执行。编译器执行代码时，注释被忽略。注释是用户友好的，因为用户可以使用注释获得代码的解释。

既然你对 YAML 的句子结构和基本原理没问题，让我们继续深入它的细节。在这一部分，我们将了解如何利用评论在 YAML。注释被用来描述关于代码生命有意义的信息。

有两种注释。

1.  内嵌或单行注释
2.  块级注释

YAML 的语言结构支持内嵌注释，但不支持块级注释

**内联注释:**内联注释是在代码行中声明的注释，Hashtag 图像用于向行的开头告知处理器它是注释。

**示例:**

```
# remarks Punctuation model in YAML document  
or
#### #### comment model
```

这些只是确定为单行注释。每一行评论都以标签图像和空白开始，然后是描述。每行都以新的换行符结束。

**区块级注释:**方形注释用于注释各行。YAML 对阻止评论自然没有帮助，你可以利用大量的内嵌评论

```
# block level Comment model  
# Comment line 1  
# Comment line 2  
# Comment  line 3
```

**YAML 的重要注释:**注释被 YAML 处理器忽略。它有助于报告代码行，使设计人员的生活简单明了，有助于通过各种集成开发环境轻松路由订单

YAML 支持单行评论。它的结构在模型的帮助下被阐明

```
# This is single line comment.
```

**评论亮点:**YAML 评论亮点如下–

*   在代码执行过程中会跳过注释块。
*   注释有助于为确定的代码块添加描述。
*   注释不能出现在标量中。

YAML 确实排除了任何摆脱哈希图像(#)的方法，因此在多行字符串中，很难将注释与原始字符串区分开来。

**示例:**

```
#comment 1
- Value line 1

#comment 2
- value line 2

#comment 3
- value line 3
```

评论 YAML 区块的另一种组合键是 **Ctrl+Q** 。

**注:**类似的进步在机会渺茫时是合适的。正如大多数工作框架所坚持的那样，它经常被规定使用高级文字处理器来制作 **YAML** 文档，并结合了工程师邻近的简单路径键。