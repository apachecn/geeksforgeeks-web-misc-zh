# 减少网站加载时间的方法|设置 2

> 原文:[https://www . geesforgeks . org/way-reduce-loading-time-网站-set-2/](https://www.geeksforgeeks.org/ways-reduce-loading-time-website-set-2/)

先决条件:[减少网站加载时间的方法|设置 1](https://www.geeksforgeeks.org/ways-reduce-loading-time-website-set-1/)

在上面的文章中，我们描述了四种方法，即:

*   优化图像
*   缩小 JavaScript 和样式表
*   启用压缩
*   浏览器缓存

在本文中，我们将探索另外五种方法来减少网站的加载时间。

**1。** **优先考虑顶级内容**

这通常指的是在页面的其余部分加载之后加载您的 JavaScript 文件。之前加载这些脚本会导致大量的等待时间，我们知道，您的访问者有多喜欢等待。对此最简单的解决方案是在页面的底部，就在结束的 body 标签之前包含这些文件。

你的网站的 CSS 可以分成两部分:一个内嵌部分，样式高于折叠内容，一个外部部分，可以推迟。

**2。** **取消不必要的插件**

使用太多插件会在很大程度上降低你的网站速度，导致崩溃和其他技术困难。因此，建议停用或删除不必要的插件。

迈克()的一个案例研究展示了他如何将自己的网站速度从 4.23 秒降低到 1.33 秒。插件贡献了高达 86%的加载时间。

**3。** **最小化重定向**

重定向会导致额外的 HTTP 请求，从而增加加载时间。因此，将这些重定向保持在最低限度是可取的。

对于响应性网站，您可能希望用户被重定向到该网站的移动版本。
按照谷歌的说法，我们可能会执行以下操作，以确保响应的直接方式不会降低您网站的速度:

*   可以使用 **HTTP 重定向**将移动用户代理带到等效的网址，而无需中间重定向。
*   **标记可能包含在您的网页中，以指定您的移动等效网址，以便谷歌机器人可以发现您的移动页面。**

****4。** **使用内容交付网络****

**内容交付网络是一个分布式服务器系统，它根据用户的地理位置交付网络内容。从靠近用户地理位置的更快的服务器访问您的站点将大大减少加载时间。**

**流行的内容交付网络包括:**

*   **麦克斯坎**
*   **云 Flare**
*   **Incapsula**
*   **边缘铸造**
*   **亚马逊云前线**

**您可以点击这里的找到简单的步骤，将**亚马逊 S3 与云前线**设置为您的内容交付网络。**

****5。** **避免自办视频****

**视频文件通常非常大，上传到你的网站可能会非常缓慢。相反，可以使用第三方视频托管服务，如 **YouTube** 、 **Vimeo** 或 **Wisita** 。**

**你所需要做的就是复制他们提供的一小部分代码，然后粘贴到你的文章或网页中。**

**在当今时代，在线用户更喜欢更丰富的在线体验。将会有更精彩的 JavaScript、CSS 技巧和其他第三方分析，这些将会增加我们网站的规模。**

**但是我们需要很好地解决这个问题，不应该被它所阻碍。**

**要知道:**失去领先优势只需要一秒钟的延迟。****

****参考文献:****

*   **[https://www.crazyegg.com/blog/speed-up-your-website/](https://www.crazyegg.com/blog/speed-up-your-website/)**
*   **[https://www . truconversion . com/blog/转化率-优化/9-tips-减少页面加载-时间-提高网站速度/](https://www.truconversion.com/blog/conversion-rate-optimization/9-tips-to-reduce-page-load-time-and-improve-website-speed/)**
*   **[http://cubewires.com/insights/reduce-web-page-load-time/](http://cubewires.com/insights/reduce-web-page-load-time/)**

**本文由**尼哈尔·兰詹·萨卡尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**