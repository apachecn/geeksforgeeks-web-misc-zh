# Pytube|下载 YouTube 视频的 Python 库

> Original: [https://www.geeksforgeeks.org/pytube-python-library-download-youtube-videos/](https://www.geeksforgeeks.org/pytube-python-library-download-youtube-videos/)

YouTube 是非常受欢迎的视频分享网站。 从 YouTube 下载视频是一项艰巨的工作。 下载下载程序并使用该下载程序获取视频，或者访问任何其他网站获取视频并将其保存在您的计算机上。 使用 Python，这项任务非常简单。 只需几行代码就可以从 YouTube 下载视频。 为此，有一个名为“pytube”的 python 库。 Pytube 是一个轻量级的、无依赖关系的 Python 库，用于从 Web 上下载视频。
pytube 不是本地库。 您需要在使用之前安装它。 有了 pip，安装就很容易了。 在终端或命令提示符下，键入以下命令以安装 pytube。

```html
pip install pytube

```

如果您没有 pip，可以将其作为外部库安装。

**下载单个视频**

Pytube 库使得视频下载变得非常简单。 通过将链接作为参数传递来创建 YouTube 模块的对象。 然后，获取视频的适当扩展和分辨率。 为了方便起见，您可以设置文件的名称，在另一种情况下，将保留原始名称。 之后，使用 Download 函数下载文件，该函数有一个参数，即下载文件的位置。

## 蟒蛇 3

```html
# importing the module 
from pytube import YouTube 

# where to save 
SAVE_PATH = "E:/" #to_do 

# link of the video to be downloaded 
link="https://www.youtube.com/watch?v=xWOoBJUqlbI"

try: 
    # object creation using YouTube
    # which was imported in the beginning 
    yt = YouTube(link) 
except: 
    print("Connection Error") #to handle exception 

# filters out all the files with "mp4" extension 
mp4files = yt.filter('mp4') 

#to set the name of the file
yt.set_filename('GeeksforGeeks Video')  

# get the video with the extension and
# resolution passed in the get() function 
d_video = yt.get(mp4files[-1].extension,mp4files[-1].resolution) 
try: 
    # downloading the video 
    d_video.download(SAVE_PATH) 
except: 
    print("Some Error!") 
print('Task Completed!') 
```

下载文件需要一些时间，因为要从 Web 下载大量数据。 根据连接速度的不同，执行程序所需的时间也不同。 如果您希望下载该数量的文件，请使用下一个案例。

**下载多个视频**

下载多个视频的基本任务与下载单个视频相同。 我们可以使用 for 循环来下载视频。

## 蟒蛇 3

```html
from pytube import YouTube 

#where to save 
SAVE_PATH = "E:/" #to_do 

#link of the video to be downloaded 
link=["https://www.youtube.com/watch?v=xWOoBJUqlbI", 
    "https://www.youtube.com/watch?v=xWOoBJUqlbI"
    ]

for i in link: 
    try: 

        # object creation using YouTube
        # which was imported in the beginning 
        yt = YouTube(i) 
    except: 

        #to handle exception 
        print("Connection Error") 

    #filters out all the files with "mp4" extension 
    mp4files = yt.filter('mp4') 

    # get the video with the extension and
    # resolution passed in the get() function 
    d_video = yt.get(mp4files[-1].extension,mp4files[-1].resolution) 
    try: 
        # downloading the video 
        d_video.download(SAVE_PATH) 
    except: 
        print("Some Error!") 
print('Task Completed!') 
```

在这里，我们使用了 for 循环来下载多个文件，如下所示。 可以使用文件处理将所有链接保存在需要下载的文件中。

**使用文件处理下载多个视频**

使用文件处理，我们可以打开包含链接组的文件。 这里遍历文本文件的每个链接，并应用非常基本的视频下载程序。 这里，我们有一个名为“linksfile.txt”的文本文件，其中包含需要下载的所有链接。

## 蟒蛇 3

```html
from pytube import YouTube 

# where to save 
SAVE_PATH = "E:/" #to_do 

# link of the video to be downloaded 
# opening the file 
link=open('links_file.txt','r') 

for i in link: 
    try: 

        # object creation using YouTube
        # which was imported in the beginning 
        yt = YouTube(i) 
    except: 

        #to handle exception
        print("Connection Error")  

    #filters out all the files with "mp4" extension 
    mp4files = yt.filter('mp4') 

    # get the video with the extension and
    # resolution passed in the get() function 
    d_video = yt.get(mp4files[-1].extension,mp4files[-1].resolution) 
    try: 

        # downloading the video 
        d_video.download(SAVE_PATH) 
    except: 
        print("Some Error!") 
print('Task Completed!') 
```

**要点：**

1.  请确保您已连接到互联网以下载视频。 否则，它将引发错误。
2.  不要在任何循环中使用 set_filename()函数。 在这种情况下，将只下载一个视频。
3.  每次都可以使用另一个名称数组修改名称。
4.  两者之间的连接中断也会引发错误，在这种情况下将不会下载视频。

本文由[**Rishabh Bansal**](https://www.linkedin.com/in/rishabh-bansal-9b4b71108/)贡献。 如果你喜欢 GeeksforGeek 并想投稿，你也可以使用[Contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章，或者把你的文章邮寄到 Contribute@geeksforgeeks.org。 看看你的文章出现在 GeeksforGeek 主页上，并帮助其他 Geek。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写下评论。