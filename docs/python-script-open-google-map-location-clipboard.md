# 在剪贴板

上打开 Google 地图位置的 Python 脚本

> Original: [https://www.geeksforgeeks.org/python-script-open-google-map-location-clipboard/](https://www.geeksforgeeks.org/python-script-open-google-map-location-clipboard/)

任务是创建一个 python 脚本，该脚本将打开默认的 Web 浏览器，指向作为命令行参数给出的地址的 Google 地图。

**具体流程如下：**

1.  **从命令行输入创建 ADDRESS_STRING：可以通过 sys 模块读取**个命令行参数。 Sys.argv 数组将第一个元素作为文件名，其余元素作为命令行参数，这些参数由空格分隔为不同的元素，与 raw_input().plit()相同。 因此，如果 sys.argv 的长度大于 1，那么我们可以确定已经传递了命令行参数。
    由于 sys.argv 是一个字符串列表，因此可以将其传递给 Join()方法，该方法返回单个字符串值。 因为第一个元素是不需要的文件名，所以我们可以分割列表并从第二个元素开始连接。

```html
#File name is Map.py
import sys
print ' '.join(sys.argv[1:])
```

```html
If we run >>> python Map.py New Delhi
The output of the program would be New Delhi.
```

*   **打开 Web 浏览器：**我们将使用**Web 浏览器**模块打开浏览器。 Web 浏览器模块具有方法**open()**，该方法可以将 Web 浏览器启动到指定的 URL。 例如，下面给出的脚本将打开 Web 浏览器，进入 GeeksforGeek 的主页。

    ```html
    import webbrowser
    webbrowser.open('https://www.geeksforgeeks.org/')
    ```

    *   **Find the URL :** Now, when we go to Google Maps and search for google maps, the URL turns out to be gibberish and of no clear pattern, as shown below.
    [https://www.google.co.in/maps/place/GeeksforGeeks/@28.5011226,77.4077907,17z/data=!3m1!4b1!4m5!3m4!1s0x390ce626851f7009:0x621185133cfd1ad1!8m2!3d28.5011226!4d77.4099794?hl=en](https://www.google.co.in/maps/place/GeeksforGeeks/@28.5011226,77.4077907,17z/data=!3m1!4b1!4m5!3m4!1s0x390ce626851f7009:0x621185133cfd1ad1!8m2!3d28.5011226!4d77.4099794?hl=en)

    网站通常会在 URL 中添加额外的文本，用于定制和跟踪等附加任务。 然而，可以观察到，url 的最初几个部分是**GeekforGeek**，其中 https://www.google.co.in/maps/place/GeeksforGeeks 是我们搜索的关键字。
    还有，比如说在搜索新德里，而不是新德里的时候，如果我们只写新德里，那么+就会自动插入到所需的位置，这就进一步简化了我们的任务。
    因此，最终的 URL 可以作为**https://www.google.co.in/maps/place/*ADDRESS_STRING*/**。

    *   **Combining the two and Completing the script :** The python script to open the given command line address is given below. There will be two imported modules, **webbrowser** to open the browser to the designated URL and **sys** to work on the command line arguments.
    *   第一步是检查是否给出了任何命令行，这是使用 len(sys.argv)完成的。
    *   然后，我们使用 Join 方法形成要在 Google Maps 中搜索的地点的地址字符串。
    *   最后，获取地址后，使用 WebBrowser 模块的 open()方法打开浏览器，进入地址 URL。

    程序通过 CMD(WINDOWS)或终端(LINUX)运行，格式如下：

    ```html
    >>> python [File Name] [Address to be searched]
    For eg. >>> python Map.py GeeksforGeeks
    ```

    ```html
    # File Name -- Map.py
    import sys, webbrowser
    if len(sys.argv) > 1:       # Argument passed
        map_string = ' '.join(sys.argv[1:])
        webbrowser.open('https://www.google.com/maps/place/' + map_string)

    else:
        print "Pass the string as command line argument, Try Again"

    ```

    ```html
    >>> python Map.py SeeksforGeeks
    The above command will open map of GeeksforGeeks in the web browser.

    ```

    本文由**哈里特·阿格拉瓦尔**贡献。 如果你喜欢 GeeksforGeek 并想投稿，你也可以使用[Contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章，或者把你的文章邮寄到 Contribute@geeksforgeeks.org。 看看你的文章出现在 GeeksforGeek 主页上，并帮助其他 Geek。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写下评论。