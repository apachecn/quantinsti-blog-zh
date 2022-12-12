# Julia 中的数据操作和可视化技术

> 原文：<https://blog.quantinsti.com/data-manipulation-visualization-using-julia/>

安舒尔·塔亚尔

在本文中，我们将研究 Julia 中的数据操作和可视化技术。然而，我不会进入每个函数的每个参数的细节，因为这个系列的目标是使用 Julia *作为工具*来实现我们的目标，即*构建和[回测交易策略](https://quantra.quantinsti.com/course/backtesting-trading-strategies)T5。所以，我们会继续关注这一点。*

如果你需要一个函数来解决你在编程时面临的任何特殊挑战，你可以参考它的详细文档。

本文分为以下几个部分:

*   [数据操作](#data-manipulation)
    *   [创建新的数据帧](#creating-new-dataframes)
    *   [索引和汇总数据](#indexing-and-summarising-data)
    *   [基本数学运算](#basic-mathematical-operations)
    *   [一般操作](#general-operations)
    *   [分组数据](#grouping-data)
    *   [处理缺失数据](#dealing-with-missing-data)
*   [导入和导出数据为 CSV 和 excel 文件](#importing-and-exporting-data-as-csv-and-excel-files)
*   [数据可视化](#data-visualization)
    *   [线图](#line-plot)
    *   [图的属性](#attributes-of-a-plot)
    *   [散点图](#scatter-plot)
    *   热图
    *   [直方图](#histogram)
    *   [饼状图](#pie-chart)
    *   [绘制数学函数](#plotting-mathematical-functions)
    *   [保存图形](#saving-plots)
    *   [动画剧情](#animated-plots)
    *   [用于在 Julia 中绘图的各种包](#various-packages-for-plotting-in-julia)

* * *

在这个 Julia 编程系列的前几篇文章中，我[介绍了语言](/julia-programming/)，并从 Julia 编程的[基本语法](/julia-syntax/)开始。你也可以去看看。

* * *

## 数据操作

无论何时使用任何编程语言，都需要理解处理大型异构数据集的数据结构。在 Julia 的世界里，它们被称为数据帧。

Julia 的 DataFrames.jl 包提供了一种结构化和操作数据的方法。

可以使用“Pkg”模块进行安装。

### 创建新的数据框架

这是一个创建新数据帧的示例。

<aside id="sidebar" role="complementary" class="grid-30 tablet-grid-30 hide-on-tablet hide-on-mobile">

<section class="widget search custom-search">

<form action="" method="get" class="hide-on-tablet hide-on-mobile"><input type="text" name="s" value="" aria-label="search" class="search-field-mobile" placeholder="Search in the blog..." required=""> </form>

</section>

 *<section class="custom-side-bar">

### 职业成长

*   [Industry](https://blog.quantinsti.com/tag/industry)
*   [Job position & Skill](https://blog.quantinsti.com/tag/jobs-skills)
*   [The trading desk is set with](https://blog.quantinsti.com/tag/trading-desk-setup)
*   [Success story](https://blog.quantinsti.com/tag/success-stories)
*   [EPAT Transaction Item](https://blog.quantinsti.com/tag/epat-trading-projects)

### 教程

*   [Automated transaction](https://blog.quantinsti.com/tag/automated-trading)
*   [Excel & R 进行交易](https://blog.quantinsti.com/tag/excel-r-for-trading)
*   [foreign exchange & password transaction](https://blog.quantinsti.com/tag/forex-crypto-trading)
*   [Machine learning](https://blog.quantinsti.com/tag/machine-learning)
*   [Mathematics and Econometrics](https://blog.quantinsti.com/tag/mathematics-econometrics)
*   [mean regression & risk management](https://blog.quantinsti.com/tag/mean-reversion-statistical-arbitrage)
*   [Python trades](https://blog.quantinsti.com/tag/python-for-trading)
*   [Popular transaction](https://blog.quantinsti.com/tag/sentiment-trading)
*   [Technical index](https://blog.quantinsti.com/tag/technical-indicators)

</section>

<section class="subscribe-custom">[![Algo Trading Course](img/b3edc2d04106cb34c8b09ce8d58c033e.png)](https://www.quantinsti.com/)</section>* </aside>

 **<footer id="footer" class="grid-container np-mobile">

### 关于

*   [QuantInsti](https://www.quantinsti.com/)
*   [Quantra](https://quantra.quantinsti.com/)
*   [蓝移](https://blueshift.quantinsti.com/)

### 活动和公告

*   [公告](https://blog.quantinsti.com/tag/announcements)
*   [网络研讨会](https://blog.quantinsti.com/tag/webinars)

### 快速链接

*   [联系我们](https://www.quantinsti.com/contact-us)
*   [隐私政策](https://www.quantinsti.com/privacy-policy)
*   [博客投稿](/blog-contribution-guidelines)

版权所有 2021[QuantInsti.com](https://www.quantinsti.com)保留所有权利。

[](javascript:void(0))</footer>

 *Our cookie policy*We use cookies (necessary for website functioning) for analytics, to give you the best user experience, and to show you content tailored to your interests on our site and third-party sites. By closing this banner, scrolling this page, clicking a link or continuing to use our site, you consent to our use of cookies. [Read more](https://www.quantinsti.com/privacy-policy#privacyPolicy)[Accept](javascript:;)****