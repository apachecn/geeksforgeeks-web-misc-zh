# 握手:一种对等命名系统

> 原文:[https://www . geesforgeks . org/handshake-an 对等命名系统/](https://www.geeksforgeeks.org/handshake-an-peer-to-peer-naming-system/)

[DNS(域名系统)](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/)是并且一直是互联网基础设施的重要组成部分。域名系统甚至在万维网(1988 年首次部署)之前就已经存在(大约在 20 世纪 80 年代初实施)。简而言之，域名系统是一种协议，负责将人类可读的主机名(如 google.com、geeksforgeeks.org、india.gov.in)转换为机器可理解的号码，这些号码主要是各自服务器的 IP 地址。这看起来很简单，但对互联网来说非常重要，重要的东西是坏人的主要目标。DNS 是一个设计良好且不断发展的协议，但安全性并不是主要方面，但现在它是了。

域名系统的一些广为人知的缺点是:

1.  **DNS 缓存中毒-**
    由不良行为者破坏(或)更改 DNS 记录的恶意方法。它是通过在域名系统中增加一些被统称为 DNSSEC(域名系统安全扩展)的安全功能来控制的。
2.  **网络数据包嗅探、DNS 劫持-**
    DNS 记录的用户查询和名称服务器响应以未加密的方式发送，这使得不良行为者得以利用。加密作为一种解决方案，被用来开发一些新的协议，以解决像 DoT(域名系统在顶级域名系统之上)和 DoH(域名系统在 HTTPS 之上)这样的问题。
3.  **隐私-**
    这并不是什么新鲜事，DNS 从来就不是为了隐私而设计的，DNS 的整个理念就是要公开。增加域名系统查询中的客户端 IP 信息量已成为用户隐私的一个关注点。从技术上来说，没有办法使域名系统成为私有的，但是可以使用虚拟专用网络，这减少了客户端的知识产权信息量。
4.  **去中心化-**
    域名系统是作为一个分级和去中心化的系统而产生的，从技术上来说它仍然是，但从伦理上来说它不是。很少有公司只运营大部分消费者和公共域名系统。这是域名系统的一个非常普遍和重要的缺点。

**握手协议及其解决的问题:**
握手是一种分散的无权限命名协议，其中每个对等体都使用区块链验证并负责管理根 DNS 命名区域。握手的主要目的是通过增加隐私和安全的好处来分散域名系统。握手希望分散许多互联网服务，这些服务变得集中起来，比如电子邮件变成了 Gmail，新闻组变成了 Reddit，博客回复变成了脸书和 Medium，Pingbacks 变成了 Twitter，squid 变成了 Cloudflare，Gnutella 再次变成了海盗湾。
Handshake 是一个基于 UTXO(未使用事务输出)的区块链，它使用 bcoin，bcoin 是用带有一些可移植 C 库的 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 编写的[比特币](https://www.geeksforgeeks.org/what-is-bitcoin/)的分叉。握手协议将取代 ICANN 根服务器。握手有完整的节点客户端 hnd 和一个轻量级客户端 hnsd。握手中的交易是利用 HNS 硬币完成的。对于那些不太擅长运行自己的节点的人来说，Namebase 注册表帮助用户使用他们的门户网站来管理他们的握手顶级域名。握手还试图取代证书颁发机构，以完全分散互联网。

**握手不止是另一个区块链:**
握手方法论是“在创造最好的东西之前，先把现有的东西变得更好”。握手试图为现有的域名系统基础设施提供尽可能多的向后兼容性。握手并不是第一个利用区块链重塑域名系统的项目，也不会是最后一个。其他项目如 ENS(以太网域名服务)、不可阻挡的域名、域名币也正在开发中。Handshake 和其他域名系统的主要区别在于，他们试图通过使用像这样的 TLD 子域来创建一个类似于域名系统的命名系统。密码。zil。eth，而 Handshake 试图替换根区域。网络中的每个对等点都负责验证和管理根区域，这完美地解释了“由每个人构建，为每个人构建”的理念。握手开发人员还保留了所有现有的 ICANN 顶级域名和 Alexa 的前 10 万，以防止恶意使用。

**握手币:**
HNS(或)握手币是握手协议中的原生类令牌币，允许域名的转移、注册和更新。当一个域名被拍卖、更新和出售时，硬币会在区块链被烧掉，所以没有人赚钱。这也产生了拥有一个名字的成本，使得在网络上发送垃圾邮件变得昂贵。

**赚买 HNS:**
握手是开源的。大多数 HNS(大约 1020 万美元)被赠与自由和开源软件的开发者、项目和社区。

1.  任何在 GitHub 上拥有超过 15 名粉丝，并且在他们的 GitHub 帐户上拥有有效 SSH+PGP 密钥的人(大约 170，000 个帐户)
2.  其 PGP 密钥包含在 WOT StrongSet 中的人员(30，000 个密钥)
3.  1.5 年以上的黑客新闻帐户，带有链接的 Keybase 帐户(约 19，000 个帐户)

所有这些都已经分发了，所以我们迟到了，但我们可以从加密货币交易所购买 HNS 硬币。由于 Handshake 只有一年的历史，支持 HNS 的交易所不多，不要担心谁知道 coinbase 很快会开始支持它们。允许 HNS 交换的一些交换是

1.  **名词基**
2.  **Bittrex**
3.  **闸门**
4.  **Hotbit**
5.  **mxm**

**握手钱包:**
全节点客户端 hnd 可用于进行交易，并允许您接收和花费 HNS，对名称进行投标，并更新您的域的 DNS 记录。[握手 cli 客户端](https://hsd-dev.org/guides/wallet.html)和[鲍勃钱包](https://github.com/kyokan/bob-wallet)(提供图形用户界面)也允许您这样做。名字库还提供和管理钱包，承担设置和管理钱包的重任。

**握手时注册域名:**
握手使用维克瑞风格的名称拍卖(最高出价者将支付第二高出价金额的拍卖类型)。让我们使用名称库，因为它很容易。

1.  进入[域名库](https://www.namebase.io/domains)页面搜索你的域名。
2.  搜索页面会告诉你你想要的名字在不在。
3.  如果可以的话，你可以用握手硬币出价，这将触发名称拍卖的 720 块(大约 5 天)投标期。
4.  投标期结束后，将开始 1440(约 10 天)的区块展示期，在此期间，投标人必须展示其投标的价值(Namebase 会自动为您这样做)。
5.  在展示期结束后，出价最高的投标人将只支付第二高的投标金额，并将收到他们赢得的名称。

```html
NOTE: 
Namebase, it doesn't need any setup or technical abilities 
all that is required is Browser with an Internet
```

**参考文献:**

1.  握手网站-[https://handshake.org](https://handshake.org/)
2.  握手文档-[https://hsd-dev.org](https://hsd-dev.org/)
3.  握手协议概要-[https://hsd-dev.org/guides/protocol.html](https://hsd-dev.org/guides/protocol.html)
4.  握手 github-https://github . com/handshake-org
5.  [https://namebase.io](https://namebase.io/)
6.  名基学习中心-[https://learn.namebase.io/](https://learn.namebase.io/)
7.  域名拍卖-[https://learn.namebase.io/about-handshake/handshake-auction](https://learn.namebase.io/about-handshake/handshake-auction)