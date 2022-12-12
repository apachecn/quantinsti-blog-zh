# 安装 Keras——使用 Python 和 R

> 原文：<https://blog.quantinsti.com/installing-keras-python-r/>

马里奥·比萨·培尼亚

安装 Keras 是一个简单的过程，基本上需要决定使用首选的后端引擎，并以与任何其他 Python 库相同的方式安装 Keras。

Keras 是深度学习的 Python 库。它已经被开发出来，允许快速而简单地开发和试验机器学习，我们可以在 **TensorFlow** 、 **CNTK** 或 **Theano** 之上运行 Keras。

如果你想玩深度学习，而又不太担心构建神经网络的底层细节，你应该考虑安装 Keras。由于其高度的抽象性、模块化和易用性，我们可以用简单的方式构建人工智能系统。在这篇关于使用 Python 和 R 安装 Keras 的文章中，我们将从安装 Keras 开始。

[![Python Handbook](img/740388889e6405dfac04c53fbf13b051.png)T4】](https://www.quantinsti.com/python-basics-handbook)

## **安装 Keras -预安装**

Keras 运行在 **TensorFlow** 、 **CNTK** 或 **Theano** 之上，也就是说，我们需要一个后端引擎在它之上运行 Keras。

Keras 本身不执行底层操作，它的优势在于能够在高层建模，从底层实现的细节中抽象出来。这些低级操作依赖于后端，并且由于 Keras 的模块化，允许使用以下一些后端:

*   [**TensorFlow**](https://www.tensorflow.org/) 是 Google 开发的开源符号张量操纵框架。
*   [**Theano**](http://www.deeplearning.net/software/theano/) 是蒙特利尔大学 LISA 实验室开发的开源符号张量操作框架。
*   [**CNTK**](https://docs.microsoft.com/en-us/cognitive-toolkit/) 是微软开发的深度学习开源工具包。

因此，我们需要在安装 Keras 之前安装其中的一些。这里我们将依赖于 **TensorFlow** ,它有很好的接受度和高性能，是 Keras 的默认后端引擎。

在安装 Keras 之前，还可以选择安装一些扩展来帮助我们解决一些相关的问题:

*   [**cuDNN**](https://developer.nvidia.com/cudnn) :需要在 GPU 上运行 Keras。
*   [**h5py**](https://www.h5py.org/) : HDF5 是一种分层文件格式，可以方便地保存数据，对于保存大量的 dta 和 Keras 模型非常有用。
*   **[graphviz](https://www.graphviz.org/) 和 pydot** :绘制 Keras 模型的图形库。

在我们继续安装 Keras 之前，让我们看一下 Tensorflow 的安装。

## **tensorlow 安装**

主要有两种稳定的张量流版本:

*   **tensorflow** :用于在 CPU 上运行。
*   **tensorflow-gpu** :在 gpu 上运行

虽然使用 GPU 我们可以在不中断 CPU 工作的情况下进行非常繁重的计算，但我们将安装更简单的 CPU 版本，这是迈出 TensorFlow 第一步的理想版本。关于安装 TensorFlow GPU 的指南和详细步骤，可以阅读[这篇文章](https://blog.quantinsti.com/install-tensorflow-gpu/)。

也有与 postfix nightly 相同的版本，它们是开发中的不稳定版本，但包括最新的更新和开发。高级用户感兴趣，并尝试最新的发展。先说 TensorFlow，它们并不是最值得推荐的。

因此，要安装 **TensorFlow** 的稳定版本，请在您的终端中编写:

```py
$ pip install tensorflow
```

要安装 TensorFlow 在 GPU 上运行，可以参考[本文](https://blog.quantinsti.com/install-tensorflow-gpu/)提供的详细步骤。

## **在 Python 上安装 Keras**

下面说说在 Python 上安装 Keras。安装 Keras 与在 Python 中安装任何其他库没有什么不同:

```py
$ pip install keras
```

默认情况下，在安装 Keras 时，Keras 将使用 TensorFlow 作为其张量操作库。按照这些指令配置其他 Keras 后端。

### **测试 Keras**

为了玩 Keras，有几个有趣的例子可以玩，但毫无疑问，最让我们感兴趣的例子与市场有关，所以我建议你尝试阅读这篇有趣的帖子，内容是关于使用 Keras 预测股价运动的 Python 中的[人工神经网络。](https://blog.quantinsti.com/artificial-neural-network-python-using-keras-predicting-stock-price-movement/)

有趣的是看到 Keras 如何在 QuantInsti 博客上抽象出直接使用 TensorFlow 的复杂性:[人工神经网络使用 Python 中的 tensor flow](https://blog.quantinsti.com/deep-learning-artificial-neural-network-tensorflow-python/)来预测股票价格

## **在 R 上安装 Keras**T2

在这里，我将解释在 R 上安装 Keras。现在，CRAN 上 R 的 Keras 包可用。要在 R 上安装 Keras，照常进行:

```py
install.packages("keras")
library(keras)
```

Keras R 接口默认使用 TensorFlow 后端引擎。要为 R 安装 TensorFlow，您必须执行以下 R 命令:

```py
install_keras()
```

这个过程创建了一个 Python Conda 环境来管理 Keras 和 TensorFlow。

## **结论**

在这篇关于“安装 Keras -使用 Python 和 R”的文章中，我们已经介绍了在 Python 中安装 Keras 和在 R 中安装 Keras。Keras 是一个 Python 机器学习库，它允许我们从实现低级网络的困难中抽象出来。由于其简单的界面，我们可以快速原型化机器学习实验，并担心问题本身，而不是实现。

正如我们所见，在 Python 中安装 Keras 没有任何困难。如果您想开始使用 Keras，最简单的方法就是开始安装 Keras——默认的 Keras 引擎 TensorFlow，并安装标准库。

从 R 安装 Keras 并使用 Keras 也没有任何困难，尽管我们必须知道 R 中的 Keras 实际上是在幕后使用 Python 环境。

为了熟悉 Keras，我们可以使用官方文档中的例子，但是我们已经看到了一些在交易中使用 Keras 的具体帖子。

如果我们谈论深度学习模型，它们需要大量的神经网络层和数据集来进行训练和运行，并且对交易领域的贡献至关重要。要了解如何在交易中应用深度学习模型，请访问我们的新课程[神经网络交易](https://quantra.quantinsti.com/course/neural-networks-deep-learning-trading-ernest-chan)，该课程由世界知名的欧内斯特·陈博士(Ernest P. Chan)教授。它涵盖了核心概念，如在 Keras 中使用 LSTM 模型的反向和正向传播。

*免责声明:股票市场的所有投资和交易都有风险。在金融市场进行交易的任何决定，包括股票或期权或其他金融工具的交易，都是个人决定，只能在彻底研究后做出，包括个人风险和财务评估以及在您认为必要的范围内寻求专业帮助。本文提到的交易策略或相关信息仅供参考。*