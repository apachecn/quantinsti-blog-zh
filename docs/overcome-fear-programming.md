# 克服对编程的恐惧

> 原文：<https://blog.quantinsti.com/overcome-fear-programming/>

![](img/51fb3eda315868c251d9dca71b5ded05.png)

由[米林德·帕拉德卡](https://www.linkedin.com/in/milind-paradkar-b37292107/)

你说你从来没有编程过？没听说过类和对象、数据帧、方法、继承、循环这样的词吗？你害怕编程吗？

不要！编程可以是有趣的、刺激的，一旦你开始学习编程，你们中的许多人会喜欢花几个小时编程不同的策略；你会喜欢看到你自己的代码在眨眼之间运行，并且会看到这些代码有多么强大。

算法交易(EPAT)课程中的[执行程序广泛使用 Python 和 R 编程语言来教授策略、回溯测试及其优化。让我们借助 R 来演示如何克服编程恐惧。这里有一些给新手程序员的建议。](https://www.quantinsti.com/epat/)

### **1)思考，让问题浮现在你的脑海中**

作为一个程序员新手，当你有一个任务要编码时，甚至在开始之前，花一些时间构思你想如何一步一步地解决它。简单地让问题在你的脑海中出现，尽可能多的问题。

**下面有几个问题:**可以从 google finance 下载 R 中的股价数据吗？如何删除 R 中的一列？如何计算指数移动平均线(EMA)？如何在 R 中画折线图？如何合并两个数据集？可以用 R 将结果保存在 excel 工作簿中吗？

### **2)谷歌问题寻找答案**

使用谷歌搜索看看你提出的问题是否有解决方案。我们来看第二个问题，如何删除 R 中的一列？我们在谷歌搜索中发布了这个问题，从下面的截图中我们可以看到，在谷歌显示的第一个结果中我们就有了解决方案。

![](img/ae877c98dbffb66dc35455a2fc1f8bdb.png)

r 是一个开源项目，网上有数百篇文章、博客、论坛、教程、Youtube 视频和书籍，它们将帮助你克服对编程的恐惧，让你从初学者过渡到中级水平，如果你渴望的话，最终成为专家。

下面的图表显示了新手和专家程序员在两个流行网站上发布的问题/帖子的数量。正如你所看到的，R 以超过 10，000 个问题/线程的成绩明显高居榜首。(来源:www.r4stats.com)

![](img/e473bdcf401a4286380d8be01961ac41.png)

**让我们在谷歌上搜索一下 QuantInsti 是否在 r 上发布了任何编程材料。**从谷歌搜索结果中可以看到，QuantInsti 在其网站上发布了高质量的内容，以帮助新手程序员在 r 上设计和模拟[量化交易策略](https://quantra.quantinsti.com/course/quantitative-trading-strategies-models)

![](img/48fe1b6ff1a1348320cc62a5ee331ecf.png)

### **3)使用 R 中的打印命令**

作为一名程序员新手，当你在互联网上遇到看起来复杂的代码时，不要害怕。如果您无法弄清楚代码到底是做什么的，只需复制 r 中的代码，您可以使用一个简单的“print”命令来帮助理解代码的工作。

还可以使用 Ctrl+Enter 来逐行执行代码，并在控制台中查看结果。

让我们以 QuantInsti 博客上发布的 MACD 交易策略为例。http://blog . quantin STI . com/an-example-of-a-trading-strategy-coded-in-r/

![](img/01c0584ae991bcd22901efc8cd7e6474.png)

我不确定第 9 行和第 11 行的命令是否有效。所以我简单地在第 10 行插入了一个 **print(head(returns))** 命令，在第 12 行又插入了一个。此后，我运行代码。下面是 r 的控制台窗口中显示的结果。

![](img/6a5d5b2822b42d5ccd7b1883d52a76a8.png)

returns = returns[' 2008-06-02/2015-09-22 ']命令只是修剪原始 NSEI。收盘价格回报系列。这个系列更早开始于 2007 年 9 月 17 日。该系列现在从 2008 年 6 月 2 日开始，到 2015 年 9 月 22 日结束。

### **4)使用 R** 中的 help()和 example()函数

人们还可以利用 R 中的 help()和 example()函数来理解代码，并学习新的编码方法。继续上面的代码，我不确定 ROC 函数在代码的第 9 行做了什么。

![](img/f0a069c751d9eca9673fb81e7a9d1327.png)

我使用了 help("ROC ")命令，R 显示了关于 ROC 函数的用法和参数的所有相关信息。

![](img/ac9e67317d6f51b85609235d404b02ab.png)

R 中有数百个附加包，这使得编程变得简单而强大。

下面是查看 R:https://cran.r-project.org/web/packages/available*包* by_name.html 中所有可用包的链接

### **5)给编程时间**

编程可能是一种非常有益的体验，我们希望您花一些时间来学习和磨练您的编程技能。下面是一个优秀程序员应该具备的一些基本特征的文字云。最好的建议是开始编程！！

![](img/3316ca717ebd16399a690ad094f6e90c.png)

### **下一步**

如果你想学习算法交易的各个方面，那就去看看算法交易(EPAT)中的 T2 高管课程。该课程涵盖了统计学&计量经济学、金融计算&技术和算法&定量交易等培训模块。EPAT 让你具备成为成功交易者所需的技能。[现在报名](https://www.quantinsti.com/epat/)！

**更新**

我们注意到一些用户在从雅虎和谷歌金融平台下载市场数据时面临挑战。如果你正在寻找市场数据的替代来源，你可以使用 [Quandl](https://www.quandl.com/) 来获得同样的信息。

作为一个新手程序员，你才刚刚起步。QuantInsti 的教师将教你用 R 和 Python 编程的不同方面。在整个课程中，你将学习不同的数据结构、类和对象、函数和许多其他方面，这将使你能够以最有效和最强大的方式编写算法交易策略。