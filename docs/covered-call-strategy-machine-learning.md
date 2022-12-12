# 使用机器学习的覆盖呼叫策略

> 原文：<https://blog.quantinsti.com/covered-call-strategy-machine-learning/>

由[瓦伦·迪瓦卡](https://www.linkedin.com/in/varun-divakar-b862a667/)

投资者利用备兑买入期权在持有股票的同时赚取一些小利润。交易员想要[创建备兑买入期权](/write-covered-call-strategy-in-python/)的主要原因是，交易员看好标的股票，并希望长期持有，但该股票不支付任何股息。该股预计将在未来 6 个月内上涨，与此同时，你可能希望将该股作为抵押品，卖出一些看涨期权，将溢价收入囊中。但这种策略有风险，即如果股票上涨，那么你的股票将在到期时被赎回。因此，你可以以较低的溢价买回期权，而不是等待期权到期。

利用[机器学习进行交易](https://quantra.quantinsti.com/course/introduction-to-machine-learning-for-trading)的方法有很多种。在这篇博客中，我将尝试向你展示如何通过使用简单的[决策树算法](/use-decision-trees-machine-learning-predict-stock-movements/)来预测期权溢价的短期变动，并在持有股票的同时赚取差价。

有关不同[期权交易](/basics-options-trading/)策略的更多详情，请访问 https://quantra.quantinsti.com/

让我给你看一个例子，用漂亮的期货。Nifty50 是一个印度指数，由来自不同行业的 50 只股票组成。

为了执行上面讨论的策略，我们假设我们持有期货合同，然后我们试图在相同的基础上卖出一个看涨期权。为了做到这一点，我们在由[各种希腊文](/the-greeks-in-options-delta-gamma-theta-and-vega/)组成的过去数据上训练一个[机器学习](/trading-using-machine-learning-python/)算法，比如选项的 IV、delta、gamma、vega、theta 作为输入。因变量或预测将在第二天的收益中进行。每当算法产生卖出信号时，我们就写调用。首先，让我们导入必要的库。

## **导入库**