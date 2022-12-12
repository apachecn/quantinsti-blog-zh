# 用 Python 的雅虎财经库下载期货数据

> 原文：<https://blog.quantinsti.com/download-futures-data-yahoo-finance-library-python/>

何塞·卡洛斯·冈萨雷斯·田中

你必须做的第一件事就是学会用 Python 下载期货数据。这个博客解释了完整的过程，并帮助您了解所需的各个步骤。

[期货交易](/futures-trading/)本来就是杠杆交易。在投资组合中使用杠杆时必须小心谨慎。管理杠杆的一个好方法是用算法进行交易，这就是这篇博客的重要性。

它包括:

*   雅虎！财务库安装
*   [导入库](#import-libraries)
*   [下载期货数据](#download-futures-data)
*   [绘制收盘价](#plot-the-close-prices)
*   [下载多个期货的数据](#download-data-for-multiple-futures)
*   [绘制倍数期货数据](#plot-multiples-futures-data)

* * *

## 雅虎！财务库安装

Python 是世界上最简单的编程语言之一。Python 使得新手更容易更快地掌握编程技能。建立自己的 Python 交易系统也很容易。

我们将使用一个 [Jupyter 笔记本](/jupyter-notebook-tutorial-installation-components-magic-commands/)。我们来编码吧！如果你还没有在你的机器上安装这个著名的库，这里有代码: