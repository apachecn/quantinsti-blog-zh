# 鞅交易策略:简要指南

> 原文：<https://blog.quantinsti.com/martingale/>

作者:Chamundeswari Koppisetti

我们经常听说在赌场游戏中的鞅策略，每次输钱后都要加倍下注。这些鞅策略能否应用到交易中，增加交易者的收益？

在这篇博客中，我们将通过以下主题来关注**鞅**及其在交易策略中的应用。

*   [什么是鞅？](#what-is-martingale)
*   [鞅是如何工作的？](#how-does-martingale-work)
*   [鞅中的条件期望](conditional-expectation-in-martingale)
*   [鞅交易策略](#martingale-trading-strategy)
*   [什么是反鞅？](#what-is-anti-martingale)
*   [python 中的鞅 vs 反鞅交易策略](#martingale-vs-anti-martingale-trading-strategy-in-python)

## 什么是鞅？

随机变量是一个未知值或一个函数，它为每个可能的试验取一个特定值。它可以是离散的，也可以是连续的。下面我们考虑离散随机变量来解释鞅。

鞅是随机变量序列 M1，M2，M3… Mn，其中

E [Mn+1|Mn] = Mn，n -> 0，1，…，n+1 🡪 (1)

以及 E [|Mn+1|] < ∞，

其被解读为 Mn+1 的期望值，假定 Mn 的值等于 Mn，即期望值保持不变

对于采用不同值 x1、x2、x3 的随机变量，其概率分别为 p1、p2 和 p3，期望值计算如下:

E[M] = x1 * p1 + x2 * p2 + x3 * p3，简单来说，期望与算术平均值相同。

**注**:鞅总是相对于一些信息集和一些概率测度来定义的。如果与过程相关的信息集或概率被改变，过程可能不再是鞅。

## 鞅是如何工作的？

考虑一个简单的游戏，你掷一枚公平的硬币，如果结果是正面就赢一美元，如果是反面就输一美元。

在这个游戏中，要么正面要么反面的概率总是一半。所以，win 的平均值等于 *(1) +* (-1) =0，这意味着你不能通过玩多轮游戏来系统地赚取任何额外的钱(尽管随机的收益或损失仍然是可能的)。

因此，以上满足鞅性质，即在任何特定的一轮中，无论前几轮的结果如何，你的总收入预计保持不变。

## 鞅中的条件期望

鞅定义中等式(1)左侧的表达式称为“条件期望”。条件期望(也称为条件均值)就是在一组先决条件发生后计算出的平均值。

随机变量 X 相对于变量 Z 的条件期望被定义为(新的)随机变量 Y = E(X|Z)

## 鞅交易策略

鞅交易策略是将亏损交易的敞口或投资规模翻倍。由于你的预期长期回报还是一样的，(价格下跌时亏损，价格上涨时盈利)，这个策略可以通过在价格下跌时逢低买入，降低你的平均进场价格来实现。因此，即使在一系列亏损交易后，如果发生了盈利交易，它会收回所有损失，包括最初的交易金额，因为它会产生 2^p=∑ 2^p-1+1 利润。

***鞅的利与弊:*** 优点之一是，随着交易者在每次亏损交易后投资规模翻倍，该策略有助于弥补亏损并产生利润，提高净收益。然而，主要的缺点是，如果你在没有止损限制的情况下增加投资规模。

**注意:**如果公司破产，你可能会失去全部资本，或者如果长期来看机会没有改善，你可能会持续亏损，导致无法弥补的资金减少，需要额外的资本。

## 什么是反鞅？

在反鞅策略中，当价格朝着有利可图的方向移动时，投资规模加倍，当出现亏损时，投资规模减半。这样做的目的是希望股票会继续上涨，这在动力驱动的市场中是有效的。

***反鞅的利与弊:*** 反鞅系统的主要优点是在不利条件下风险最小，因为在亏损时交易量不会增加。尽管有优势，反鞅也不会带来利润，如果有长期亏损的交易。因此，进场信号应该准确计算，以确保亏损不超过盈利。

在下一节中，我们将在 python 中构建鞅和反鞅策略。如果你不知道从哪里开始学习 python，你可以试试我们的 Python [课程](https://quantra.quantinsti.com/course/python-trading-basic)或者 python [手册](https://www.quantinsti.com/python-basics-handbook)。

## python 中的鞅与反鞅交易策略

我们使用苹果(AAPL)调整后的收盘价数据已经超过 6 个月了。这些数据来自雅虎财经网站，存储在一个 csv 文件中。想知道如何下载金融数据，可以去看看这个[博客](/stock-market-data-analysis-python/)。

### 读取股票数据

2019 年半年度(7 月至 12 月)调整收盘价数据已下载