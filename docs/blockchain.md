# 区块链解释

> 原文：<https://blog.quantinsti.com/blockchain/>

由[乌迪莎·阿洛克](http://www.linkedin.com/in/udisha-alok)

一段时间以来，区块链一直是各界感兴趣的话题。它不断出现在多种讨论和不同的上下文中——而且是有充分理由的！

根据最近的[报告](https://www.marketsandmarkets.com/Market-Reports/blockchain-technology-market-90100890.html#:~:text=%5B441%20Pages%20Report%5D%20The%20Blockchain,68.4%25%20during%20the%20forecast%20period.)，区块链市场规模预计将从 2021 年的 49 亿美元增长到 2026 年的 674 亿美元，预测期内的复合年增长率(CAGR)为 68.4%。

区块链就像一个神奇的精灵，拥有看似无限的力量，不可能在一篇文章中涵盖它的所有内容。让我们试着把这个精灵放进瓶子里，简单看看区块链是什么，是什么让它具有破坏性。

以下是我们将在本文中讨论的一些内容。

*   [价值互联网](#internet-of-value)
*   [什么是区块链？](#what-is-blockchain)
*   [区块链的组成](#components-of-a-blockchain)
*   [区块链的优势](#strengths-of-blockchain)
*   [区块链的应用](#applications-of-blockchain)
*   [使用区块链的挑战](#challenges-of-using-blockchain)

* * *

## 价值互联网

在我们开始讨论区块链的话题之前，让我们先回顾一下另一项技术——互联网，它也有类似的去中心化、可访问性和匿名性的承诺，这正是区块链吸引我们的地方。

互联网的出现预示着人类的一个新时代，以至于很难想象没有它的存在。与世界各地的人交流和互动，与更广泛的受众分享观点、意见和创造力的自由，以最低的成本进入一个全新的技术世界——互联网的好处是巨大的。

这就是信息互联网——旨在传输信息，而不是像金钱或产权这样有价值的东西；至少在没有银行、Paypal 或政府等第三方的情况下是不会的。

但是当我们在网上发布任何东西时，我们真的是匿名的吗？

最近，互联网上的行为显然受到了密切监控。通过向我们提供免费账户和服务，大公司一直在收集关于我们的重要信息。关于我们的婚姻状况、收入、我们去过的地方、我们买的东西、我们花更多时间浏览的网站、喜欢和不喜欢的东西、我们的朋友、我们的政治和宗教倾向等信息。

一点一点地，他们正在建立我们每个人的数字角色，最终可能听起来比我们自己更真实——你会记得五年前的今天你去过的餐馆或那天你“绝对喜欢”的菜吗？数字角色会的！

互联网的好处之一是能够与任何人自由分享信息。当你自拍并与朋友分享时，你分享了它的副本。因此，你可以与任何数量的人分享它，并且仍然拥有原始版本。因此，像现在这样的互联网不能用来分享任何有价值的东西，比如钱。

但是，如果你也能使用互联网来分享资产，那会怎么样呢？如果你能追踪每一项资产，比如一件艺术品或一笔钱，并通过互联网发送给一个朋友，那会怎么样？这样，由互联网供电的多个设备不仅可以相互通信，还可以购买电力？

这就是互联网 2.0 - **价值互联网**。

* * *

## 什么是区块链？

区块链本质上是一个分布在多个节点/计算机上的数据库。它由信息的“块”组成，每个块都“链接”到其前一个块。街区？锁链？让我们进一步分解一下。

### 块、链和散列

块由几条记录组成，就像常规数据库中的表或电子表格一样。但它与传统数据库的不同之处在于，每个块都连接或链接到前一个块。我们稍后将看到这种“连锁”是如何发生的。

现在，在我们继续讨论之前，让我们简单地了解一下什么是 hash。就像指纹被用来识别人一样，散列是一串看似随机的数值，代表任何文件——图像、文本、音频等。每次你创建一个文件的散列，你都会得到相同的值。

然而，即使是对文件的微小修改，不管是空格还是逗号，都会改变散列。

有不同类型的散列算法，但在区块链通常使用的是 SHA256。这里，SHA 的意思是安全哈希算法。

在 Python 中，我们可以使用' *hashlib* '模块为文件/字符串生成散列。这个模块支持许多不同类型的散列算法。