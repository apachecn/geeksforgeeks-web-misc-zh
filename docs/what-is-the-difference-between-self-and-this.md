# 自我和$这个有什么区别？

> 原文:[https://www . geesforgeks . org/自我和这个的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-self-and-this/)

关键字 **self** 仅用于指代该类范围内的当前类本身，而 **$this** 用于指代特定类实例的成员变量和函数。

**self 运算符:** self 运算符代表当前类，因此用于访问类变量或静态变量，因为这些成员属于某个类，而不是该类的对象。
**语法:**

```html
self::$static_member
```

**$this 运算符:** $this，作为“{ content }”；暗号暗示，是一个物体。$这表示类的当前对象。它用于访问类的非静态成员。
**语法:**

```html
$that->$non_static_member;
```

[**在 PHP 中何时使用 self over $ this**](https://www.geeksforgeeks.org/when-to-use-self-over-this-in-php/):

**例:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
    class StudentDetail{

        public $name;
        public static $age;

        public function getName() {
            return $this->name;
        }

        public static function getAge() {
            return self::$age;
        }

        public function getStudentAge() {
            return self::getAge();
        }
    }

    $obj = new StudentDetail();

    $obj->name = "GFG";

    StudentDetail::$age = "18";

    echo "Name : " .$obj->getName()."\xA";
    echo "Age  : " .StudentDetail::getStudentAge();

?>
```

**Output**

```html
Name : GFG
Age  : 18
```

**self 与$本的区别:**

<figure class="table">

| ***self*** | ***$本*** |
| *自我*键台切第 8 号什么事符号〔T2〕〔T3〕 | *When referring to class members, this* keyword should be preceded by a **$** symbol. |
| In order to access class variables and methods, a range resolution operator is used. | In order to access class variables and methods, the arrow operator (->) is used. |
| [T0】 self 【T1] keyword is used to access the static members of the class existing in the program. | $ This is a non-static member used to access the classes that exist in the program. |
| The [T0】 Self 【T1] keyword refers to a class member, but does not point to any specific object of the class. | *$ This* can refer to the member variables and functions of a selected instance of the class. |

</figure>