# 为了准确测量结果而进行回溯测试时要避免的常见错误

> 原文：<https://blog.quantinsti.com/common-mistakes-backtesting/>

扎克·奥克斯

回溯测试是*而不是*本身就是一个**开发工具**，目标不是看你能做出多大的权益曲线。一个**好的**回测应该是指 ***它如何准确地反映实时交易*** ，*而不是*系统看起来如何'*好*。

在这篇博客中，我们将讨论:

*   [构建回溯测试](#building-backtests)*   [佣金、复杂功能和细节](#commissions-complications)*   [战略逻辑](#strategy-logic)*   [对抗回测偏差](#backtest-bias)*   [回溯测试清单](#checklist)

所以，你刚刚写完你的自动交易算法，你正在接近关键时刻——最初的回溯测试。你已经花了几个小时来构建这个，所以你真的希望股票曲线至少是正斜率，并且希望没有任何大的下降。

这一时刻肯定会定义过去几个小时在这方面的工作，甚至可能用一条足够好的曲线改变你的未来——一条直的、绿色的、向上倾斜的线会带来纯粹的快乐，而一条起伏的黑/红线会降低你的自我价值。比方说这个例子，你的结果是一个巨大的、二次的、向上倾斜的曲线，它不会停止。

这条曲线将带你到应许之地，将粉碎你路上的任何人，并且对它的辉煌不做任何道歉。我们都见过其中的一个——但是我们怎么能*确定*这个回溯测试是有效的，并且我们可以在这些结果的范围内期待一些东西呢？

有一些技巧可以帮助我们确定回溯测试准确的概率。首先，我们从力学和假设开始。任何没有对**佣金和滑点**建模的回溯测试都不应该被认为是策略的代表。在一些系统中，这是一个无关紧要的差异，但在其他系统中，它可以彻底改变曲线**——我见过它反转一些刷单系统的权益曲线。**

**那么多少才够呢——佣金通常是相当标准的费用表，所以简单地让他们是什么。这个东西并不复杂，但是不要忽略这些小细节是非常重要的。**

**滑点可能会更复杂一些，但在[期货](https://quantra.quantinsti.com/course/futures-trading)中，市场订单的常见估计是每边 12.50 美元，我想我对股票/ETF 使用每边 0.02-. 10 美元。我通常发现这是一个相当高的估计——但是重要的是根据你的执行历史来建模*。***

**就我个人而言，我使用了其中的一半——但那只是因为我用我的执行对系统进行了广泛的测试，并且发现 6 美元更接近我实现的滑点。回顾一些你的实时交易与纸上交易的对比，看看它们相对于 sim 账户的填充情况。**

**这里不是所有的工具都相等，所以如果你发现 ES(埃米尼标准普尔 500 期货合约)有大约 12.50 的滑点，这并不意味着 KC(咖啡期货合约)也会有大约 10 美元——我见过 KC 交易在非流动性区间填补 40 美元。注意您测试的仪器，最简单的方法是比较现场报告和 sim 报告。这件事很值得你花时间去做。**

**所以一旦滑点和佣金被准确地或保守地包含在你的[回溯测试](https://quantra.quantinsti.com/course/backtesting-trading-strategies)中，让我们来看看实际的策略逻辑。有几个组件在现实生活中非常有效，但也会产生一些奇怪的回溯测试结果——其中之一就是百分比跟踪止损。**

**在许多回溯测试引擎(TradeStation、NT8、TradingView)中，默认设置是基于棒线而不是在棒线内进行回溯测试。这意味着一个长输入将简单地查看 OHLC 值来确定你的 trailstop 是否被执行——也就是说它将寻找一个大于你的% Trailing 的高收盘值。**

**在实时交易中，你会发现你的头寸可以在任何给定的棒线内被执行数百次，在任何收盘价之前——这可以显示大得多的*平均获利交易，从而显示平均交易，以及总体表现。***

**在回溯测试中，引擎会假设绿色条是一个向上的运动，而不是许多小的向上运动的集合，并带有回溯。你所要做的就是将任何 30 分钟图与相同区间的 1 分钟图进行比较——中间有很多波动，很可能触发你的跟踪止损(很可能会生效)。**

**那么，我们如何对抗大多数测试引擎的这种回溯测试(事后诸葛亮)偏见呢？让我们看看。**

**在 TradeStation/Multicharts 中，您可以在属性中启用条内回溯测试(或 MC 中的条放大镜)(并将分辨率设置为分、秒或分笔成交点)，这将使您对系统的性能有一个更好的了解。这将需要更长的时间，但它更准确。**

**如果没有任何设置可以做到这一点，比如在 Python 中，你可以运行 2 个数据集。一个作为信号间隔，例如，说 30M 条-以信号通知条目；另一个跟踪止损百分比，比如一个点，30 秒或 1 米棒线。**

**我将分享一个 IB 系统，在这个系统中，我用 5 秒钟的小节来测试我的测试站，而不是用 60 米的小节来测试入口——实现这样的东西是确保你自己的回溯测试尽可能准确的最可行的选择。**

**![A close up of a map

Description automatically generated](img/21d630b96f5234a68168194a81b61594.png)**

**![A close up of a map

Description automatically generated](img/73c87db069c0d0760d657e70c68e57bf.png)**

**如果您无法实现更小的间隔棒线(可能没有任何 1 米或秒棒线或可用数据)，那么您可以实现一个固定的目标值来代替您的跟踪止损，从而为您提供一个估计的最坏情况填充值。**

**我发现它的表现肯定比止损差，但不是对你的盈利交易完全不合理的估计。一个例子是用 90 - 120 美元的固定目标替换或简单地组合一个+100 美元的 PNL 止损点。**

**试着对自己诚实，你通常会在哪里被阻止。这也可以通过使用 100 美元的 pnl 跟踪止损点**和**来完成，也许是 150 美元的固定目标，限制你的上涨，计算机可以根据假设来创造。**

**假设你已经做到了这一步，你的回溯测试肯定会变得更加实际。通过[回溯测试](/backtesting/)，我仍然发现一些事情会导致一些疯狂的结果，所以我将它们列出来进行最后的回顾。**

*   **同一酒吧内的入口和出口**
*   **周末/隔夜套利(+运气)**
*   **小样本量(包括至少 100 个交易和尽可能多的制度)**
*   **细价股票/流动性差的名字**
*   **宇宙包括杠杆 ETF/ETN**
*   **全域包括冗余符号(QQQ 和 TQQQ)**

## ****结论****

**如果你已经完成了这个基本的清单，你会对你看到的任何结果感觉更好。如果你从来没有考虑过这些，请不要气馁。请记住，大多数职业基金经理不会跑赢市场——也不会试图跑赢市场。他们专注于提高而不是达到特定的绩效水平。**

**为什么这么多都依赖于一个单独的折线图，我们怎么能确定一个漂亮的回溯测试不仅仅是我们的计算机在跟我们开一个残酷的玩笑呢？按照这个清单进行工作将会有很大的改进。**

**在我们复习的时候，让我们试着记住回溯测试的*目的*。我*永远不会*相信一个漂亮的回溯测试——即使是最好的假设也会有太多的假设。让我们重新定义一下什么是漂亮的回溯测试，同时，让我们记住它们只是一个验证工具，而不是开发工具。**

**你可以通过对历史数据进行回溯测试来提高交易成功的可能性。Quantra 的这个关于[回溯测试交易策略](https://quantra.quantinsti.com/course/backtesting-trading-strategies)的课程正是你从交易中获得最大收益所需要的。从基本步骤、数据、规则、风险管理等方面学习一切。立即注册！**

**-交易愉快！**

* * *

**编辑注:QuantInsti 尊重作者的选择和偏好，但我们绝不认可、支持或建议本文中的任何品牌。这些观点完全是作者的观点。我们更喜欢并提倡使用 Python 进行量化交易。T3】**

 ***<small>免责声明:本文提供的所有数据和信息仅供参考。QuantInsti 对本文中任何信息的准确性、完整性、现时性、适用性或有效性不做任何陈述，也不对这些信息中的任何错误、遗漏或延迟或因其显示或使用而导致的任何损失、伤害或损害负责。所有信息均按原样提供。</small>***