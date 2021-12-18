# Python|Django 模型中的关系字段

> Original: [https://www.geeksforgeeks.org/python-relational-fields-in-django-models/](https://www.geeksforgeeks.org/python-relational-fields-in-django-models/)

Prerequisite: [Django models](https://www.geeksforgeeks.org/django-models-set-1/)

Django 模型代表真实世界的实体，真实世界的实体彼此完全独立的情况很少发生。 因此，Django 支持关系数据库，并允许我们在不同模型之间建立关系。 Django 支持三种类型的关系字段：多对一、多对多和一对一。

## 多对一字段：

当模型 A 的一个记录与另一个模型 B 的多个记录相关时使用。例如，模型**歌曲**与模型**专辑**具有多对一关系，即一个专辑可以有多首歌曲，但一首歌曲不能是多张专辑的一部分。 多对一关系是使用**`django.db.models`**的**`ForeignKey`**字段定义的。

下面的示例演示了这一点。

```
from django.db import models

class Album(models.Model):
    title = models.CharField(max_length = 100)
    artist = models.CharField(max_length = 100)

class Song(models.Model):
    title = models.CharField(max_length = 100)
    album = models.ForeignKey(Album, on_delete = models.CASCADE)
```

使用与相关模型相同的名称(小写)来命名多对一字段是一种很好的做法。

## 多对多字段：

当模型 A 的一条记录与另一模型 B 的多条记录相关时使用此选项，反之亦然。 例如，模型**图书**与模型**作者**具有多对多关系，即一本书可以由多位作者编写，而一位作者可以编写多本书。 多对多关系是使用**`django.db.models`**的**`ManyToManyField`**字段定义的。

下面的示例演示了这一点。

```
from django.db import models

class Author(models.Model):
    name = models.CharField(max_length = 100)
    desc = models.TextField(max_length = 300)

class Book(models.Model):
    title = models.CharField(max_length = 100)
    desc = models.TextField(max_length = 300)
    authors = models.ManyToManyField(Author)
```

使用相关模型的复数版本(小写)来命名多对多字段是一种很好的做法。 这两个模型中哪一个包含多对多字段并不重要，但它不应该同时放在两个模型中。

## 一对一字段：

当模型 A 的一条记录恰好与另一模型 B 的一条记录相关时，可以使用该字段作为对象的主键(如果该对象以某种方式扩展了另一个对象)。 例如，模型**汽车**与模型**车辆**具有一对一的关系，即汽车就是车辆。 使用**`django.db.models`**的**`OneToOneField`**字段定义一对一关系。

下面的示例演示了这一点。

```
from django.db import models

class Vehicle(models.Model):
    reg_no = models.IntegerField()
    owner = models.CharField(max_length = 100)

class Car(models.Model):
    vehicle = models.OneToOneField(Vehicle, 
          on_delete = models.CASCADE, primary_key = True)
    car_model = models.CharField(max_length = 100)
```

最好将一对一字段命名为与相关模型的名称相同的小写名称。

## 数据完整性选项：

由于我们正在创建依赖于其他模型的模型，因此我们需要定义一个模型中的记录在删除另一个模型中的相应记录时的行为。 这是通过在关系字段中添加可选的**`on_delete`**参数来实现的，该参数可以采用下列值：

*   **`on_delete = models.CASCADE`**-这是默认值。 当一张唱片被删除时，它会自动删除所有相关的记录。(例如，当一张专辑记录被删除时，与之相关的所有歌曲记录都会被删除)
*   **`on_delete = models.PROTECT`**-它阻止删除与其他记录有关系的记录。(例如，任何删除专辑记录的尝试都将被阻止)
*   **`on_delete = models.SET_NULL`**-如果设置了**`null = True`**，则在删除记录时将 NULL 赋给关系字段。
*   **`on_delete = models.SET_DEFAULT`**-当删除记录时，它会将默认值分配给关系字段，因此必须提供默认值。
*   **`on_delete = models.SET()`**-它可以采用默认值作为参数，也可以采用返回值将赋给该字段的可调用参数。
*   **`on_delete = models.DO_NOTHING`**-不执行任何操作。 使用此值是一种糟糕的做法。