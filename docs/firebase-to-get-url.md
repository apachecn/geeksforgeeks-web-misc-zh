# Firebase 获取网址

> 原文:[https://www.geeksforgeeks.org/firebase-to-get-url/](https://www.geeksforgeeks.org/firebase-to-get-url/)

什么是 Firebase？

Firebase 是一个平台，它允许你在没有服务器端编程语言的情况下构建 web 和移动应用程序。它将用户数据存储在其实时数据库中，该数据库在用户之间实时同步数据。它是谷歌的产品，为我们提供了多种功能。Firebase 的一些关键特性包括:

*   Firebase 宿主
*   实时数据库
*   Firebase 分析
*   云消息
*   火炉储存
*   通知等。

所有这些特性使 firebase 成为一个好工具，尽管 firebase 最广泛使用的特性肯定是它提供的实时数据库。Firebase 实时数据库基本上是一个云托管的 NoSQL 数据库，允许您在用户之间实时存储和同步。数据库只是开发人员可以实时管理的一个大的 JSON 对象。实时同步使用户可以轻松地从任何设备访问数据，无论是网络设备还是移动设备。

获取图像 URL

Firebase 可用于各种用途，但主要用于实时数据库、在线处理。Firebase 云存储是开发人员使用最多的功能。**云存储**允许开发人员快速轻松地将文件上传到 Firebase 提供和管理的谷歌云存储桶中。

**图片网址**是通过上传一张图片到 firebase bucket，然后可以返回一个网址，这个网址是一个永久的网址，可以在任何地方打开。然后，用户可以在其应用程序中出于任何目的使用该网址。

在 firebase 中生成一个 **Bucket** ，然后创建一个文件夹“images”(或任何文件夹名)，然后从 firebase 访问配置文件，这个文件在您生成数据库 Bucket 时生成。

### 配置代码如下所示:

```html
var config = {
    apiKey: "YOUR KEY",
    authDomain: "YOUR DOMAIN",
    databaseURL: "DATA BASE URL",
    projectId: "postweb-b3f18",
    storageBucket: "BUCKET",
    messagingSenderId: "157746640407"
  };

```

**在添加以上配置代码**
之前，添加以下脚本标签

```html
<script src="https://www.gstatic.com/firebasejs/5.0.4/firebase.js"></script>
```

**初始化你的 FireBase 云存储**

```html
firebase.initializeApp(config);
```

**给你的 html 代码添加一些 HTML，这样我们就可以上传文件了**

```html
<form>
<progress value="0" id="uploader" max="100">0%</progress><br><br>
// get the file from user
<input id="photo"class="file"type="file" name="mainimage" 
                   value="" onchange="getfile()"><br><br>
// submit the chosen file
<button id="submit_link"type="submit" name="button">Save</button>
</form>
```

**说明:**
上面的代码只是一个 html 表单，可以接受用户的输入，即用户可以选择一个他想要上传的文件，然后点击保存按钮。当用户选择文件时' getfile()'函数调用和下面显示的' getfile()'函数在 javascript 文件中可以运行。然后可以用 javascript 代码进行进一步的调用处理，并返回图像的 url。

**添加 javascript，使 html 中定义的函数可以工作:**

```html
<script type="text/javascript">
       var selectedFile;
      function getfile()
      {
          var pic = document.getElementById("photo");

           // selected file is that file which user chosen by html form
          selectedFile = pic.files[0];

           // make save button disabled for few seconds that has id='submit_link'
          document.getElementById('submit_link').setAttribute('disabled', 'true');
          myfunction(); // call below written function
      }
      function myfunction()
      {
          // select unique name for everytime when image uploaded
          // Date.now() is function that give current timestamp
          var name="123"+Date.now();

          // make ref to your firebase storage and select images folder
          var storageRef = firebase.storage().ref('/images/'+ name);

          // put file to firebase 
          var uploadTask = storageRef.put(selectedFile);

          // all working for progress bar that in html
          // to indicate image uploading... report
          uploadTask.on('state_changed', function(snapshot){
            var progress = 
             (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
              var uploader = document.getElementById('uploader');
              uploader.value=progress;
              switch (snapshot.state) {
                case firebase.storage.TaskState.PAUSED:
                  console.log('Upload is paused');
                  break;
                case firebase.storage.TaskState.RUNNING:
                  console.log('Upload is running');
                  break;
              }
          }, function(error) {console.log(error);
          }, function() {

               // get the uploaded image url back
               uploadTask.snapshot.ref.getDownloadURL().then(
                function(downloadURL) {

               // You get your url from here
                console.log('File available at', downloadURL);

              // print the image url 
               console.log(downloadURL);
              document.getElementById('submit_link').removeAttribute('disabled');
            });
          });
      };
 </script>
```

**说明:**
当用户提交 html 表单后，调用 getfile()函数。该函数只需获取 html 表单选择的文件，并使保存按钮禁用几秒钟，直到文件上传到 firebase，然后进一步调用另一个函数“myfunction()”。“myfunction()”可以包含所有与 firebase 相关的实体,“myfunction”中的“name”是用于在数据库中存储名称图像的名称。然后一些代码来运行进度条和存储文件以及其他所有关联的实体和存储文件。将选定的文件放入数据库。然后 uploadtask . snapshot . ref . getdownloadurl()给我们返回 URL，再次以 html 形式保存按钮无法上传另一张图片。
文件上传到 firebase，然后返回一个需要 2-3 秒的网址，所以这就是为什么我可以使用进度条，并使提交按钮禁用一段时间。上传文件并生成网址后，只能启用提交按钮。