# 价格行为交易概念

> 原文：<https://blog.quantinsti.com/price-action-trading/>

凯文·帕特劳

价格行动是一种已经存在很久的交易方法，在不断发展的交易社区中非常流行。许多散户和机构交易员经常利用价格行为交易策略来预测和分析金融资产的短期价格变动，这是通过分析历史价格行为和趋势来实现的。

通过这篇文章，我们将试图加深我们对价格行为交易概念的理解，我们也将试图识别在真实图表中形成的价格行为模式。

本文分为以下几个部分:

*   [什么是价格行动交易？](#what-is-price-action-trading)
*   [价格行为交易的流行](#popularity-of-price-action-trading)
*   [不同类型的图表](#different-types-of-charts)
*   [了解市场趋势](#understanding-the-market-trend)
*   [支撑和阻力的概念](#concept-of-support-and-resistance)
*   [趋势线的概念](#concept-of-trendlines)
*   [使用 Python 识别支撑和阻力](#identifying-support-and-resistance-using-python)
*   [价格行为交易的利与弊](#benefits-and-drawbacks-of-price-action-trading)

* * *

## 什么是价格行动交易？

价格行动策略是一种交易实践，其中最重要的是研究价格随时间的运动和行为，而不是依赖各种技术指标来预测即将到来的趋势并建立相关的长/短头寸。

虽然大多数价格行为交易者不使用普通的交易指标，如移动平均线、布林线或 RSI，但这不是强制性的做法，一些交易者可能更喜欢在他们的交易设置中包括几个指标以提高准确性。

然而，赋予纯价格变动的权重总是远远大于赋予技术指标的权重。

价格行为交易者寻找的最受追捧的交易机构是那些提供最佳风险回报比的机构。

这些设置可能包括各种各样的新兴突破形态(如:趋势线、旗帜、三角形、楔形)，趋势反转形态，如头肩底、双顶、双底等。

除此之外，能够识别关键水平，如支撑位和阻力位，并对各种烛台模式分析有一个基本的了解也是非常重要的。

* * *

## 价格行为交易的流行

绝大多数市场参与者坚信，预测资产价格几乎是不可能的，因为有太多的因素可以影响这些资产的价格。事实上，无论市场周期和趋势如何变化，都很难开发出一个完美的系统。

然而，据观察，利用过去的价格数据和一些基本的技术分析知识，有时可以正确地估计近期的资产价格变动。这正是价格行动交易策略发挥作用的地方。

价格行为的核心非常简单，即使是新手也很容易掌握。另一个优点是，它在股票、商品等多种资产类别中运行良好，甚至可以应用于外汇和加密市场。

但是让这个策略在交易社区中脱颖而出的是这样一个事实，它帮助交易者在根据他们自己对价格行为的解释来寻找交易机会时感觉更有控制力。

与此同时，该策略还在以下方面提供了大量的灵活性，如[头寸规模](https://quantra.quantinsti.com/course/position-sizing-trading)、风险/回报管理、进场和出场点等，当一个人遵循标准的基于规则的交易系统时，这是不容易实现的。

* * *

## 不同类型的图表

一个简单的折线图提供了一项资产在特定时间内的收盘价数据的汇总。下面是一个显示苹果每日收盘价数据的简单折线图示例。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![charting platform for price action trading](img/64da789b8eb53cb8c51ecd811adde2a8.png)

<figcaption>Charting platform: tradingview.com</figcaption>

</figure>

折线图的一个缺点是，其他重要的数据，如当天的开盘价，最高和最低交易价格，根本不包括在图表中。

因此，为了更好地进行技术分析，蜡烛图/条形图比折线图更受欢迎，因为它们包含并代表了这些额外的数据，可以跟踪这些数据来精确地研究特定时间段内的价格变动。

下面是一个蜡烛图，也显示了每个时间间隔的开盘价、最高价、最低价和收盘价。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![candlestick chart for price action](img/a427670e561a992a7eee741b0d484c59.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

清楚地理解如何使用烛台来代表 OHLC 数据是能够发现和阅读图表中的价格行动所必需的。如果你想了解更多关于烛台的信息，你可以访问此[链接](/candlestick-patterns-meaning/)。

* * *

## 了解市场趋势

### **下降趋势**

每当价格运动的方式，它形成了一系列的较低的高点和较低的低点时，与它以前的摆动高点和摆动低点相比，我们可以说，资产价格有一个持续的下降趋势或熊市趋势。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![downtrend for price action](img/b718ba390de1dccb96e179c772cfb4e3.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

### **上升趋势**

当价格持续移动，形成一系列更高的高点和更高的低点，与之前的高点和低点相比，我们可以得出结论，资产价格处于上升趋势或看涨趋势。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![uptrend price action](img/3dd31fccb405a8c4bdfcb3cab16d96e0.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

### **横盘走势**

如果波动高点和波动低点在一段时间内倾向于在一个水平范围内移动，这个趋势可以被称为横向趋势。在盘整阶段，价格通常会横向移动。这些阶段可能会导致现有上升趋势/下降趋势的延续，有时甚至可能预示着整体趋势的逆转。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![sideway trend for price action](img/315a6735f7d7d9438c5aedec7c3a22bc.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

* * *

## 支撑和阻力的概念

阻力是一个重要的水平，在这个水平上，可用供应往往会超过总体需求，这阻止了价格的进一步上涨。在大多数情况下，价格将面临巨大的抛售压力，当价格到达这一区域时，可以预期会出现大幅下跌。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![resistance zone for price action](img/b4125381e1660300a43b17aec5f88781.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

上图显示了 2300 价格带附近的一个非常强的阻力区。

相反，**支撑位**是一个重要的价格水平，在这里对资产的需求超过了可获得的供给，这阻止了价格的进一步下跌。在大多数情况下，该资产在关键支撑位似乎被低估，导致投资者/交易者买入该资产并创建新的多头头寸。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![support and resistance for price action](img/5f8e91e2b06f906c06b2671b926f838f.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

上图显示了 160 价格带附近的一个关键支撑/需求区和 360 价格带附近的一个强阻力区。当价格进入这些重要区域时，观察价格趋势如何强烈反转。

* * *

## 趋势线概念

趋势线是一条直线，连接至少三个波动高点或三个波动低点，并向未来延伸，作为支撑或阻力区。大多数适用于支撑区和阻力区的属性也可以在趋势线上看到。

<figure class="kg-card kg-image-card kg-width-full kg-card-hascaption">![trendline for price action](img/3a4d4dc702d8d6d8638be5563b83405a.png)

<figcaption>(Source: tradingview.com)</figcaption>

</figure>

上图向我们展示了一条连接 2015 年至 2020 年波动高点的趋势线。正如我们所观察到的，价格处于下降趋势，因为它在此期间形成了一系列较低的高点和较低的低点。

* * *

## 使用 Python 识别支持和阻力

我们方法的第一步是导入必要的库并获得资产数据。

我们将关注 HINDUNILVR 的收盘价格数据。用于执行支撑和阻力分析的 NS。我们从雅虎获取资产的 OHLCV 数据。融资并将其存储在如下所示的数据框架中。