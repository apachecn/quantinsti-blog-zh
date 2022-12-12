# 如何通过 Python 股票 API 获取历史行情数据

> 原文：<https://blog.quantinsti.com/historical-market-data-python-api/>

由克里斯托夫·勒鲁和[雷希特·帕查内卡](https://www.linkedin.com/in/rekhit/)拍摄

作为一个量化交易者，你总是在寻找创造和优化你的交易策略。回溯测试是这个过程中非常重要的一部分。对于回溯测试，访问历史数据是必要的。但是找到合适的历史价格数据来回溯测试你的交易策略是一项非常艰巨的任务。

虽然简单的谷歌搜索可以给你任何股票的收盘数据，但下载并为你的策略代码做好准备可能是一项任务。如果你正在创建一个需要许多不同资产类别的投资组合，那么所需要的时间将是巨大的。如果您只需运行几行代码并接收数据，不是更简单吗？

这个博客将会做到这一点。我们将研究免费和付费的解决方案，所有这些解决方案都有一个围绕其服务的易于使用的 Python Stock API 包装器。对于每种类型的解决方案，我们将查看哪种资产类型(股票、ETF、外汇、商品期货、期权、国债，甚至是[密码](https://quantra.quantinsti.com/course/crypto-trading-strategies-intermediate))。这些资源提供了关于如何以各种方式检索它的信息，当然还有 python 代码中的一个例子。

这篇文章的结构如下:

*   [使用 Python stock API 免费解决历史数据](#free-solutions-for-historical-data-using-python-stock-api)
    *   雅虎！财务-使用 Python 股票 API 获取数据
        * [使用 Python 股票 API 获取单个资产的数据](#getting-data-of-a-single-asset-using-python-stock-api)
        * [使用 Python 股票 API 获取多个资产的数据](#getting-data-of-multiple-assets-using-python-stock-api)
        * [使用 Python 股票 API 获取不同类型资产的数据](#getting-data-of-different-types-of-assets-using-python-stock-api)
        * [使用 Python 股票 API 获取不同时间频率的数据](#getting-data-with-different-time-frequencies-using-python-stock-api)
        * [从雅虎获取数据的注意事项！金融](#caveats-of-getting-data-from-yahoo-finance)
    *   [Quandl -使用 Python 股票 API 获取数据](#quandl-getting-data-using-python-stock-api)
        * [从 Quandl 获取数据的注意事项](#caveats-of-getting-data-from-quandl)
*   [获取免费历史数据的资源](#resources-to-get-free-historical-data)
*   [使用 Python 股票 API 对历史数据的付费解决方案](#paid-solutions-for-historical-data-using-python-stock-api)
    * [Alpha Vantage -使用 Python 股票 API 获取数据](#alpha-vantage-getting-data-using-python-stock-api)
    * [十二数据-使用 Python 股票 API 获取数据](#twelve-data-getting-data-using-python-stock-api)
*   [获取付费历史数据的资源](#resources-to-get-paid-historical-data)

* * *

## 使用 Python Stock API 免费解决历史数据

从正确的来源获取财务数据非常重要。虽然有许多免费的数据提供者，但你必须确保质量是好的。自由数据的问题是，在读数中可能会有一些不一致，或者有时几个字段也是如此。

因此，一旦检索到数据，就要对其进行检查。现在，让我们详细看看一些提供者。

* * *

## 雅虎！金融——使用 Python 股票 API 获取数据

雅虎！金融是雅虎网络的一部分，于 2017 年被出售给威瑞森媒体。

按月流量计算，它是美国最大的商业新闻网站，提供[财经新闻](https://quantra.quantinsti.com/course/financial-time-series-analysis-trading)、数据和评论，包括股票报价、新闻稿、财务报告和原创内容。

他们提供关于[加密货币](/getting-started-cryptocurrency-algorithmic-trading/)的[市场数据](https://quantra.quantinsti.com/course/getting-market-data)，常规货币，商品期货，股票和债券，基本面和期权数据，以及市场分析和新闻。

雅虎曾经有自己的官方 API，但这在 2017 年被关闭，它在 2019 年的某个地方重新活跃起来。

代码示例是在 Google Colab 中制作的，但是当然可以在任何 [jupyter notebook](/jupyter-notebook-tutorial-installation-components-magic-commands/) 服务器或本地 python 文件中执行(预先安装了依赖项)。我们将使用著名的 [matplotlib](/python-matplotlib-tutorial/) 来绘制我们的数据。

### 使用 Python stock API 获取单个资产的数据

首先，我们从检索单个 ETF 的每日历史价格数据开始，让我们以 SPDR 标准普尔 500 ETF 信托(SPY)为例，绘制这些数据。