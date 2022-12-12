# 使用 Python 中的未平仓权益、展期交割和 FII/DII 活动进行趋势分析

> 原文：<https://blog.quantinsti.com/trend-analysis-open-interest-rollover-fii-dii-python/>

由阿舒托什·戴夫

2020 年第一季度是二战后最具挑战性的时期之一。地缘政治原因导致的油价暴跌和新冠肺炎全球疫情是主导主题。

金融市场充当着风向标的角色，为我们提供了对全球经济整体情绪的反映。这些情绪不仅反映在价格上，也反映在其他指标上，如未平仓利息、展期百分比、FII/DII 交易。

这篇博客旨在分析 Nifty 50 的上述三个重要指标，Nifty 50 是印度领先的广泛市场指数。我们将使用 Python 来进行这一分析。

**内容:**

*   [导入 Python 库](#importing-python-libraries)
*   [俏皮 50 期货](#nifty-50-futures)
*   [获取数据](#getting-the-data)
*   [分析价格变动](#analysing-the-price-movement)
*   [分析价格与交易量](#analysing-price-vs-volume)
*   [未结利息分析](#open-interest-analysis)
*   [翻车分析](#rollover-analysis)
*   [FII/DII 活动分析](#fii-dii-activity-analysis)

## **T3】**

在用 Python 开始任何分析之前，我们需要导入所需的库。我们将使用 pandas、NumPy 和 Matplotlib 等流行的库(用于可视化)。

让我们现在导入它们。