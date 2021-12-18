# Python|Django

中具有自定义权限的用户组

> Original: [https://www.geeksforgeeks.org/python-user-groups-custom-permissions-django/](https://www.geeksforgeeks.org/python-user-groups-custom-permissions-django/)

让我们考虑一下旅行预订服务，它们是如何处理不同的计划和套餐的。 该公司提供了订阅者订阅不同套餐后可获得的产品列表。 一般来说，他们遵循的理念是不同产品的水平分销。

让我们看看旅游预订服务上提供的不同套餐：

1.  **入门计划**：在此套餐中，订阅者只可享受非空调巴士出行的便利，并只能在非空调房间停留一天。 假设这趟旅行是从德里到哈里德瓦尔(乌特特拉坎德邦的一个宗教场所)。
2.  **黄金计划**：它比启动计划要贵一些。 在这项计划中，订阅者将在非空调房间停留两天，乘坐空调巴士旅行，行程将从德里到哈里德瓦、里希凯什和穆索里。
3.  **钻石计划**：这是最昂贵的计划，订阅者将获得为期 3 天的计划，包括 AC 巴士和 AC 房间住宿，以及前往 Haridwar、Rishikesh 和 Mussoorie 的旅行，以及前往水上公园的旅行。

我们的主要目标是以非常高效的方式为后端设计和编写代码(遵循[DRY 原则](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself))。
在 Django 中有多种实现此功能的方法，但最合适、最有效的方法是将用户分组并定义这些组的权限。 该特定组的用户将自动继承该特定组的权限。 让我们先定义一下用户模型：

创建 Django 应用程序**个用户**。 在 Models.py 文件中的‘Users’应用程序目录下，编写以下代码。

## 蟒蛇 3

```
# importing necessary django classes
from django.contrib.auth.models import AbstractUser
from django.utils import timezone
from django.db import models

# User class
class User(AbstractUser):

    # Define the extra fields
    # related to User here
    first_name = models.CharField(_('First Name of User'),
                            blank = True, max_length = 20)

    last_name = models.CharField(_('Last Name of User'),
                            blank = True, max_length = 20)

# More User fields according to need

    # define the custom permissions
    # related to User.
    class Meta:

        permissions = (
            ("can_go_in_non_ac_bus", "To provide non-AC Bus facility"),
            ("can_go_in_ac_bus", "To provide AC-Bus facility"),
            ("can_stay_ac-room", "To provide staying at AC room"),
            ("can_stay_ac-room", "To provide staying at Non-AC room"),
            ("can_go_dehradoon", "Trip to Dehradoon"),
            ("can_go_mussoorie", "Trip to Mussoorie"),
            ("can_go_haridwaar", "Trip to Haridwaar"),
            ("can_go_rishikesh", "Trip to Rishikesh"),

# Add other custom permissions according to need.
```

迁移上面写的模型后，我们有两个选项来创建组。

1.  **Django 管理面板**：在管理面板中，您将看到**组**以粗体字母显示，单击该组并创建 3 个不同的组，分别命名为 Level 0、Level 1、Levvel3。 另外，根据需要定义自定义权限。
2.  **通过以编程方式创建具有权限**的组：使用 python manage.py shell 打开 python shell。

## 蟒蛇 3

```
# importing group class from django
from django.contrib.auth.models import Group, Permission
from django.contrib.contenttypes.models import ContentType

# import User model
from users.models import User

new_group, created = Group.objects.get_or_create(name ='new_group')

# Code to add permission to group
ct = ContentType.objects.get_for_model(User)

# If I want to add 'Can go Haridwar' permission to level0 ?
permission = Permission.objects.create(codename ='can_go_haridwar',
                                        name ='Can go to Haridwar',
                                                content_type = ct)
new_group.permissions.add(permission)
```

*
我们将以相同的方式为所有三个组设置不同的权限集。 在此之前，我们已经创建了组，并将其与自定义权限链接起来。

现在，检查特定用户是否正在访问适当的功能，例如，限制*Level 0*不能访问*Level 1 用户*或*Level 2 用户*的功能，依此类推。 要执行此操作，请检查所创建的每个视图函数的权限。
在这里非常小心，对于基于函数的视图，我们将简单地使用自定义装饰器。

**例如：**

## 蟒蛇，蚺蛇 / 巨蛇

```
@group_required('level0')
def my_view(request):
    ...
```

有关更多详细信息，请参阅[本](https://djangosnippets.org/snippets/10508/)。
当我们谈论基于类的视图时，事情变得有点复杂，我们不能简单地添加一个装饰器函数，而必须创建一个混合权限的类。

**例如：**

## 蟒蛇，蚺蛇 / 巨蛇

```
class GroupRequiredMixin(object):
    ...............
    ....Class Definition.....

class DemoView(GroupRequiredMixin, View):
  group_required = [u'admin', u'manager']

  # View code...
```

有关更多详细信息，请参阅[本](https://gist.github.com/ceolson01/206139a093b3617155a6)。

**References：**
1.[https：//docs.djangoproject.com/en/1.11/topics/class-based-views/mixins/](https://docs.djangoproject.com/en/1.11/topics/class-based-views/mixins/)
2.[http：//bradmontgomery.blogspot.in/2009/04/restricting-access-by-group-in-djangangangin。 Django-view-decorators.html](http://bradmontgomery.blogspot.in/2009/04/restricting-access-by-group-in-django.html)
4.[https：//micropyramid.com/blog/custom-decorators-to-check-user-roles-and-permissions-in-django/](https://micropyramid.com/blog/custom-decorators-to-check-user-roles-and-permissions-in-django/)