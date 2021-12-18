# 如何在 Codeigniter 中设置或获取配置变量？

> 原文:[https://www . geesforgeks . org/如何在 codeigniter 中设置或获取配置变量/](https://www.geeksforgeeks.org/how-to-set-or-get-the-config-variables-in-codeigniter/)

**配置类:**配置类提供了检索配置首选项的方法。 [Codeigniter](https://www.geeksforgeeks.org/introduction-to-codeignitor-php/) 中的配置项可以设置并进入环境。配置值 *$this- >配置*可用于获取和设置环境中的项目。配置项包含在一个数组中，即 *$config* 。配置文件存储在*“application/config/config . PHP”*中，这可能会提供添加新项目或创建单独的配置项目实体的机会。

默认情况下，CodeIgniter 加载主配置文件(*application/config/config . PHP*)，而自定义文件需要从外部加载。

**设置配置变量值:**可以使用以下两种方法在环境中设置 CodeIgniter 中的配置变量。配置类方法 **set_item()** 用于设置 Codeigniter 中变量的值。 **set_item()** 可用于动态设置配置项或修改现有配置项。

**语法:**

```html
$this->config->set_item('item_name', 'item_value');
```

**论据:**

*   **项目名称:**$要更改的配置数组项目名称。
*   **项目 _ 值:**要更改的值。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
  // Setting the value of config variable
  $this->config->set_item('str', "Hello GFG!");
  echo($this->config->item('str'));
?>
```

**输出:**

```html
[1] "Hello GFG!"
```

还可以使用 *$config* 变量中定义的键值对来修改或初始化配置项。还可以使用 CodeIgniter 中的键值对来设置配置变量的项值。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
  $config['str'] = "Hello GFG!";
  echo($this->config->item('str'));
?>
```

**输出:**

```html
[1] "Hello GFG!"
```

**获取配置变量值:**配置项也可以很容易地从 CodeIgniter 环境中获取。配置类函数 **item()** 用于获取 Codeigniter 中配置变量的值。

**语法:**

```html
$this->config->item('item_name');
```

**论据:**

*   **item _ name:**$要检索的配置数组索引。

**返回值:**该函数返回指定数组索引键的值，如果不存在这样的键，则返回空值。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```html
<?php
  // Getting the value of config variable
  $this->config->item('str');
?>
```

**输出:**

```html
[1] "Hello GFG!"
```