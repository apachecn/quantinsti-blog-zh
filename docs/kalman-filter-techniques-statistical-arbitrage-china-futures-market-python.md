# 中国期货市场的卡尔曼滤波技术和统计套利

> 原文：<https://blog.quantinsti.com/kalman-filter-techniques-statistical-arbitrage-china-futures-market-python/>

与更发达的市场相反，套利机会并不容易实现，这表明对于那些寻找并能够利用它们的人来说，可能存在机会。这个项目利用[统计套利](/statistical-arbitrage/)和配对交易技术，专注于**中国期货市场**。

本文是作者提交的最后一个项目，作为他在 QuantInsti 的算法交易管理课程( [EPAT](https://www.quantinsti.com/epat) )的一部分。请务必查看我们的[项目页面](https://www.quantinsti.com/category/project-work-epat/)，看看我们的学生正在构建什么。

* * *

## 关于作者

**邢弢**计算机科学学士(LZU)，信息系统与管理科学硕士(北京大学)，通过 CFA 级考试。目前，他是房地产、土地和基础设施的投资经理。

交易是他的爱好之一。5 年来，他一直试图成为一名定量分析师，并渴望申请计算机金融方面的博士学位。

* * *

## 项目

该项目对利差运行[增强的 Dickey-Fuller](/augmented-dickey-fuller-adf-test-for-a-pairs-trading-strategy/) 检验，以从统计上确认该序列是否均值回复，对利差序列和利差序列的滞后版本计算[卡尔曼滤波器](/implementing-pairs-trading-using-kalman-filter/)回归，以便随后使用系数计算[均值回复的半衰期](https://quantra.quantinsti.com/course/python-mean-reversion-strategies-ernest-chan)。

* * *

## 项目动机

根据目前中国的交易规则，股票不能卖空。与更发达的市场相反，套利机会并不容易实现。这表明，对于那些寻找并能够利用这些机会的人来说，可能存在着机会。

因此，我决定使用统计套利和[配对交易](/pair-trading-strategy-excel-model/)技术来关注中国的期货市场。

* * *

## 战略思想

本项目实施的交易策略称为“[统计套利交易](https://quantra.quantinsti.com/course/statistical-arbitrage-trading)”，也称为“[配对交易](/pairs-trading-basics/)，这是一种反向策略，旨在从特定配对比率的均值回复行为中获利。

这种策略背后的假设是，显示协整特性的货币对的价差本质上是均值回复，因此如果价差显著偏离均值，将提供套利机会。

* * *

## 资料组

数据集将来自中国金融期货交易所(CFFEX)、上海期货交易所(SHFE)、大连商品交易所(DCE)和郑州商品交易所(ZCE)。

由于数据的可用性，来自上述四个交易所的所有每日数据将通过 [UQER 的 API](https://uqer.io/) 访问。交易策略将回测 678 天(2015 年 3 月 30 日至 2017 年 12 月 31 日)。

前 542 天(2015 年 3 月 30 日至 2016 年 11 月 14 日，占总周期的 80%)为样本内回测期，其余 136 天(2016 年 11 月 15 日至 2017 年 12 月 31 日，占总周期的 20 %)为样本外回测期。

**中国金融期货交易所**

CFFEX 是一家股份化交易所，致力于金融期货、[期权](/basics-options-trading/)和其他衍生品的交易、清算和结算。2006 年 9 月 8 日，经国务院和中国证监会批准，由上海期货交易所、郑州商品交易所、大连商品交易所、上海证券交易所和深圳证券交易所在上海设立了中国期货交易所。

**上海期货交易所** (SHFE)

SHFE 是根据相关规则和条例组建的。它是一个自我监管的实体，履行其章程和州法律法规中规定的职能。中国证监会对其进行监管。目前期货合约的标的**商品**，即:

*   黄金，
*   银色，
*   铜，
*   铝，
*   铅，
*   钢筋，
*   钢盘条，
*   天然橡胶，
*   燃料油和
*   锌上市交易。

**大连商品交易所** (DCE)

DCE 是经国务院批准，由中国证监会监管的期货交易所。多年来，通过有序经营和稳步发展，DCE 已经成为全球最大的农产品期货市场和最大的石油、塑料、煤炭、冶金焦、铁矿石期货市场。

它也是中国重要的期货交易中心。截至 2017 年底，共有 16 个期货合约和 1 个期权合约在 DCE 上市交易，包括

*   一号大豆，
*   豆粕，
*   玉米，
*   2 号大豆，
*   大豆油，
*   线性低密度聚乙烯(LLDPE)，
*   RBD 棕榈油精，
*   聚氯乙烯(PVC)，
*   冶金焦炭，
*   炼焦煤，
*   铁矿石，
*   鸡蛋，
*   纤维板，
*   黑板
*   聚丙烯(PP)，
*   玉米淀粉期货和
*   豆粕选项。

**郑州商品交易所** (ZCE)

ZCE 是国务院批准的第一个期货市场试点。目前，ZCE 上市的产品包括:

*   小麦(强筋小麦和普通小麦)，
*   早籼稻，
*   粳稻，
*   棉花，
*   油菜籽，
*   菜籽油，
*   菜籽粕，
*   白糖，
*   动力煤，
*   甲醇，
*   纯对苯二甲酸(PTA)和
*   平板玻璃。

这些产品构成了一个全面的产品系列，涵盖了国民经济的几个关键领域，包括农业、能源、化学工业和建筑材料。

* * *

## 选择这一特定战略领域的动机

我对中国未来市场的关注是出于以下主要原因:

*   首先，由于中国股市的非卖空限制，我们只能做多股票，这使得在中国不可能进行股票配对交易。因为我们做配对交易的时候，总是做多很少的股票，做空相关性高的股票。
*   更重要的是，在中国期货交易所运营的算法交易公司/策略非常少。我相信这会提供很好的机会，因为竞争很少。与更发达的市场相反，套利机会并不容易实现，这表明那些寻找并能够利用它们的人可能有机会。
*   最后但同样重要的是，UQER 提供了优秀的 API，通过它我可以访问中国四个期货交易所的所有每日主力合约数据。众所周知，高质量的数据在 algo 交易中起着至关重要的作用。当我们选择[市场](https://quantra.quantinsti.com/course/getting-market-data)和策略时，数据的可访问性是我们应该考虑的重要因素之一。

* * *

## 概述

1.  定义我们的符号对，从 UQER 下载相关价格数据，并确保为每个符号下载的数据长度相同。
2.  每一个可能的合同对都将进行协整测试。将执行一个 **ADF 测试**,这样，另一个假设是被测试的货币对是固定的。
3.  对价差进行扩展的 Dickey-Fuller 测试，以从统计上确认该系列是否均值回复。我们还会计算 spread 系列的**赫斯特指数**。
4.  对价差序列和价差序列的滞后版本运行**卡尔曼滤波**回归，以便随后使用系数计算**均值回复**的半衰期。
5.  计算交易信号的 Z 值，定义回测的进出 Z 值水平。

* * *

## 数据挖掘

#### ****从四个期货交易所获取每日主力合约数据。**T3】**

主合约的每日交易价格通过 UQER 的 API 获取。

*   前 542 天(2015 年 3 月 27 日至 2016 年 11 月 14 日，占总周期的 80%)为样本内回测周期，且
*   其余 136 天(2016 年 11 月 15 日至 2017 年 12 月 29 日，占总周期的 20%)为样本外回测周期。