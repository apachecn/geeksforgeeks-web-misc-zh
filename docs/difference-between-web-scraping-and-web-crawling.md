# 刮网和爬网的区别

> 原文:[https://www . geeksforgeeks . org/网页抓取和网页抓取的区别/](https://www.geeksforgeeks.org/difference-between-web-scraping-and-web-crawling/)

**1。** [**网页抓取**](https://www.geeksforgeeks.org/introduction-to-web-scraping/) **:**
网页抓取是一种从网站中提取大量数据，然后以 [XML](https://www.geeksforgeeks.org/xml-basics/) 、excel 或 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 的形式保存到本地机器的技术。用于刮网的工具称为**刮网器**。根据给定的要求，他们可以在短时间内从任何网站提取数据。任务的这种自动化对于为机器学习和其他目的开发数据非常有帮助。它们分四步工作:

1.  将请求发送到目标页面。
2.  从目标页面获取响应。
3.  解析并提取响应。
4.  下载数据。

一些流行的网页抓取工具有 ProWebScraper、web scratcher . io 等。

**2。网络爬行:**
网络爬行类似蜘蛛爬行，但这里爬行的地方是网络！。它基本上访问一个网站并阅读网页，目的是为搜索引擎索引建立条目。用于网络爬行的工具被称为**网络爬虫**或**蜘蛛**。对一系列网页进行分析，然后跟踪指向这些网页的链接，寻找更多的链接，从而对信息提取进行深度搜索。著名的搜索引擎，如谷歌、雅虎和必应，进行网页抓取，并使用这些信息为网页编制索引。例如 Scrapy 和 Apache 坚果。

**刮网与爬网的区别:**

<figure class="table">

| s。没有。 | Scraping net | Crawl |
| --- | --- | --- |
| 1。 | The tool used is **scraper** . | The tools used **web crawler** or **spider** . |
| 2。 | Used to **download** information. | Used for **index** webpage |
| 3。 | It **does not need to visit all pages of the website** to obtain information. | It **visits every page** until the last line gets the information. |
| 4。 | The scraper **does not obey the robot in most cases.** | Not all web crawlers **obey robots.txt** . |
| 5。 | Do both small-scale **and large-scale** . | Mainly used for **large** . |
| 6。 | Applications include retail marketing, equity search and machine learning. | Which is used for providing search results to users in search engines. |
| 7。 | Deduplication is not necessarily part of web crawling. | Deduplication is an indispensable part of web page crawling. |
| 8。 | This **requires a capture agent and a parser** to parse the response. | This **only needs to grab the agent** . |
| 9。 | 前屏幕、网络屏幕。超正析象管就是例子 | Google, Yahoo or Bing do Web crawling. |

</figure>