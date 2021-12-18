# 用于抓取网页并获取最常用单词的 Python 程序

> Original: [https://www.geeksforgeeks.org/python-program-crawl-web-page-get-frequent-words/](https://www.geeksforgeeks.org/python-program-crawl-web-page-get-frequent-words/)

任务是统计最频繁的单词，这将从动态来源中提取数据。
首先，在*请求*模块和*美丽汤*模块的帮助下创建一个 web 爬行器或刮取器，该模块将从网页中提取数据并将其存储在列表中。 可能存在一些不需要的单词或符号(如特殊符号、空格)，可以对其进行过滤，以减少计数并获得所需的结果。

在计算完每个单词之后，我们还可以计算出最常用的单词(比如 10 个或 20 个)。
**使用的模块和库函数：**

> **请求：**将允许您发送 HTTP/1.1 请求以及更多请求。
> **BeaufulSoup4：**用于解析 HTML/XML 以从 HTML 和 XML 文件中提取数据。*
> **运算符：**导出一组与内部运算符相对应的高效函数。*
> **集合：**实现高性能容器数据类型。

下面是上面讨论的想法的实现：

## 蟒蛇 3

```
# Python3 program for a word frequency
# counter after crawling/scraping a web-page
import requests
from bs4 import BeautifulSoup
import operator
from collections import Counter

'''Function defining the web-crawler/core
spider, which will fetch information from
a given website, and push the contents to
the second  function clean_wordlist()'''

def start(url):

    # empty list to store the contents of
    # the website fetched from our web-crawler
    wordlist = []
    source_code = requests.get(url).text

    # BeautifulSoup object which will
    # ping the requested url for data
    soup = BeautifulSoup(source_code, 'html.parser')

    # Text in given web-page is stored under
    # the <div> tags with class <entry-content>
    for each_text in soup.findAll('div', {'class': 'entry-content'}):
        content = each_text.text

        # use split() to break the sentence into
        # words and convert them into lowercase
        words = content.lower().split()

        for each_word in words:
            wordlist.append(each_word)
        clean_wordlist(wordlist)

# Function removes any unwanted symbols

def clean_wordlist(wordlist):

    clean_list = []
    for word in wordlist:
        symbols = "!@#$%^&*()_-+={[}]|\;:\"<>?/., "

        for i in range(len(symbols)):
            word = word.replace(symbols[i], '')

        if len(word) > 0:
            clean_list.append(word)
    create_dictionary(clean_list)

# Creates a dictionary containing each word's
# count and top_20 occurring words

def create_dictionary(clean_list):
    word_count = {}

    for word in clean_list:
        if word in word_count:
            word_count[word] += 1
        else:
            word_count[word] = 1

    ''' To get the count of each word in
        the crawled page -->

    # operator.itemgetter() takes one
    # parameter either 1(denotes keys)
    # or 0 (denotes corresponding values)

    for key, value in sorted(word_count.items(),
                    key = operator.itemgetter(1)):
        print ("% s : % s " % (key, value))

    <-- '''

    c = Counter(word_count)

    # returns the most occurring elements
    top = c.most_common(10)
    print(top)

# Driver code
if __name__ == '__main__':
    url = "https://www.geeksforgeeks.org/programming-language-choose/"
    # starts crawling and prints output
    start(url)
```

```
[('to', 10), ('in', 7), ('is', 6), ('language', 6), ('the', 5),
 ('programming', 5), ('a', 5), ('c', 5), ('you', 5), ('of', 4)]
```