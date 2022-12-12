# Fama French 五因素模型及其应用

> 原文：<https://blog.quantinsti.com/fama-french-five-factor-asset-pricing-model/>

**本文原载于 Quants 门户网站。*T3】*

由鲁杰科·穆萨鲁尔瓦

风险和收益之间的关系一直是讨论和研究的话题。投资者和投资经理寻求量化风险的金融模型，并将风险转化为对预期股本回报率的估计(穆林斯，1982)。这篇文章将关注并讨论 Fama French 5 因素模型及其应用。

本文将从讨论理论和模型的起源开始。随后将讨论何时以及如何实施和应用该模型。

最终可以看出，Fama-French 五因素模型比以前的模型有所改进，但仍有一些缺点和可以改进的地方。

* * *

## ****背景和历史****

证券定价的不同方法和模型以及由此确定资本投资的预期回报的方法和模型多年来已经得到了改进和发展。

最初，在 1964 年，单因素模型也被称为资本资产定价模型被开发出来。这个单一因素就是贝塔，据说贝塔说明了一只股票相对于市场的波动程度。比市场波动更大的股票具有更高的贝塔系数，因此风险和回报也更高(DeMuth，2014)。

1993 年，Fama 和 French 提出了三因素模型，其中两个额外因素是规模和价值(如账面市值比)。三因素模型是对 CAPM 的重大改进，因为它调整了优于大盘的趋势。

但是，它没有解释一些异常现象，也没有解释与盈利能力和投资特别相关的预期回报的横截面变化(ValueWalk，2015)。

Fama-French 五因素模型增加了两个因素，即盈利能力和投资，这是因为有证据表明三因素模型是一个不适合预期回报的模型，因为它的三个因素忽略了与盈利能力和投资相关的平均回报的大量变化(Fama 和 French，2015)。

* * *

## ****法玛法 5 **因子模型**T5】的应用****

**Fama-French 五因素模型的理论起点是股息贴现模型，因为该模型表明股票今天的价值取决于未来的股息。Fama 和 French 利用股利贴现模型从中得到两个新的因素，投资和盈利能力(Fama 和 French，2014)。**

**Fama French 模型的实证测试旨在解释在规模、B/M、盈利能力和投资方面产生巨大利差的投资组合的平均回报。**

*   **首先，该模型适用于根据规模、B/M、盈利能力和投资形成的投资组合。要解释的投资组合收益来自产生该因子的各种改进版本。**
*   **其次，在解释与模型未针对的主要异常相关的平均回报方面，将五因素模型的表现与三因素模型的表现进行了比较(Fama and French，2014)。**

**随着盈利能力和投资因素的增加，五因素模型时间序列回归具有以下等式:**

****R<sub>it</sub>—R<sub>Ft</sub>= a<sub>I</sub>+b<sub>I</sub>(R<sub>Mt</sub>—R<sub>Ft</sub>+s<sub>I</sub>SMB<sub>t</sub>+h<sub>I</sub>HML<sub>t</sub>+R<sub>I</sub>RMW<sub>t</sub>+c****

 **其中:

*   R <sub>ft</sub> 是其中一个投资组合在 t 月的回报率
*   R <sub>Ft</sub> 是无风险利率
*   Rm - Rf 是资本加权股票市场和现金之间的收益差
*   SMB 是小股票减去大股票的收益差(即规模效应)
*   HML 是廉价股票减去昂贵股票的收益差(即价值效应)
*   RMW 是利润最高的公司减去利润最低的公司的收益差
*   CMA 是保守投资减去激进投资的公司的收益差(AQR，2014)

回归测试的目的是观察五因素模型是否捕捉到变量的平均回报，并查看哪些变量彼此正相关或负相关，此外还确定回归斜率的大小以及所有这些因素如何与股票价值的平均回报相关并影响股票价值的平均回报。

Fama 和 French (2014)所做的测试表明，当盈利能力和投资因素被添加到等式中时，价值因素 HML 对于描述平均回报是多余的，对于唯一感兴趣的是异常回报的应用，可以使用四或五因素模型，但是如果除了异常回报之外，投资组合倾斜也是感兴趣的，那么最好使用五因素模型。

结果还表明，Fama-French 五因素模型解释了规模、价值、盈利能力和投资组合的预期回报的 71%至 94%的横截面方差。

事实证明，旨在捕捉平均股票回报的规模、价值、盈利能力和投资模式的五因素模型比三因素模型表现更好，因为它减少了无法解释的异常平均回报。

新的模型表明，最高的预期回报是由规模小、盈利和价值公司获得的，没有重大的增长前景(Fama 和 French，2014)。

然而，Fama-French 五因素模型的主要挫折是，它未能捕捉到小型股票的低平均回报，这些股票的回报表现类似于那些尽管利润率低但投资很多的公司，并且该模型的表现与其因素的定义方式无关(Fama 和 French，2015)。

* * *

## ****结论****

与以前的模型相比，Fama French 5 因子模型仍有待证明是一种改进，但它为将来进一步开发更好的模型留下了空间。

大多数投资者仍然使用著名的三因素模型，但是人们开始使用这种方法似乎需要几年时间，因为行业人员总是心存疑虑。

从 Fama 和 French 所做的实际工作来看，在这种方法在经验证据中证明自己之前，使用其他因素模型似乎对投资者最有利。

如果你也对发展终身技能感兴趣，这些技能会帮助你提高交易策略。在这个 [algo 交易课程](https://www.quantinsti.com/epat)中，你将接受统计学&计量经济学、编程、机器学习和量化交易方法的培训，因此你精通每一项在量化&算法交易中出类拔萃所必需的技能。现在就了解更多关于 EPAT 的课程吧！

* * *

**参考文献**

*   AQR，2014 年。我们的模型达到了六个，并通过冗余节省了价值。[在线]见:[https://www . aqr . com/cliffs-perspective/our-model-goes-to-six-saves-value from-the-redundancy-by-way](https://www.aqr.com/cliffs-perspective/our-model-goes-to-six-and-saves-value-from-redundancy-along-the-way)[2015 年 6 月 5 日访问]
*   DeMuth，p .，2014 年。Fama & French 的新 5 因素模型是怎么回事？神秘的新因素诉福布斯，[在线]可在以下网址查阅:[http://www . Forbes . com/sites/phildemuth/2014/01/20/whats-up-with-Fama-frenchs-new-5-factor-model-the-mystery-new-factor-v/](http://www.forbes.com/sites/phildemuth/2014/01/20/whats-up-with-fama-frenchs-new-5-factor-model-the-mysterious-new-factor-v/)[2015 年 6 月 6 日查阅]
*   法玛，E 和法国，k，2015。用五因素模型剖析异常。社会科学研究网络。[在线]可在:[http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2503174](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2503174)[2015 年 6 月 5 日访问]
*   Fama，E 和 French，k，2014 年。五因素资产定价模型。社会科学研究网络。[在线]可在:[http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2287202](http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2287202)[2015 年 6 月 5 日访问]
*   穆林斯特区，1982 年。资本资产定价模型有效吗？哈佛商业评论。[在线]见:[https://HBR . org/1982/01/does-the-capital-asset-pricing-model-work](https://hbr.org/1982/01/does-the-capital-asset-pricing-model-work)[2015 年 6 月 6 日访问]
*   2015 年价值行走。五因素 Fama-French 模型:国际证据。[在线]见:[http://www . value walk . com/2015/05/the-five-factor-Fama-French-model-international-evidence/](http://www.valuewalk.com/2015/05/the-five-factor-fama-french-model-international-evidence/)[2015 年 6 月 7 日查阅]

* * *

*<small>免责声明:本客座博文中提供的观点、意见和信息仅属于作者个人，不代表 QuantInsti 的观点、意见和信息。本文中所做的任何陈述或共享的链接的准确性、完整性和有效性都不能得到保证。我们对任何错误、遗漏或陈述不承担任何责任。与侵犯知识产权相关的任何责任由他们承担。</small>T3】***