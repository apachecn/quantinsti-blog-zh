# 实际有效汇率(REER):公式，计算，等等

> 原文：<https://blog.quantinsti.com/real-effective-exchange-rate/>

由[查尼卡·塔卡](https://www.linkedin.com/in/chainika-bahl-thakar-b32971155/)

实际有效汇率是计算本国货币相对于其他国家货币的强势的有用工具。当 REER 增加时，它表明贸易竞争力的损失。

因此，实际有效汇率的计算有助于您通过考虑包括贸易竞争力在内的有利于贸易的因素来决定交易哪种货币。

REER 是制定政策和考察一个国家经济增长时考虑的一个重要指标。国际货币基金组织、世界银行、国际清算银行等机构提供了 133 个国家的 REER 分析。

让我们通过这篇博客发现一些更有趣的事实和实际有效汇率(REER)的用法，这篇博客包括:

*   [实际有效汇率简介](#a-brief-introduction-to-real-effective-exchange-rate)
*   [REER 公式](#formula-for-reer)
*   [用实例计算 REER](#calculation-of-reer-with-example)
*   [REER 兑实际汇率](#reer-vs-real-exchange-rate)
*   [REER 对即期汇率](#reer-vs-spot-exchange-rate)
*   [汇率类型](#types-of-exchange-rates)
*   [REER 的工作](#working-of-reer)
*   [常见问题解答](#faqs)
    *   低于 100 的 REER 意味着什么？
    *   更高的 REER 意味着什么？
    *   REER 适应通货膨胀了吗？

* * *

## 实际有效汇率简介

实际有效汇率(REER)是一国货币相对于一篮子其他货币的加权平均值。这种汇率主要用于确定一个国家的货币相对于其他主要货币的价值。

REER 对一篮子货币中每种货币的通胀影响进行了调整，使其能够衡量一种货币实际可以购买的东西。

过去，REER 被用来理解一种货币相对于其他货币以及自身的表现。这是一个重要的[量化工具](https://quantra.quantinsti.com/)，交易者应该认识到这一点。

实际有效汇率有助于衡量一种货币相对于其贸易伙伴是否升值。实际有效汇率在短期内是不稳定的，对于日内交易来说不是一个好的[指标](/indicators-build-trend-following-strategy/)，但它可以用于具有长期视角的[外汇交易策略](/forex-trading-strategies-backtesting-webinar-14-august-2018/)。

* * *

## REER 公式

回到 REER 计算，一个国家的 REER 可以通过取其与贸易伙伴之间的双边实际汇率(RER)的平均值，然后使用每个伙伴的贸易分配进行加权，然后根据通货膨胀进行调整来计算。

对于初学者来说，这可能听起来有点复杂，但我们将通过一个例子来讨论 REER 的计算，这将进一步简化。

首先，让我们看看计算实际有效汇率(REER)的公式，它是由印度储备银行给出的:

$$\prod_{i=1}^n = [(e/e{i}) (P/P{i})]^wi$$

在哪里，

*   n =篮子中的国家数量
*   i =篮子中的第 I 种货币
*   e 是印度卢比对国际货币基金组织指数形式的特别提款权的汇率
*   ei 是以指数形式表示的外币“I”对国际货币基金组织特别提款权(SDR)的汇率
*   wi 是外币“I”的权重
*   Pi 是与外币“I”相关的国家的消费者价格指数
*   p 是印度的消费者价格指数(CPI)(印度用 CPI 来调整 REER)

* * *

## REER 的计算举例

为了计算 6 个国家中每个国家的 REER，我们需要找到以下内容:

*   6 个国家各自的权重
*   每个国家的汇率
*   所有 6 个国家的通货膨胀率

### 6 个国家各自的权重

我们将通过获取六个篮子国家的贸易量数据来计算“权重”。

2021-22 财年，印度最大的贸易伙伴及其贸易总额(进出口总额)以十亿美元计如下:

| **排名** | **国家** | **出口** | **进口** | **贸易总额** |
| one | 美国 | Seventy-six point one one | Forty-three point three one | One hundred and nineteen point four two |
| Two | 中国 | Twenty-one point two five | Ninety-four point one six | One hundred and fifteen point four one |
| three | 阿拉伯联合酋长国 | Twenty-eight point one | Forty-four point eight | Seventy-two point nine |
| four | 沙特阿拉伯 | eight | Thirty-four | forty-two |
| five | 瑞士 | One point two one | Sixteen point nine | Eighteen point one one |
| six | 德国 | Eight point two one | Thirteen point six nine | Twenty-one point nine |

<small>* in billions of US dollars for the financial year 2021-22</small> <small>Source: [Wikipedia](https://en.wikipedia.org/wiki/List_of_largest_trading_partners_of_India)</small>

与这六个国家的贸易总额=(119.42)+(115.41)+(72.90)+(42.00)+(18.11)+(21.9)= 3897.4 亿美元。使用贸易总额参数计算这六个国家的贸易权重如下:

| **国家** | **重量** | **重量百分比(%)** |
| 美国 | 119.42/389.74 | Thirty point six |
| 中国 | 115.41/389.74 | Twenty-nine point six |
| 阿拉伯联合酋长国 | 72.90/389.74 | Eighteen point seven |
| 沙特阿拉伯 | 42/389.74 | Ten point seven |
| 瑞士 | 18.11/389.74 | Four point six |
| 德国 | 21.9/389.74 | Five point six |

### 每个国家的汇率

现在让我们看看六种篮子货币对印度卢比的汇率。为了简化计算，我将每种外币的汇率定为每 10 个印度卢比。例如，10 元人民币= 113.90 印度卢比。

| **国家** | **与印度卢比的汇率** |
| 美国 | Eight hundred and fifteen point zero nine |
| 中国 | One hundred and thirteen point nine |
| 阿拉伯联合酋长国 | Two hundred and twenty-two point zero five |
| 沙特阿拉伯 | Two hundred and sixteen point seven |
| 瑞士 | Eight hundred and twenty-three point six six |
| 德国 | Seven hundred and eighty-seven point five nine |

<small>* exchange rates as of 2022</small>

在这种情况下，我们将欧元/印度卢比视为德国的汇率。在计算汇率值时，这些机构会考虑一段预定时间内的平均汇率。这样做是为了应对外汇市场的每日波动。

此外，实际有效汇率(REER)值通常由国际货币基金组织、各国央行和其他国际机构发布，滞后约 3 个月。

### 通货膨胀

现在让我们看看 6 个篮子货币和印度的通胀数据。

| **国家** | **消费价格通胀** |
| 美国 | Two hundred and ninety-six point one seven one |
| 中国 | One hundred and three point one |
| 阿拉伯联合酋长国 | One hundred and eight point six two |
| 沙特阿拉伯 | One hundred and seven point six one |
| 瑞士 | One hundred and four point seven seven |
| 德国 | One hundred and eighteen point eight |
| 印度 | One hundred and seventy-four point three |

<small>* CPI values as of 2022</small> <small>Source: [Trading Economics](https://tradingeconomics.com/)</small>

现在，我们将按照以下步骤计算中国的 REER:

*   汇率成分= e/e1 = 1/113.90 = 0.00877
*   通货膨胀部分= P/P1 = 174.3/103.1(印度/中国的 CPI) = 1.690
*   汇率部分和通货膨胀部分的乘积= 0.00877 * 1.690((e/E1)*(p/p1)]^w1)= 0.0148
*   最终的实际有效汇率成分=[(e/E1)*(p/p1)]^w1=(0.0148)^0.296= 0.31875

同样，我们可以对篮子里的其他国家和印度进行这种计算。此外，你可以计算其他国家的 REER。

例如，通过取所有其他国家的实际有效汇率(REER)分量的乘积，我们得到印度相对于一篮子六个国家的总 REER。

此外，如果你发现印度/你自己国家的 REER 与另一个国家相比有所增加，这意味着出口到特定国家的产品变得昂贵，而进口产品变得便宜。因此，这意味着现在的贸易竞争力不大。

同样，当一个印度/你自己的国家的 REER 与另一个国家相比下降时，这意味着该国的出口变得更便宜，进口变得更贵，这也意味着该国的贸易竞争力增加了。

* * *

## REER 对实际汇率

现在让我们看看 REER 和实际汇率之间的区别。

| **REER** | **实际汇率** |
| REER 是将一个国家的货币价值与其主要贸易伙伴货币的加权平均值进行比较的衡量标准或工具。 | 实际汇率衡量一个国家的商品相对于另一个国家、一组国家或世界其他地区的商品的价值，以当时的名义汇率计算。 |
| 实际有效汇率的公式是:REER = i=1n [(e/ei) (P/Pi)]wi在哪里，
n 是篮子中国家的数量I 是篮子里的第 I 个货币e 是印度卢比对国际货币基金组织指数形式的特别提款权的汇率
ei 是以指数形式表示的外币“I”对国际货币基金组织特别提款权(SDR)的汇率
wi 是外币“I”的权重
Pi 是与外币“I”相关的国家的消费者价格指数p 是印度的消费者价格指数，印度用这个指数来调整 REER

 | 实际汇率的公式是:
e x P / P*
在哪里，
e =每单位本国货币的外币，即名义汇率
P/P* =国内价格/国外价格(以外币表示)

 |

* * *

## REER 对即期汇率

即期汇率是在可能的最早起息日(涉及有价格波动的资产的金融交易日期)将一种货币兑换成另一种货币进行交割的当前价格。

虽然即期汇率是在最早的日期交割，但大多数即期交易的标准结算日是交易日之后的两个工作日。

即期汇率是当前的市场价格，而 REER 是一种货币相对于其贸易伙伴的价值指标。

* * *

## 汇率的类型

有四种主要的汇率可供选择。这四种汇率是:

*   固定汇率
*   浮动汇率
*   钉住浮动
*   美元化

让我们一个一个地看看每一个的关联性。

### 固定汇率

可直接兑换成其他货币的汇率称为固定汇率。在固定汇率的情况下，特定国家的中央银行将该国的官方汇率与另一国的货币或黄金挂钩。

这样，固定汇率制度将货币价值保持在一个狭窄的货币区间内。例如，丹麦克朗(DKK)与欧元挂钩，中间价为 746.038 克朗兑 100 欧元。

### 浮动汇率

当今大多数国家采用的最常见的制度是浮动汇率。最常见的例子是日元、美元、欧元和英镑都属于这一类。

由于汇率浮动，各国中央银行频繁干预，以避免贬值或升值。

### 钉住浮动

在浮动汇率下，这些货币与特定的价值或货币范围挂钩。挂钩浮动要么定期调整，要么是固定的。

钉住浮动也被认为是爬行带。爬行区间是允许围绕区间中心值波动的速率。此外，固定浮动会定期调整。调整是以受控方式或以预先通知的速率完成的。

例如，香港允许资本自由流动，并将汇率与美元挂钩。

### 美元化

美元化是一个术语，通常用于特定的非美国国家使用美元作为他们的国家货币。例如，津巴布韦在 2009 年引入了美元化，以减少恶性通货膨胀。然而，津巴布韦中央银行[最近排除了津巴布韦回归美元化的可能性。](https://www.bloomberg.com/news/articles/2022-02-07/zimbabwe-s-central-bank-rules-out-return-to-dollarization)

* * *

## REER 的工作

在计算实际有效汇率时，将一国货币的相对贸易差额与指数中的每个现有国家进行比较，以计算权重。

汇率决定了特定货币相对于指数中其他主要货币的价值。

REER 表示货币的均衡价值。它衡量国家的贸易能力和进出口状况。

由于 REER 表示消费者购买非本国产品或进口产品所支付的价格，因此它包括进口产品所涉及的关税和其他交易成本。

一国货币的 REER 可以通过加权该国与其贸易伙伴之间的双边汇率平均值来计算，使用的是双方的贸易分配。

根据消费物价指数或单位劳动力成本计算 REER 是最常见的做法。国际货币基金组织根据几乎所有国家的消费价格指数计算 REER，而大多数工业国家则采用基于单位劳动力成本的 REER。

它检测贸易流动的潜在因素，并考虑国际价格的变化。

* * *

## 常见问题

有一些关于实际有效汇率的常见问题，我们在这里回答其中一些。

### REER 低于 100 意味着什么？

低于 100 的 REER 指数让出口保持竞争力，进口变得昂贵。

### 更高的 REER 意味着什么？

更高的 REER 意味着进口更便宜，出口更贵。

### REER 适应通货膨胀了吗？

是的。在计算 REER 时，REER 根据通货膨胀进行了调整。

* * *

### 结论

实际有效汇率主要用于确定一个国家的货币相对于其他主要货币的价值。因此，REER 被用来理解一种货币相对于其他货币的表现，以及过去相对于自身的表现。

这就是量化分析师在交易或投资一种货币之前使用 REER 来确定其强度的原因。

如果您希望进一步了解汇率以及如何在市场中获得优势，您可以报名参加[外汇自动交易](https://quantra.quantinsti.com/learning-track/automated-trading-in-forex-markets)的学习课程。

您将获得关于外汇估值方法的知识，如购买力平价、名义有效汇率和实际有效汇率，并学习使用 Python 在交互式经纪人和 FXCM 上自动进行外汇交易。此外，完成本学习课程后，您可以创建自己的交易系统或使用基于云的交易解决方案。一定要去看看。

* * *

*<small>免责声明:股票市场的所有投资和交易都涉及风险。在金融市场进行交易的任何决定，包括股票或期权或其他金融工具的交易，都是个人决定，只能在彻底研究后做出，包括个人风险和财务评估以及在您认为必要的范围内寻求专业帮助。本文提到的交易策略或相关信息仅供参考。</small>T3】*