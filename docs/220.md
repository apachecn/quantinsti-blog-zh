# 黄金价格预测:使用 Python 机器学习的逐步指南

> 原文：<https://blog.quantinsti.com/gold-price-prediction-using-machine-learning-python/>

由[伊山·沙阿](https://www.linkedin.com/in/ishan-shah-18393828/)和[雷希特·帕查内卡](https://www.linkedin.com/in/rekhit/)

有可能预测黄金价格的走向吗？

是的，让我们使用[机器学习回归技术](https://quantra.quantinsti.com/course/trading-with-machine-learning-regression)来预测最重要的贵金属之一黄金的价格。

我们将创建一个[机器学习](https://quantra.quantinsti.com/course/introduction-to-machine-learning-for-trading)线性回归模型，该模型从过去的黄金 ETF (GLD)价格中获取信息，并返回第二天的黄金价格预测。

**GLD 是直接投资实物黄金的最大 ETF。** ( [来源](http://www.etf.com/GLD))

在我们使用 python 中的[机器学习来预测黄金价格的旅程中，我们将涉及以下主题。](/trading-using-machine-learning-python/)

*   [导入库并读取黄金 ETF 数据](#import-the-libraries-and-read-the-gold-etf-data)
*   [定义解释变量](#define-explanatory-variables)
*   [定义因变量](#define-dependent-variable)
*   [将数据分成训练和测试数据集](#split-the-data-into-train-and-test-dataset)
*   [创建线性回归模型](#create-a-linear-regression-model)
*   [预测黄金 ETF 价格](#predict-the-gold-etf-prices)
*   [绘制累积收益图](#plotting-cumulative-returns)
*   [如何用这个模型预测每日走势？](#how-to-use-this-model-to-predict-daily-moves)

* * *

## 导入库并读取黄金 ETF 数据

首先:导入实现这个策略所需的所有必要的库。