# 如何检查以某个给定字符/模式开头的字符串？

> 原文:[https://www . geesforgeks . org/如何检查以给定字符开头的字符串模式/](https://www.geeksforgeeks.org/how-to-check-a-string-begins-with-some-given-characters-pattern/)

我们可以通过 javascript 中的各种方法检查给定的字符串是否以指定字符串的字符开头，如下所述:

**方法 1:** 这是一个简单的方法，从使用循环开始，我们将逐个匹配字符，如果有任何字符不匹配，那么我们可以说字符串不是以字符或指定的字符串开头。

**语法:**

```
for (var i = 0; i < pattern.length; i++) {
        if(str.charAt(i) != pattern.charAt(i)){
            result = false;
            break;
        }
      }
```

**示例:**下面的程序演示了上述方法:

```
<script>
    // Javascript script to check 
    // whether the String begins
    // with something or not

    // Function to check String
    // begins with something or not
    function check(str, pattern){
      // Initially we assume that String
      // begins with something
      // so result is true
      var result = true;

      // Loop to match character by character
      for (var i = 0; i < pattern.length; i++) {

        // If any character doesn't matches 
        // then result is false
        if(str.charAt(i) != pattern.charAt(i)){
            result = false;
            break;
        }
      }

      if(result){
        document.write("String begins with \""
                + pattern + "\"<br><br>");
        }
      else{
        document.write("String  doesn't " + 
            "begins with \"" + pattern + "\"<br><br>");
        }
    }

    // Driver code
    // String to check
    var str = "GeeksforGeeks";

    // Pattern by which string 
    // begins or not
    var pattern = "Geeks";

    document.write("String = \"" + str + "\"<br>");
    document.write("String should begin with  = \""
            + pattern + "\"<br>");

    // Call check function
    check(str, pattern);

    // Change string
    str = "geeksforgeeks";

   document.write("String = \"" + str + "\"<br>");
    document.write("String should begin with  = \""
            + pattern + "\"<br>");

    // Calling check function
    check(str, pattern);
</script>                    
```

**输出:**

```
String = "GeeksforGeeks"
String should begin with = "Geeks"
String begins with "Geeks"

String = "geeksforgeeks"
String should begin with = "Geeks"
String doesn't begins with "Geeks"

```

**方法二:**在该方法中，我们将使用 [substring()](https://www.geeksforgeeks.org/javascript-string-substring/) 函数获取模式串所需长度的子串，然后使用 [localeCompare()](https://www.geeksforgeeks.org/javascript-string-localecompare/) 函数将子串与模式进行匹配。

**语法:**

```
var = string.substring(Startindex, Endindex)
var.localeCompare(compareString)

```

**示例:**下面的程序演示了上述方法:

```
<script>
    // Javascript script to check 
    // whether the String begins
    // with something or not

    // Function to check String
    // begins with something or not
    function check(str, pattern){
      // Extracting substring of
      // pattern length
      var sub_str = 
            str.substring(0, pattern.length);

      if(sub_str.localeCompare(pattern) == 0){
        document.write("String begins with \""
                + pattern + "\"<br><br>");
        }
      else{
        document.write("String  doesn't " + 
            "begins with \"" + pattern + "\"<br><br>");
        }
    }

    // Driver code
    // String to check
    var str = "GeeksforGeeks";

    // Pattern by which string 
    // begins or not
    var pattern = "Geeks";

    document.write("String = \"" + str + "\"<br>");
    document.write("String should begin with  = \""
            + pattern + "\"<br>");

    // Call check function
    check(str, pattern);

    // Change string
    str = "geeksforgeeks";

   document.write("String = \"" + str + "\"<br>");
    document.write("String should begin with  = \""
            + pattern + "\"<br>");

    // Calling check function
    check(str, pattern);
</script>                    
```

**输出:**

```
String = "GeeksforGeeks"
String should begin with = "Geeks"
String begins with "Geeks"

String = "geeksforgeeks"
String should begin with = "Geeks"
String doesn't begins with "Geeks"

```

**方法 3:** 这首先是最好的解决方案，在这个方法中我们将使用 [startsWith()](https://www.geeksforgeeks.org/javascript-string-startswith/) 方法直接检查给定的字符串是否以某个东西开始。

**语法:**

```
str.startsWith( searchString , position )

```

**示例:**下面的程序演示了上述方法:

```
<script>
    // Javascript script to check 
    // whether the String begins
    // with something or not

    // Function to check String
    // begins with something or not
    function check(str, pattern){

      if(str.startsWith(pattern)){
        document.write("String begins with \""
                + pattern + "\"<br><br>");
        }
      else{
        document.write("String  doesn't " + 
            "begins with \"" + pattern + "\"<br><br>");
        }
    }

    // Driver code
    // String to check
    var str = "Burn to shine";

    // Pattern by which string 
    // begins or not
    var pattern = "Burn";

    document.write("String = \"" + str + "\"<br>");
    document.write("String should begin with  = \""
            + pattern + "\"<br>");

    // Call check function
    check(str, pattern);

    // Change string
    str = "Happy coding";
    // Change pattern
    pattern = "happy";

   document.write("String = \"" + str + "\"<br>");
    document.write("String should begin with  = \""
            + pattern + "\"<br>");

    // Calling check function
    check(str, pattern);
</script>                    
```

**输出:**

```
String = "Burn to shine"
String should begin with = "Burn"
String begins with "Burn"

String = "Happy coding"
String should begin with = "happy"
String doesn't begins with "happy"

```