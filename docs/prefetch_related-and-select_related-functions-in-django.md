# Django

中的 Prefetch_Related 和 SELECT_Related 函数

> Original: [https://www.geeksforgeeks.org/prefetch_related-and-select_related-functions-in-django/](https://www.geeksforgeeks.org/prefetch_related-and-select_related-functions-in-django/)

在 Django 中，SELECT_RELATED 和 PREFETCH_RELATED 旨在阻止因访问相关对象而导致的数据库查询泛滥。在本文中，我们将了解它如何减少查询数量，并使程序运行更快。

*   **SELECT_REGRECTED ()** "follows" the foreign key relationship, selecting additional related object data when executing the query.
*   **PREFETCH_Related ()** performs a separate lookup for each relationship and performs a "join" in Python.

当要选择的对象是单个对象时，可以使用 SELECT_Related，即 OneToOneField 或 ForeignKey。 当您要获取一组对象时，可以使用 PREFETCH_REGRECTED，因此 ManyToManyFields 如您所述，或者反转 ForeignKey。 只是想澄清一下我所说的“反向外键”是什么意思。

**举例说明 Prefetch_Related 和 SELECT_Related-**的概念

上面的分类可能不太清楚，让我们看一个例子：

```html
class A(models.Model):
   pass

class B(models.Model):
   a = ForeignKey(ModelA)

# Forward ForeignKey relationship
A.objects.select_related('a').all()

# Reverse ForeignKey relationship
A.objects.prefetch_related('modelb_set').all() 
```

SELECT_Related 通过多表连接关联查询一次获取所有数据，并通过减少数据库查询次数来提高性能。 它利用 SQL 的 JOIN 语句，通过减少 SQL 查询次数来优化和提高性能，后者是通过 JOIN 语句来解决 SQL 查询中的问题。 但是，对于多对多关系，用 SQL 语句来解决并不明智，因为 JOIN 得到的表会很长，这会增加 SQL 语句的运行时间和内存占用。 PREFETCH_Related()的解决方案是分别查询每个表，然后使用 Python 处理它们之间的关系！

下面是一些示例：

`Models.py reads as follows:`

```html
from django.db import models

class Province(models.Model):
   name = models.CharField(max_length = 10)
   def __unicode__(self):
       return self.name

class City(models.Model):
   name = models.CharField(max_length = 5)
   province = models.ForeignKey(Province)
   def __unicode__(self):
       return self.name

class Person(models.Model):
   firstname = models.CharField(max_length = 10)
   lastname = models.CharField(max_length = 10)
   visitation = models.ManyToManyField(City, related_name = "visitor")
   hometown = models.ForeignKey(City, related_name = "birth")
   living = models.ForeignKey(City, related_name = "citizen")
   def __unicode__(self):
       return self.firstname + self.lastname
```

**select_Related-**

如果我们使用 select_Related()函数：

```html
>>> citys = City.objects.select_related().all()
>>> for c in citys:
...   print c.province
...
```

只有一个 SQL 查询， 这明显减少了 SQL 查询的数量：

```html
SELECT `Optimize_city`.`id`, `Optimize_city`.`name`,
`Optimize_city`.`province_id`, `Optimize_province`.`id`, `Optimize_province`.`name`
FROM`Optimize_city`
INNER JOIN `Optimize_province` ON
(`Optimize_city`.`province_id`=`Optimize_province`.`id`);
```

**PREFETCH_REGRECTED-**

这里我们可以看到 Django 使用了 INTER JOIN。 我想澄清的一件事是，优化是我们应用程序的一个名称。 如果我们想获取湖北的所有城市名称，可以这样做：

```html
> HB=Province.objects.prefetch_related('city_set').get(name__iexact=u"Hubei Province")
>>> for city in hb.city_set.all():
...   city.name
...
```

触发的 SQL 查询：

```html
SELECT `Optimize_province`.`id`, `Optimize_province`.`name`
FROM `Optimize_province`
WHERE `Optimize_province', `name `LIKE'Hubei Province';

SELECT `Optimize_city`.`id`, `Optimize_city`.`name`, `Optimize_city`.`province_id`
FROM `Optimize_city`
WHERE `Optimize_city`.`province_id` IN (1);
```

正如我们看到的，预取是使用 IN 语句实现的。 这样，当 QuerySet 中有太多对象时，根据数据库的特性可能会出现性能问题。