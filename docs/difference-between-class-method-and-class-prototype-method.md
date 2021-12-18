# 类方法和类原型方法的区别

> 原文:[https://www . geesforgeks . org/类-方法和类-原型-方法的区别/](https://www.geeksforgeeks.org/difference-between-class-method-and-class-prototype-method/)

JavaScript 是一种面向对象的编程语言，但与同类语言(基于类)不同，JavaScript 是一种基于原型的语言。这意味着在 JavaScript 中，您可以创建一个对象(原型对象)，作为新对象的模板。这些新对象可以在创建时或运行时提供新属性。

有两种方法可以向对象添加新方法。

1.  **类方法:****类方法**是静态的，与类的任何实例都没有关系。必须使用类名调用类方法。内存中只存在该函数的一个实例。

    **示例:**

    ## java 描述语言

    ```html
    <script>

       // Constructor function
       function User(userName) {
         this.userName = userName;
       };

       // Static function 
       User.message = function () {
         document.write("Login successful");
       };

       // Creating an instance of User
       // using new keyword
       const newUser = new User("GFG");

       // Message method accessed with User
       User.message(); 
    </script>
    ```

    **Output:**

    ```html
    Login successful
    ```

2.  **类.原型.方法:**创建与对象实例相关的**类.原型.方法**。它是使用对象实例名调用的。类的每个实例都有自己的这个方法的副本。

    **示例:**

    ## java 描述语言

    ```html
    <script>
       function User(userName) {
          this.userName = userName;
        };

        User.message = function () {
          document.write("Login successful");
          document.write("<br>");
        };

        // Instance method 
        User.prototype.greet = function () {

           // can access object properties
           // using 'this' keyword
           document.write("Welcome " + this.userName); 
        };

        const newUser = new User("GFG");
        User.message();

        // Instance method being accessed 
        // using instance variable
        newUser.greet(); 
    </script>
    ```

    **Output:**

    ```html
    Login successful
    Welcome GFG 
    ```

    上面的代码可以使用 ECMAScript 2015 中引入的 JavaScript 类来编写。

    ## java 描述语言

    ```html

    <script>

        // JavaScript class  
        class User {
            constructor(userName) {
                this.userName = userName;
            }

            // Corresponds to User.message()
            static message = function () {
                document.write("Login successful");
                document.write("<br>");
            };

            // Corresponds to User.prototype.greet()
            greet = function () {
                document.write("Welcome " 
                        + this.userName);
            };
        }

        const newUser = new User("GFG");
        User.message();
        newUser.greet();
    </script>
    ```

    **Output:**

    ```html
    Login successful
    Welcome GFG 
    ```

    JavaScript 类在语法上比 JavaScript 基于原型的方法更好。