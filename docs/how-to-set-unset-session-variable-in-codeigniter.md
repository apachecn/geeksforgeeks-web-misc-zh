# 如何在 codeigniter 中设置&未设置会话变量？

> 原文:[https://www . geesforgeks . org/how-set-unset-session-变量 in-codeigniter/](https://www.geeksforgeeks.org/how-to-set-unset-session-variable-in-codeigniter/)

[CodeIgniter](https://www.geeksforgeeks.org/introduction-to-codeignitor-php/) 中的*会话*类允许用户在浏览网站时保持用户的“状态”并跟踪他们的活动。可以使用库初始化会话，并使用以下命令在环境中自动加载会话。

```
$this->load->library('session');
```

**设置会话变量:**可以使用键值对分配会话索引。可以使用赋值运算符将特定的键赋给一个值。该值可以是字符串、键，甚至是数组。

**语法:**

```
$_SESSION['key'] = value; 
```

**例 1:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?PHP  

  // Starting a new session
  session_start();

  $_SESSION['id'] = 9 ;

  // Check if the session name exists
  if( isset($_SESSION['id']) ) {
      echo 'Session id is '.$_SESSION['id'].'<br>';
  }
  else {
      echo 'Set the session id first '.'<br>';
  }
   echo'<br>';

  // Modifying the value of session
  $_SESSION['id'] = -8 ;
  echo 'New session id is '.$_SESSION['id'].'<br>';    
?>
```

**输出:**

```
Session id is 9
New session id is -8
```

也可以使用 CodeIgniter 中的 **set_userdata()** 方法分配会话值。此方法将一个键作为第一个参数，并将。接下来是要分配的值。

**语法:**

```
set_userdata ('key' , value)
```

还可以在 CodeIgniter 中的会话索引处添加多个键值对，如下面的代码片段所示。

**例 2:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php

  // Setting multiple key values
  $sess_arr = array('id'=>5, 'name' => 'yash');

  // Setting index at logged_in
  $this->session->set_userdata('logged_in', $sess_arr);

  // Printing the contents at this index
  print_r($_SESSION['logged_in']);
?>
```

**输出:**

```
Array ( [id] => 5 [name] => yash ) 
```

**取消设置会话变量:**可以通过将会话变量赋给空值来取消设置。这会破坏存储在该键值中的值。

**语法:**

```
$_SESSION['ey'] = NULL
```

**例 3:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php  

  // Starting a new session
  session_start();

  // Setting multiple values
  $sess_arr = array('id'=>5, 'name' => 'yash');

  $_SESSION['logged_in']= $sess_arr;
  echo ('Old session : ');
  print_r ($_SESSION['logged_in']);
  echo '</br>';

  // Unsetting the value
  $_SESSION['logged_in']= NULL;
  echo ('New session? : ');
  print_r ($_SESSION['logged_in']);
?>
```

**输出:**

```
Old session : Array ( [id] => 5 [name] => yash )
New session? :
```