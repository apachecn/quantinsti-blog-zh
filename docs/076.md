# Python 中的机器学习分类策略

> 原文：<https://blog.quantinsti.com/machine-learning-classification-strategy-python/>

由[伊山·沙阿](https://www.linkedin.com/in/ishan-shah-18393828/)和[雷希特·帕查内卡](https://in.linkedin.com/in/rekhit)

在你继续构建你的机器学习分类算法之前，有一个问题要问你。你知道泰斯拉和网飞有什么共同点吗？

两家公司的首席执行官都更愿意遵循古老的“首要原则”哲学。

第一性原理的哲学是什么？

简单来说，当面对一个困难的问题时，你会试着把它分解成更小的部分，然后从那里开始。

但是，为什么在一个关于机器学习分类模型的博客中会提到“第一原则”？

在我们用 python 建立分类模型之前，我们将从基础开始，这就是机器学习。让我们看看博客里为我们准备了什么:

*   [机器学习简介](#a-brief-on-machine-learning)
*   [机器学习是如何在交易中实现的？](#how-is-machine-learning-being-implemented-in-trading)
*   [](#how-is-machine-learning-being-implemented-in-trading)[机器学习中的分类算法是什么？](#what-is-a-classification-algorithm-in-machine-learning)
*   [机器学习中分类算法的类型根据分类任务](#types-of-classification-algorithms-in-machine-learning-according-to-classification-tasks)
*   [在 Python 中实现分类](#implementing-classification-in-python)
    *   [步骤 1:导入库](#step-1-import-the-libraries)
    *   [步骤 2:取数据](#step-2-fetch-data)
    *   [步骤 3:确定目标变量](#step-3-determine-the-target-variable)
    *   [步骤 4:创建预测变量](#step-4-creation-of-predictors-variables)
    *   [步骤 分类模型使用训练数据集](#step-5-test-and-train-dataset-split)
    *   [步骤 7:分类模型精度 _ Python 中的得分](#step-7-the-classification-model-accuracy_score-in-python)
    *   [步骤 8:预测](#step-8-prediction)
    *   [步骤 9:在 matplotlib 中绘制分类数据](#step-9-plotting-classification-data-in-matplotlib)

* * *

## **机器学习简介**

让我们来简单定义一下机器学习。机器学习为机器提供了基于过去的经验、观察和分析给定数据集中的模式来自主学习的能力，而无需显式编程。

为了分解它，早期的程序员使用显式编码机器应该做什么。以带动力转向的汽车为例。如果司机把方向盘转到右边，有一个程序告诉汽车把轮子转到右边。这会使汽车向右转。

当我们加入机器学习时会发生什么？

我们可以在车上安装一个摄像头和一些接近传感器，这将有助于程序“看到”车前的情况。而且我们会教机器检查车前是否有障碍物，如果没有，那就往前开。

这显然是一种过度简化，但这是制造“无人驾驶”汽车的首要原则之一。特斯拉、福特和宝马等公司正在使用机器学习和人工智能来完成所有这些任务。

如果你想知道更多关于机器学习的基础知识，一定要看看[机器学习基础知识](/machine-learning-basics/)博客。

* * *

## 机器学习是如何在交易中实现的？

我们可以使用数据来创建机器学习模型，然后用它来预测未来，这些数据可能是 OHLC 或价格数据、基本面数据，或者是替代数据，如关于某项资产的推文和新闻数据。

当我们说预测未来时，我们是说机器学习模型将为我们提供信号，告诉我们是购买还是出售资产以增加我们的收益。当然，没有人是完美的，机器学习在准确预测未来之前还有很长的路要走。

因为如果可以的话，每个用它的人现在都是百万富翁了。然而，在交易领域，机器学习可以给你超越竞争对手的优势。

当谈到机器学习时，有不同类型的方法来解决问题。概括地说，你可以将机器学习模型分为三个不同的类别:

*   监督学习，
*   [无监督学习](/unsupervised-learning/)，以及
*   [强化学习](/reinforcement-learning-trading/)。

在下一节中，让我们尝试理解机器学习如何使用机器学习分类模型来帮助预测未来。

* * *

## **什么是机器学习中的分类算法？**

人类本质上是喜欢对事物进行分类的生物。事实上，这是我们学习识别事物的方式之一。

想象一个婴儿正在试图理解他所看到的世界。

*   他看见他的父母，他们有两只手和两条腿。
*   但是有一次当他在一个花园里时，他也注意到一个有四条腿和一条尾巴的生物。
*   婴儿的妈妈说这个生物是一只狗。
*   然后婴儿的父亲展示了一张猫的照片，并说这是一种不同的生物。
*   现在这个婴儿能识别人类、猫和狗。

这是机器学习模型如何通过分类学习的简化版本。最初，我们为机器学习模型提供一些示例来训练模型。然后，我们通过给它一些例子作为测试来检查机器已经学习了多少。

有各种类型的机器学习模型来满足不同类型的分类任务。让我们在下一节检查几种类型的机器学习算法。

我们从无数可用的学习辅助工具中挑选了一些最好的。以下是排名前十的[机器学习博客](/machine-learning-top-blogs/)列表。

* * *

## **根据分类任务的机器学习中分类算法的类型**

以下是基于不同分类的机器学习中的各种类型的分类算法。

### 二元分类

在这种类型的分类中，您只有两个类别可供分类。一个常见的例子就是垃圾邮件或者不是垃圾邮件，或者买或者不买。

### 多类分类

顾名思义，在这种分类任务中有两种以上的类。例如，模型必须分类为买入、持有和卖出。

### 不平衡分类

如果给你的数据中某一类的数据占多数，那么这就是一种不平衡分类任务。例如，如果采用 S&P500 的数据，任务是预测我们是否应该持有一年，我们会发现，由于 S&P500 每年都在增加，模型总是会说持有一年。

* * *

根据不同的任务，您可以选择不同的分类模型。事实上，看看交易书中的[机器学习，我们已经解释了各种机器学习模型，包括 Python 中的分类。如果你想了解 Python 中不同类型的分类模型，可以在这里](https://www.quantinsti.com/machine-learning-trading-book)阅读[。](/machine-learning-classification/)

现在让我们用 Python 建立一个分类模型，帮助我们决定是否购买一项资产。

* * *

## **在 Python 中实现分类**

这里有一个简短的声明，你也可以用其他编程语言建立一个机器学习分类模型。但是在这里，我们将重点放在 Python 中的分类上，因为它的通用性和易用性。

虽然掌握 Python 需要一些时间，但由于从第一天起 Python 中各种库的支持，您可以理解代码及其功能。

如果没有这些库，您将不得不花时间编写各种函数来执行您想要的任务。但是有了这些库，你只需要写几行代码，任务就完成了。这里我们将使用“sk learn”Python 库来创建一个简单的分类模型。

我们将一边进行一边解释代码，您将会理解 Python 语言的简单性。

我们将使用[支持向量](/support-vector-machines-introduction/)分类器(SVC)在 S & P500 上实现一个[机器学习分类](https://quantra.quantinsti.com/course/trading-machine-learning-classification-svm)算法。

SVC 是监督学习分类模型。一组训练数据被提供给[机器学习分类算法](https://quantra.quantinsti.com/course/trading-machine-learning-classification-svm)，每个数据属于其中一个类别。

例如，类别可以是买入或卖出股票。分类算法基于训练数据建立模型，然后将测试数据分类到其中一个类别中。

* * *

### 步骤 1:导入库

在我们开始编码任何交易策略之前，我们必须导入必要的 Python 库。在我们的例子中，这些包括 sklearn 机器学习库。

此外，我们使用 pandas 库来存储和执行各种数据操作任务。最后，我们使用 matplotlib 和 seaborn 库来可视化数据。