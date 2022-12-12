# 使用不同数据源的基本面和情绪分析

> 原文：<https://blog.quantinsti.com/fundamental-sentiment-analysis-data/>

由克里斯托夫·勒鲁和[雷希特·帕查内卡](https://www.linkedin.com/in/rekhit/)和
制作

价格和成交量历史的技术分析在当今不会单独削减它。当我们想要进行价值投资和/或衡量证券的内在价值时，我们需要对证券进行基本面分析。

为了进行基本面分析，我们需要数据，大量的数据。我们需要比率、财务报表、收益等形式的基本数据。除此之外，我们还可以使用宏观经济数据，如国内生产总值、失业率、消费者价格指数。

最近，金融新闻和推文被用于[情绪分析](/tag/sentiment-trading/)来帮助交易者做决定。

我们将研究每一种不同类型的数据，为它们找到合适的数据提供者，并用 Python 代码给出一个如何使用这些数据的例子。

所有代码示例都是在 Google Colab 中制作的，但是当然可以在任何 [jupyter notebook](/python-data-types-variables-tutorial/) 服务器或任何 python 环境中执行。

这篇文章的结构如下:

*   [基础数据](#fundamental-data)
*   [宏观经济数据](#macroeconomic-data)
*   [收益日历](#earnings-calendar)
*   [财经新闻数据](#financial-news-data)
*   [推特数据](#twitter-data)
*   [情感数据](#sentiment-data)

## 基本数据

基本面数据包括用于初步筛选公司财务状况的财务比率，例如，市盈率(PE)、市净率(PBV)、净资产收益率(ROE)、复合年增长率(CAGR)、流动比率、股息率等。

它还包括用于评估企业的核心财务报表，如资产负债表、损益表和现金流量表。这些有价值的数据可以很容易地从 Yahoo！当然，有一个 [Python 包](/installing-python-packages/)用于此，我们将使用 yahoofinancials。

其他著名的基础数据提供者(带有 python 包)是 Quandl 和 Intrinio。现在让我们看看如何检索这些信息。

### 财务比率