# 减少网站加载时间的方法|设置 1

> 原文:[https://www . geesforgeks . org/way-reduce-loading-time-网站-set-1/](https://www.geeksforgeeks.org/ways-reduce-loading-time-website-set-1/)

**“耐心是一种美德”**——当我们考虑网络活动时，这句格言几乎不成立。网站的页面加载时间非常重要。**为什么？**
它决定了你网站的访问者是继续探索，还是第一次点击就分道扬镳。
一些统计事实:

*   1 秒钟的加载时间延迟会导致页面浏览量减少 11%，客户满意度下降 16%，转化率下降 7%。
*   44%的客户对公司产生负面形象，如果其网站加载时间少的话。
*   按照**亚马逊**的说法，每提高 100 毫秒就有 1%的收入增长。

此外，研究表明，47%的访问者预计加载时间为 2 秒或更短，如果加载时间超过 3 秒，57%的潜在客户将放弃该网站，前往其他地方满足他们的需求。

速度也决定了你网站的谷歌搜索排名。下面提供了一些有助于减少网站加载时间的方法。

**减少网站加载时间的方法**

**1。** **优化图像:**上传前，图像应适当缩放。我们需要明白这一点:如果我们有一个 1000 X 1000 像素的图像，我们已经在 CSS 的帮助下缩小到 100 X 100 像素，浏览器仍然加载实际大小，也就是说，在这种情况下，比需要的大 10 倍。

为了避免这种情况，在使用各种图像编辑工具将图像上传到您的网站之前，请裁剪或缩放图像。这些图像优化工具包括:

*   Smush.it
*   在线图像优化器
*   JPEG &PNG 剥离器
*   SuperGIF

说到图像格式， **JPEG** 是最好的选择。 **PNG** 也不错，虽然很多老浏览器不支持。

**2。** **缩小 JavaScript 和样式表:**缩小是从代码中删除所有不必要的字符，以减小大小。不需要的空白字符，如空格、换行符、制表符等。并删除注释。缩小 HTML、CSS 和 JavaScript 的推荐工具:

*   对于 HTML，我们可以使用**页面速度洞察 Chrome 扩展**来生成您的 HTML 代码的优化版本。
*   对于 CSS，使用 **YUI 压缩机**和 **cssmin.js**
*   对于 JavaScript，可以使用**闭包编译器**、 **JSMin** 或者 **YUI 压缩器**。

也有一些在线工具可以使用，[https://javascript-minifier.com/](https://javascript-minifier.com/)，[https://cssminifier.com/](https://cssminifier.com/)

**3。** **启用压缩:**大页面可以通过拉链压缩。压缩会减少页面的带宽，从而减少 HTTP 响应。

**Gzip** 是经常用来实现这一点的工具之一。由于当今 90%的互联网流量使用 Gzip，因此值得选择。Gzip 压缩后，设置您的服务器以启用压缩。

*   阿帕奇:使用 mod_deflate
*   nginx:使用 HttpGzipModule
*   IIS:配置 HTTP 压缩

**4。** **浏览器缓存:**将数据临时存储在访问者的硬盘上，可以省去访问者每次访问你的网站时的等待时间。这可以使用浏览器缓存来完成。但是，存储这些数据的持续时间取决于您的服务器端缓存配置。要启用浏览器缓存，您需要编辑您的 HTTP 头来设置特定类型文件的到期时间。

此示例显示了如何配置 **Apache** 来提供适当的报头:

*   找到你的。域根目录中的 htaccess 文件。文件是隐藏的，但是像 FileZilla 这样的 FTP 客户端会帮助它显示出来。
*   使用记事本或任何其他基本编辑器向。htaccess 文件。

```
## EXPIRES CACHING ##
<IfModule mod_expires.c>
ExpiresActive On
ExpiresByType image/jpg "access plus 1 year"
ExpiresByType image/jpeg "access plus 1 year"
ExpiresByType image/gif "access plus 1 year"
ExpiresByType image/png "access plus 1 year"
ExpiresByType text/css "access plus 1 month"
ExpiresByType application/pdf "access plus 1 month"
ExpiresByType text/x-javascript "access plus 1 month"
ExpiresByType application/x-shockwave-flash "access plus 1 month"
ExpiresByType image/x-icon "access plus 1 year"
ExpiresDefault "access plus 2 days"
</IfModule>
## EXPIRES CACHING ##
```

**重要点**

*   根据您网站的文件，可以设置不同的到期时间。频繁更新的文件需要更早的到期时间。
*   完成后，按原样保存文件。

更多的方法将在下一集探讨。
[减少网站加载时间的方法|第二集](https://www.geeksforgeeks.org/ways-reduce-loading-time-website-set-2/)

**参考文献:**

*   [https://www.crazyegg.com/blog/speed-up-your-website/](https://www.crazyegg.com/blog/speed-up-your-website/)
*   [https://www . truconversion . com/blog/转化率-优化/9-tips-减少页面加载-时间-提高网站速度/](https://www.truconversion.com/blog/conversion-rate-optimization/9-tips-to-reduce-page-load-time-and-improve-website-speed/)
*   [http://cubewires.com/insights/reduce-web-page-load-time/](http://cubewires.com/insights/reduce-web-page-load-time/)
*   [https://gtmetrix.com/leverage-browser-caching.html](https://gtmetrix.com/leverage-browser-caching.html)

本文由**尼哈尔·兰詹·萨卡尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。