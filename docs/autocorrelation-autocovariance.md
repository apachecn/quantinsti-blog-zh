# 自相关和自协方差:计算、例子等等

> 原文：<https://blog.quantinsti.com/autocorrelation-autocovariance/>

何塞·卡洛斯·冈萨雷斯·田中

自相关和自协方差是金融时间序列计量经济学中最重要的指标之一。这两个函数都基于协方差和相关性度量。你会对他们了解更多。这本简单易学的基本指南将帮助你更好地了解 ARMA 模型。

*   [什么是自协方差？](#what-is-autocovariance)
*   [什么是自相关？](#what-is-autocorrelation)
*   [滞后零点的自协方差和自相关性是什么？](#what-are-the-autocovariance-and-autocorrelation-at-lag-zero)
*   [举例计算自协方差](#calculation-of-the-autocovariance-with-an-example)
*   [举例计算自相关](#calculation-of-the-autocorrelation-with-an-example)
*   [Python 中自协方差和自相关的计算](#computation-of-autocovariance-and-autocorrelation-in-python)
*   [用 Python 绘制自相关函数](#plot-the-autocorrelation-function-in-python)
*   [计算 R 中的自协方差和自相关性](#computation-of-autocovariance-and-autocorrelation-in-r)
*   [绘制 R 中的自相关函数](#plot-the-autocorrelation-function-in-r)
*   [什么是偏自相关？](#what-is-partial-autocorrelation)
*   [Python 和 R 中偏自相关的计算](#computation-of-partial-autocorrelation-in-python-and-r)

你可能遇到过自己试图学习自回归移动平均(ARMA)模型。然后，你开始看到大量使用协方差和相关性，但奇怪的是，你看到这两个词带有前缀" *auto"* ，你会感到害怕！

别担心，这篇文章会帮助你了解他们的细节。只要把注意力集中在文章上，一切都会好的！

* * *

## 什么是自协方差？

首先，你需要明白什么是[协方差和相关性](/covariance-correlation/)。请记住，协方差应用于 2 项资产。自协方差与协方差相同。

唯一的区别是自协方差应用于相同的资产，也就是说，你用相同的资产价格收益 X 来计算资产价格收益 X 的协方差，但是是从以前的时期。

这怎么可能？简单，来看看:

$$ \text{Cov(X,Y)} = \frac{\sum_{i=1}^{n}\left(X_{i}-\overline{X}\right)\left(Y_{i}-\overline{Y}\right)}{N-1}$$

其中 X 和 Y 可以分别是资产 X 和 Y 的收益。

现在，自协方差函数可以定义为:

$$ \gamma_{s} = \frac{\sum_{t=1}^{T}\left(r_{t}-\overline{r}\right)\left(r_{t-s}-\overline{r}\right)}{N-1}$$

其中:

*   \( \gamma_{s} \text{:滞后时间的自协方差" }s\text{"}。\)*   \( r_{t} \text{:资产价格在时间" }t\text{"}返回。\)*   \(r _ { t-s } \ text {:Asset price returns at time " } t-s \ text { " }。\)

* * *

## 什么是自相关？

简单来说，[自相关](/autoregression/)与相关函数相同！具体来说，自相关作为自协方差应用于同一资产。

检查相关和自相关(也称为序列相关)之间的差异如下:

$$ \text{Corr(X，y)} = \frac{\sum_{i=1}^{n}\left(x_{i}-\overline{x}\right)\left(y_{i}-\overline{y}\right)}
{
\ sqrt {
\left(\sum_{i=1}^{n} \左(x _ { I }-\ overline { x } \right)^2 \右)
\left(\sum_{i=1}^{n} \左(y _ { I }-\ overline { y } \right)^2 \右)
} }

= \frac{\sum_{i=1}^{n}\left(x_{i}-\overline{x}\right)\left(y_{i}-\overline{y}\right)}
{
\ sqrt {
\sum_{i=1}^{n} \左(x _ { I }-\ overline { x } \right)^2

其中:

*   \( \text{Cov(}X，Y \ text {:X \ text { and } Y . \)之间的协方差*   \( SD_{X} \text{:变量的标准偏差}\text{X}。\)*   \( SD_{Y} \text{:变量的标准偏差}\text{Y}。\)

现在让我们检查一下自相关性:

$$ \rho_{s} = \frac{\text{Cov}\left(r_t,r_{t-s}\right)}{\text{Var}\left(r_t\right)}$$

其中:

*   \( \rho_{s} \text{:滞后自相关" }s\text{"}。\)*   \( r_{t} \text{:资产价格在时间" }t\text{"}返回。\)*   \(r _ { t-s } \ text {:Asset price returns at time " } t-s \ text { " }。\)*   \(\ text { Var } \ left(r _ t \ right)\ text {:方差收益}。\)

你可能会问我们:

为什么是方差而不是不同滞后期收益的标准差的乘积？

你必须记住，ARMA 模型适用于平稳的时间序列。本题目属于[时间序列分析](/time-series-analysis/)。因此，假设价格回报，如果是平稳的，对于任何滞后都具有相同的方差，即:

$$ \text{Var}\left(r_t\right) = \text{Var}\left(r_{t-1}\right) = \text{Var}\left(r_{t-2}\right) = ... = \text{Var}\left(r_{0}\right) $$

* * *

## 滞后零点的自协方差和自相关性是什么？

有趣的问题和简单的答案！我们先来看前者:

$$ \gamma_{0} = \frac{\sum_{t=1}^{T}\left(r_{t}-\overline{r}\right)\left(r_{t-0}-\overline{r}\right)}{N-1} = \gamma_{0} = \frac{\sum_{t=1}^{T}\left(r_{t}-\overline{r}\right)\left(r_{t}-\overline{r}\right)}{N-1} = \gamma_{0} = \frac{\sum_{t=1}^{T}\left(r_{t}-\overline{r}\right)^2}{N-1} $$

你能猜出最后一部分像什么吗？
它是价格收益的方差！

因此，滞后 0 时收益的自协方差就是收益的方差。

你现在能猜出在滞后 0 时收益的自相关性是多少吗？让我们用公式来找出:

$$ \rho_{0} = \frac{\text{Cov}\left(r_t,r_{t-0}\right)}{\text{Var}\left(r_t\right)} = \frac{\text{Cov}\left(r_t,r_{t-0}\right)}{\text{Var}\left(r_t\right)} = \frac{\text{Cov}\left(r_t,r_{t}\right)}{\text{Var}\left(r_t\right)}$$

从上面的代数计算中，我们知道同一个变量的协方差就是它的方差，因此我们得到:

$$ \rho_{0} = \frac{\text{Cov}\left(r_t,r_{t}\right)}{\text{Var}\left(r_t\right)} = \frac{ \text{Var}\left(r_t\right)} {\text{Var}\left(r_t\right)}$$ $$ \rho_{0} = 1 $$

因此，滞后 0 的任何资产价格回报的自相关函数总是 1。

* * *

## 用实例计算自协方差

到目前为止你可能一直在想:
*为什么用“s”下标定义自协方差和自相关？*
*伟大的问题！*

让我们解释一下:实际上，上面定义的自协方差公式是一个允许计算不同滞后的自协方差的函数。自相关函数也是如此。

*迷茫？放心吧！我们掩护你！*

让我们来看一个例子，让你的思想清楚这个概念！我们将举例说明如何计算微软价格收益在滞后 1 时的自协方差。我们将使用上面显示的自协方差函数。

假设我们对微软的价格有以下回报:

| 第一天 | 第二天 | 第三天 | 第四天 | 第五天 | 第六天 | 第七天 | 第八天 | 第九天 | 第 10 天 |
| 5% | 1% | -2% | 3% | -4% | 6% | 2% | -1% | -3% | 4% |

假设我们想计算滞后 1 时的自协方差。你需要到第 10 天的收益，以及到第 9 天的 1 期滞后收益。

因此，第 10 天和第 9 天的退货数据结构如下:

| 可变的 | 第一天 | 第二天 | 第三天 | 第四天 | 第五天 | 第六天 | 第七天 | 第八天 | 第九天 | 第 10 天 |
| \( r_{t} \) | 5% | 1% | -2% | 3% | -4% | 6% | 2% | -1% | -3% | 4% |
| \( r_{t-1} \) |  | 5% | 1% | -2% | 3% | -4% | 6% | 2% | -1% | -3% |

你能看出这两个变量之间的区别吗？
第二个是第一个滞后的 Xt。

现在，由于两个变量有不同的维度(第一个变量有 10 个观察值，而第二个变量有 9 个)，我们将使用第二天以后的数据。

因此，我们的数据如下:

| 可变的 | 第二天 | 第三天 | 第四天 | 第五天 | 第六天 | 第七天 | 第八天 | 第九天 | 第 10 天 |
| \( r_{t} \) | 1% | -2% | 3% | -4% | 6% | 2% | -1% | -3% | 4% |
| \( r_{t-1} \) | 5% | 1% | -2% | 3% | -4% | 6% | 2% | -1% | -3% |

这两个变量之间的协方差将是滞后 1 时收益的自协方差。

你能做到，对吗？
查一下我们上一篇文章中给出的例子。

在你准备用铅笔和纸之前，让我们告诉你一些重要的事情。

记住自协方差公式:

$$ \gamma_{s} = \frac{\sum_{t=1}^{T}\left(r_{t}-\overline{r}\right)\left(r_{t-s}-\overline{r}\right)}{N-1}$$

如果你注意细节，你会发现两个收益的平均收益是一样的，在我们的例子中，第 10 天和第 9 天的收益是一样的。正如我们之前解释的，自协方差和自相关函数只适用于平稳的时间序列。

因此，不仅方差而且平均值对于整个跨度都是唯一的值。这就是为什么任何价格回报滞后的均值都是一样的。

微软价格回报的平均值是 1.1%。让我们按照程序来计算自协方差:

| 可变的 | \( r_{t} \) | \( r_{t-1} \) | \(\ left(r _ { t }-\ overline { r } \ right)\) | \(\ left(r _ { t-1 }-\ overline { r } \ right)\) | \(\ left(r _ { t }-\ overline { r } \ right)\)\(\ left(r _ { t-1 }-\ overline { r } \ right)\) |
| 第二天 | 1% | 5% | -0.100% | 3.900% | -0.004% |
| 第三天 | -2% | 1% | -3.100% | -0.100% | 0.003% |
| 第四天 | 3% | -2% | 1.900% | -3.100% | -0.059% |
| 第五天 | -4% | 3% | -5.100% | 1.900% | -0.097% |
| 第六天 | 6% | -4% | 4.900% | -5.100% | -0.250% |
| 第七天 | 2% | 6% | 0.900% | 4.900% | 0.044% |
| 第八天 | -1% | 2% | -2.100% | 0.900% | -0.019% |
| 第九天 | -3% | -1% | -4.100% | -2.100% | 0.086% |
| 第 10 天 | 4% | -3% | 2.900% | -4.100% | -0.119% |

自协方差只是最后一列值的总和除以(N-1，等于 8)，结果为-0.046%。

* * *

## 举例计算自相关性

让我们进行同样的练习，计算第 10 天微软价格收益在滞后 1 时的自相关性。自相关是自协方差除以方差。我们给出了您需要的确切提示:到第 10 天为止，微软价格回报的方差为 0.121%。

让我们按照代数公式并使用数字来计算自相关:

$$ \rho_{s} = \frac{\text{Cov}\left(r_t,r_{t-s}\right)}{\text{Var}\left(r_t\right)}=\frac{-0.046%}{0.121%}$$ $$ \rho_{s} = -0.38 $$

* * *

## Python 中自协方差和自相关的计算

在我们开始这一部分之前，让我们告诉你一些事情。我们已经计算了滞后 1 时微软价格回报的自协方差和自相关性。我们不可能在滞后 2、滞后 3 等时进行计算。我们留给你的是一个练习！

在 [Python](https://quantra.quantinsti.com/course/python-for-trading) 或任何其他编程语言中，当你需要计算这两个重要的指标时，你将需要在许多滞后时间计算它们，而不仅仅是 1，就像我们之前所做的那样。

因此，请记住，我们将使用 Python 来计算自协方差和自相关函数，即不同滞后的自协方差和自相关函数。

首先，让我们导入必要的库来使用: