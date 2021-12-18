# 【BitTorrent 是如何工作的？

> 原文:[https://www.geeksforgeeks.org/how-bittorrent-works/](https://www.geeksforgeeks.org/how-bittorrent-works/)

我们大多数人都听说过激流，可能也尝试过下载电影、书籍、音乐、电视剧、游戏等。但是，什么是 BitTorrent？它是如何工作的？

BitTorrent 是[点对点文件共享](https://www.geeksforgeeks.org/p2ppeer-to-peer-file-sharing/)(“P2P”)的超级分发通信协议，用于在互联网上分发数据和电子文件。它是由布法罗大学计算机科学研究生布拉姆·科恩开发的。

Bittorrent 通过极其强大的网络连接将大型数据文件从一台大型服务器传输到每个用户，并将其拆分为多台普通电脑和多个较小的网络连接。

如果你是一个 Torrent 用户，你可能会注意到术语“种子”、“同行”和“水蛭”，让我们来理解这些术语。

**什么是种子？**
Seed 是已经下载了完整文件的用户，现在正在与对等方共享该文件，但没有从其他人那里下载该文件的任何部分。

**什么是水蛭？**
水蛭是同时下载和上传的。

**什么是同行？**
文件是分块下载的。当用户下载某些部分时，他会自动开始上传。如果有更多的用户参与到这个过程中，文件下载会更快。

第一次共享文件时，有一个种子或用户将文件上传到第一个下载器，对等体首先创建一个名为“种子”的小文件。该文件包含关于要共享的文件和跟踪器的元数据，因此种子在刚创建时总是相对较慢，但是一旦原始上传/下载过程完成，下载该文件的用户(也称为来自原始种子的对等用户)也会变成种子，然后越受欢迎的文件创建的种子越多，新来者的速度就越快。

**参考文献**T2[https://en.wikipedia.org/wiki/BitTorrent](https://en.wikipedia.org/wiki/BitTorrent)T5[https://www.geeksforgeeks.org/p2ppeer-to-peer-file-sharing/](https://www.geeksforgeeks.org/p2ppeer-to-peer-file-sharing/)

本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。