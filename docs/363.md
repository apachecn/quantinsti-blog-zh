# 在 Scikit-learn 中构建和调整线性回归模型

> 原文：<https://blog.quantinsti.com/linear-regression-models-scikit-learn/>

由阿舒托什·戴夫

在[的上一篇博客](/scikit-learn-tutorial/)中，我们研究了在 scikit learn 中训练和优化分类模型的步骤。在这篇博客中，我们将重点放在线性回归模型上。我们将讨论正则化的概念、其示例(山脊、套索和弹性网正则化)以及如何使用 scikit learn 库在 Python 中实现它们。

**内容**

*   [导入库](#importing-libraries)
*   [数据:来自 Scikit Learn 的“糖尿病”数据集](#the-data-diabetes-dataset-from-scikit-learn)
*   [数据预处理](#data-preprocessing)
*   [模型评估指标](#model-evaluation-metric)
*   [简单线性回归](#simple-linear-regression)
*   [多元线性回归](#multiple-linear-regression)
*   [为什么要正规化？](#why-regularize)
*   [什么是岭回归？](#what-is-ridge-regression)
*   [在 scikit learn 中实现岭回归](#implementing-ridge-regression-in-scikit-learn)
*   [什么是拉索回归？](#what-is-lasso-regression)
*   [什么是弹性净回归？](#what-is-elastic-net-regression)
*   [总结](#summary)

* * *

线性回归问题也属于监督学习，其目标是构建一个“模型”或“估计器”,该模型或“估计器”可以在给定一组特征(X)值的情况下预测连续因变量(y)。

任何线性回归模型的一个基本假设是，因变量(y)是(至少在某种程度上！)自变量(Xis)的线性函数。也就是说，我们可以使用数学表达式估算 y:

\(y = b _ 0+b _ 1 X _ 1+b _ 2 X _ 2+b _ 3 X _ 3+\ cdots+b _ n X _ n \)，

其中，\(b_i\)s 是模型要估计的系数。

我们寻求最小化的**成本函数**是误差平方和(也称为残差)。这种方法被称为**普通最小二乘法(OLS)方法**。换句话说，我们想要最小化\( \sum (y - \hat{y})^2\ \ ),其中\(\hat{y}\)是模型预测的 y 值的 bis 的那些最佳值。

尽管 OLS 方法在很多情况下都很有效，但当数据中存在大量异常值或预测变量(\(X_i\)相互关联时，它也有自己的缺点。

这可能会对模型的整体预测准确性产生重大影响，尤其是对于样本外数据或新数据。在这种情况下，某种形式的正规化是有帮助的。

两种最流行的正则化技术是岭回归和套索回归，我们将在这个博客中讨论。

让我们从基础开始，即导入所需的库。

* * *

## 导入库

我们将需要一些常用的库，如 pandas、numpy 和 matplotlib 以及 scikit learn 本身: