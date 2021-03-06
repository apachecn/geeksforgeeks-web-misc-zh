# Python|使用 regex 和 urllib

解析网站

> Original: [https://www.geeksforgeeks.org/python-parse-a-website-with-regex-and-urllib/](https://www.geeksforgeeks.org/python-parse-a-website-with-regex-and-urllib/)

让我们讨论一下使用 python 进行解析的概念。 在 Python 中，我们有很多模块，但是对于解析，我们只需要**urllib**和**Re**，即正则表达式。 通过使用这两个库，我们可以获取网页上的数据。

请注意，解析网站意味着获取整个源代码，并且我们希望使用给定的 url 链接进行搜索，它会给出大量您无法理解的 HTML 内容的输出。 让我们看一下演示，并提供解释，让您更好地理解解析。

**代码#1：**需要库

```html
# importing libraries
import urllib.request
import urllib.parse
import re
```

**代码#2：**

```html
url = 'https://www.geeksforgeeks.org/'
values = {'s':'python programming',
          'submit':'search'}
```

我们已经定义了要搜索的 URL 和一些相关值。 请记住，我们将值定义为字典，并且在这个键值对中，我们在定义的 url 上定义了**python Programming**到**search**。

**代码#3：**

```html
data = urllib.parse.urlencode(values)        
data = data.encode('utf-8')                  
req = urllib.request.Request(url, data)      
resp = urllib.request.urlopen(req)    

respData = resp.read()                      
```

在第一行中，我们对前面定义的值进行编码，然后(第二行)对机器可以理解的相同数据进行编码。
在第三行代码中，我们请求定义的 url 中的值，然后使用模块`urlopen()`打开该 HTML 的 Web 文档。 最后一行`read()`中的
将帮助逐行读取文档，并将其赋给*resData*命名变量。

**代码#4：**

```html
paragraphs = re.findall(r'<p>(.*?)</p>', str(respData))

for eachP in paragraphs:
    print(eachP)
```

为了提取相关数据，我们采用了正则表达式。 第二个参数必须是字符串类型，如果我们想打印数据，则应用简单的打印函数。

下面是几个示例：

**示例 1：**

```html
import urllib.request
import urllib.parse
import re

url = 'https://www.geeksforgeeks.org/'
values = {'s':'python programming',
          'submit':'search'}

data = urllib.parse.urlencode(values)
data = data.encode('utf-8')
req = urllib.request.Request(url, data)
resp = urllib.request.urlopen(req)
respData = resp.read()

paragraphs = re.findall(r'<p>(.*?)</p>',str(respData))

for eachP in paragraphs:
    print(eachP)
```

**输出：**
![](img/36733ede0bc48e2d54b63636e67fb989.png)

**示例 2：**

```html
import urllib.request
import urllib.parse
import re

url = 'https://www.geeksforgeeks.org/'
values = {'s':'pandas',
          'submit':'search'}

data = urllib.parse.urlencode(values)
data = data.encode('utf-8')
req = urllib.request.Request(url, data)
resp = urllib.request.urlopen(req)
respData = resp.read()

paragraphs = re.findall(r'<p>(.*?)</p>',str(respData))

for eachP in paragraphs:
    print(eachP)
```

**输出：**
![](img/74575e47e0c8e74f4d73ff1e39bf92f5.png)