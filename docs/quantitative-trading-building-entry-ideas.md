# 量化交易——建立入门思路和思路流程

> 原文：<https://blog.quantinsti.com/quantitative-trading-building-entry-ideas/>

扎克·奥克斯

我最喜欢的作者之一凯文·戴维(Kevin Davey)宣扬了一个他称之为“策略工厂”的想法——虽然这个过程的所有部分对盈利策略的制定都至关重要，但如果没有原始投入(或新的交易想法)，你将会极大地限制你的产出。那么，即使在你似乎已经测试并优化了你认为可行的每一个入口组合之后，你如何保持想法的流动呢？让我们看看。

在本文中，我们将介绍:

*   [交易中的想法流程](#flow)*   [进入和退出](#entry-exit)*   [产生参赛创意](#generate-ideas)*   [鼓舞人心的新高度](#inspiring)*   [产生新想法的重要性](#importance-ideas)

自动交易的一个关键部分是想法的产生，通过保持事情简单，你可以通过改善输入来大大提高输出。做到这一点的一个简单方法是让战略的一些可变方面保持不变——比如使用固定的退出方案——并在开始时只关注新的进入。

通过优化战略发展的过程，你可以创造一个新鲜的，独特的信号不断输出，可以结合起来，大大提高你的表现。

那么，我们如何保持想法流动？对我来说，我设定了每周必须测试的新想法的门槛——为了保持信号的持续流入。这些并不总是最初的伟大想法，但有时它们会激发伟大的想法或对现有事物的改进。我试着每周创造 5 个有机进入信号。

让我对*条目*多讲一点——最初，我有一个通用的退出包(TrailStop，Fixed Stop，Boolean Target ),我称之为*信号*退出；基本上只是出场逻辑的延伸。

用一个例子来解释更容易，如果我在 5 日均线穿过 20 日均线时做多，也许我的做多信号出口是在 5 日均线有负斜率时，或者当它们都是负斜率时，或者当 5 日均线低于 20 日均线时，如果只是做多。

结合我的一般退出包——百分比止损、固定止损和布尔利润目标——我基本上可以复制粘贴到我的退出包中，调整进场逻辑，我就可以开始测试策略了。

我这样做有几个原因:

1.  效率——它能让我保持思路畅通。有时我会添加一个新的退出信号的想法，并把它作为那周我的 5 个独特想法之一。但大多数时候，我坚持使用我的通用退出包。
2.  一致性——通过保留标准的退出包，我能够以一种快速(多图表性能报告)的方式比较进入信号的有效性。

出口被处理了，所以我可以专注于入口——我的想法流现在只依赖于入口信号。那么，在我测试了所有合理的技术、基本面和这些信号的组合之后，我在哪里产生这些进场的想法呢？

我是一个技术人员，所以我承认我对价格行为有偏好，但对我来说，我总是喜欢看图表来寻找新的进场想法。我让自己沉浸在一个符号中，然后改变时间框架，或者在同一张图表上配对几个时间框架，也许添加一两个指标，看看它是否给我展示了什么新的东西。

*   一旦我得到一些看起来可能是可重复模式的东西，
*   我在图表上寻找一些*心理*条目。
*   我试图找到例子来证明**我的信号是错误的，也就是说进场信号表现很差。**
*   然后，我会看看是否有一个不同的区间，一个额外的指标，或者一些 OHLC 模式可以把这个坏的条目从组合中去掉。
*   我寻找过滤器，使我发现的模式更加可靠。

记住，要想有一个有效的策略*，你不想过多地限制你的交易*；你需要一个*坚实的条目数量*，这不仅是为了增加更大超额收益的可能性，也是为了增加你的样本量和统计显著性。

如果你一个月有一笔交易，你很容易连续 5 笔交易亏损 6 个月。如果你大约每小时有一笔交易，如果你还在 6 个月的亏损中交易，那么你比我更勇敢。

当我在图表中看不到任何新的东西时，我该去哪里呢？我有几个最喜欢的信号想法，如果你给他们一个机会，我保证你会大大提高你的想法流。

*   我浏览流行的图表标记，新的指标想法，寻找我没有像其他人那样经常交易的符号，浏览我在宏观层面上注意到的普遍情绪或偏见。也许每隔一个图表是一个比特币到 50k 的图表，也许我不同意，可以利用这一点。
*   **股票和商品的技术分析:**(杂志，或者网站——Traders.com)这是我绝对喜欢的一个。你不仅会得到新鲜的图表和观点，而且它们总是有一个新的指标(或对旧指标的新看法)。
    他们有不同的市场和符号，这总是有助于开发一个新的想法。大多数问题实际上都有一个策略，可以转换到你熟悉的任何平台上。
    从这里开始，看看它是否能给你一些不同的想法。
*   **书籍:**我从*真的*旧的交易书籍中找到很多新的想法；我特别喜欢拉里·威廉姆斯或比尔·威廉姆斯的作品。他们在这里有一些永恒的模式，虽然从技术的角度来看这不是一个新鲜的视角，但他们经常提供不同的视角。这些旧书中有许多是完整的瑰宝，新书也非常有用(Bean、Chan、Davey、Prado、Pruitt 是我最喜欢的作者)。
*   归档:当我在开发一个新策略时，如果它不完全符合我的预期，但仍然有利可图，我会将它归档。我将它和它的性能指标一起保存在一个大数据库中，以便以后我可以带着新的东西回来。
    如果我在寻找一个新的想法，我有时会从那些看起来不太可行的策略开始，看看我是否错过了什么。老实说，我已经能够改进我存档的大多数**策略，只要稍后带着新的见解回来。改进后，并不是所有的都符合我的要求，但是很多都符合！没有什么比挽救一个几乎被扔进垃圾桶的改良回收项目更好的了。
    我还鼓励你回顾一下你现有的“强大”策略列表，看看你是否能改进那些已经符合你的规格的策略。**

**重要的不是你在哪里发现新想法，而是你持续不断地产生新想法。这些资源激励我寻找新的进入方式，但是你的可能完全不同！**

**我还想澄清一点，这不是一部印第安纳·琼斯电影，我们也不是在这里寻找圣杯——我们的目标是产生**超额回报**的**新**策略，以及与现有阿尔法模型的 ***负相关*** 。**

**如果你把足够多的这些信号结合起来，它很有可能成为一个革命性系统的组成部分。不过有一点是肯定的，如果不尝试新的(或循环的)想法，你的阿尔法技能将永远不会增长。把自己放在那里；创造一些新的大胆的东西，你永远不知道——它可能是**你的** *圣杯*系统中的一个成分。**

## ****结论****

**虽然新的想法是你持续发展的原材料，但有许多方法可以提高底线，例如，增加新的、稳健的交易策略。我发现即使是最好的策略也往往非常简单。**

**虽然没有人知道 RenTec 的信号是什么样的，但我想至少它们都是以非常简单的方式开始的。它们都必须从某个地方开始，我鼓励你也这样做，牢记这些目标。**

* * *

**编辑注:QuantInsti 尊重作者的选择和偏好，但我们绝不认可、支持或建议本文中的任何品牌。这些观点完全是作者的观点。我们更喜欢并提倡使用 Python 进行量化交易。T3】**

 ***<small>免责声明:本文提供的所有数据和信息仅供参考。QuantInsti 对本文中任何信息的准确性、完整性、现时性、适用性或有效性不做任何陈述，也不对这些信息中的任何错误、遗漏或延迟或因其显示或使用而导致的任何损失、伤害或损害负责。所有信息均按原样提供。</small>***