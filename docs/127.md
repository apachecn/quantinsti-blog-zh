# 预测每日股票价格并自动执行每日交易策略[算法交易项目]

> 原文：<https://blog.quantinsti.com/algo-trading-epat-projects-8-february-2022/>

[https://www.youtube.com/embed/Rn1MpizWwNY?rel=0](https://www.youtube.com/embed/Rn1MpizWwNY?rel=0)

* * *

## 关于演示文稿

本次会议有两位我们尊敬的 EPAT 校友的项目陈述。首先是英国 Renato Votto 的“用随机森林分类器、技术指标和情绪数据预测每日股票价格”；其次是印度 Ujjwal Agrawal 的“如何实现期权日交易策略的自动化”。

* * *

### 项目 1:用随机森林分类器、技术指标和情绪数据预测每日股票价格

一个交互式程序，训练一个随机森林分类器，使用技术指标和 Twitter 帖子的[情绪](https://quantra.quantinsti.com/course/trading-using-options-sentiment-indicators)分数、[回溯测试](/backtesting/)交易策略并产生性能指标来预测特斯拉的每日价格。

该项目利用技术、范例和数据结构，例如:

*   函数式和面向对象编程
*   机器学习
*   情感分析
*   并发和并行处理
*   有向无环图
*   数据管道
*   幂等性

这个项目背后的意图是在一个程序中实现算法交易策略回溯测试的端到端工作流，该程序具有一个光滑的界面和一定程度的自动化，使得用户能够通过输入最少量的数据，部分甚至以交互的方式，来定制策略的细节和程序的输出。

这应该使程序可重用，这意味着很容易对不同的资产进行交易策略的回溯测试。此外，软件设计的模块化应该便于改变以使程序适应不同的需求(即不同的数据或 ML 模型)。

**项目代码**

该项目的完整代码可在 [Renato 的 Github 账户](https://github.com/renatovotto)上获得。

**演示幻灯片**

[//www.slideshare.net/slideshow/embed_code/key/ty5kgb3DRWT47i](//www.slideshare.net/slideshow/embed_code/key/ty5kgb3DRWT47i)

**[Predict daily stock prices with random forest classifier, technical indicators and sentiment data final](//www.slideshare.net/QuantInsti/predict-daily-stock-prices-with-random-forest-classifier-technical-indicators-and-sentiment-data-final "Predict daily stock prices with random forest classifier, technical indicators and sentiment data final")** from **[QuantInsti](//www.slideshare.net/QuantInsti)**

* * *

### 项目 2:如何自动化期权日交易策略

该项目的目的是自动化一个简单的策略，如需要复杂的回溯测试和定量分析以确定交易中的统计意义和定量优势的日内跨/扼杀。使用 Python 和 Excel 对指数期权进行回溯测试，以了解不同的冲击差异和止损。

该策略包括在早上的固定时间做空一个多空或扼杀，在收盘前的固定时间对两条腿设置止损并平仓所有或剩余头寸。

不会结转任何头寸，因为这是一种日内策略，有助于避免隔夜头寸出现任何大缺口。这种策略可以分为无方向性和趋势跟踪两种，因为它在这两种情况下都表现良好，只有当指数波动非常大，以之字形移动时，才会出现止损。

**演示幻灯片**

[//www.slideshare.net/slideshow/embed_code/key/gsb0m9xj7yBI1x](//www.slideshare.net/slideshow/embed_code/key/gsb0m9xj7yBI1x)

**[How to automate an options day trading strategy final](//www.slideshare.net/QuantInsti/how-to-automate-an-options-day-trading-strategy-final "How to automate an options day trading strategy final")** from **[QuantInsti](//www.slideshare.net/QuantInsti)**

* * *

## 提出者

### Renato Votto(来自英国的数据分析师)

<figure class="kg-card kg-image-card kg-width-wide">![Renato Votto pic](img/a4dc8b8c9467d5e9bd93254922fd055c.png)</figure>

Renato 真正喜欢并热衷于开发自动化软件，寻找复杂问题的算法解决方案并优化程序。他拥有量化优势，精通算法交易、量化开发、机器学习、数据工程、Python、C++和 SQL。Renato 拥有能源工程背景，是算法交易(EPAT)高管课程的毕业生。在进入 EPAT 大学之前，他还完成了机器学习和数据工程研究。

目前在天然气和电力市场办公室(OFGEM)担任分析师，主要从事定量分析和系统识别市场操纵的软件和工具的开发。

他是一个加密货币爱好者，一个狂热的摇滚听众，热爱编码，一个平庸的吉他弹奏者，当他在户外时，你可能会发现他在拍摄奇怪的照片。

### Ujjwal Agrawal(量化交易者和来自印度的企业主)

<figure class="kg-card kg-image-card kg-width-wide">![Ujjwal Agrawal pic](img/2f8f050fb330bd69c79c92deffb1a4a2.png)</figure>

Ujjwal Agrawal 是 CFA(特许金融分析师)三级考生，拥有浦那大学机械工程学士学位。他是奥里萨邦农产品加工业的业主，过去 4 年一直在印度市场做生意。全职管理一家企业和交易有时会变得很困难，这让他开始自动化自己的交易设置。完成 EPAT 课程后，在 QuantInsti 团队的无条件支持下，Ujjwal 现在已经完全实现了交易系统的自动化，并将全部时间投入到自己的业务中。

他的项目“盘中跨骑”是众多系统中第一个完全自动化的系统，现在他研究并组合不相关的系统，以最小的损失产生可观的回报。

* * *

本次会议于:
*2022 年 2 月 8 日星期二
东部时间上午 8:30 | IST 时间晚上 7:00 |新加坡时间晚上 9:30*