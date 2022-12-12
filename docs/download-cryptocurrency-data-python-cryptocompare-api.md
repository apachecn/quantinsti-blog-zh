# 使用加密比较 API 下载 Python 中的加密货币数据

> 原文：<https://blog.quantinsti.com/download-cryptocurrency-data-python-cryptocompare-api/>

何塞·卡洛斯·冈萨雷斯·田中

Python 中如何使用 Cryptocompare API 下载加密货币数据？Cryptocompare 是一家加密货币市场数据提供商。这个博客解释了你如何用超级简单的步骤来做到这一点，并让你随时准备应用它！

如果你正在向算法交易或加密货币世界迈出第一步，那么这篇文章就是为你准备的！

我们涵盖:

*   [为什么选择 CryptoCompare？](#why-cryptoCompare)
*   [导入库](#import-libraries)
*   [设置 API 密钥](#set-api-key)
*   [获取所有加密货币报价机](#fetch-all-cryptocurrency-tickers)
*   [以特定频率下载历史数据](#download-historical-data-with-a-specific-frequency)
*   [下载比特币每小时历史数据](#download-bitcoin-hourly-historical-data)
*   [绘制数据](#plot-the-data)

* * *

## 为什么选择 CryptoCompare？

CryptoCompare 允许用户从大多数重要的加密交易所获得实时价格，绘制图表并进行市场研究分析。它还允许我们获得有限的免费数据进行下载。这就是我们在这篇文章中要做的。

* * *

## 导入库

首先，让我们在我们的 [Jupyter 笔记本](/jupyter-notebook-tutorial-installation-components-magic-commands/)中安装 cryptocompare 库: