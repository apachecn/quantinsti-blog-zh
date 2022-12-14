# 你的交易策略失败的 10 种方式

> 原文：<https://blog.quantinsti.com/ways-trading-strategy-fail/>

由苏尼尔·古格拉尼

算法交易试图消除我们交易时的情绪。我们提出交易策略，设定买卖资产的规则，并在部署前进行彻底测试。然而，在这个过程中我们会犯一些常见的错误。忽视它们会导致我们的策略悲惨地失败。

通过一系列的例子/测验，这篇文章涵盖了十种我们经常会犯的错误。这些例子基于算法交易的各个方面，如前瞻偏差、过度拟合、性能参数的误算等。

在本文中，我们将介绍以下内容:

*   [测验 1-2](#quiz-1-2)
*   [测验 3-4](#quiz-3-4)
*   [测验 5](#quiz-5)
*   [测验 6](#quiz-6)
*   [测验 7](#quiz-7)
*   [测验 8](#quiz-8)
*   [错误 9](#mistake-9)
*   [错误 10](#mistake-10)

完整博客的链接以 Google Colab 格式出现在博客的末尾，以防你想亲自尝试。

* * *

## **[竞猜 1-2](#quiz-1-2)**

下面是一个经过历史数据检验的交易策略。这里面有什么逻辑/技术错误吗？

*如果有，是什么？*

(时间段:2019 年 1 月 1 日至 2019 年 6 月 28 日，间隔:1 分钟，脚本:BANKNIFTY)

### **战略背后的理念**

*   如果(sma_short/sma_long)>long_ratio，则在开盘时买入，在下一分钟收盘时卖出
*   如果(SMA _ short/SMA _ long)< short _ ratio，则在开盘时做空，在下一分钟收盘时买入
*   注:出于演示目的，回报仅按百分比计算，不考虑该工具的最小可交易单位。