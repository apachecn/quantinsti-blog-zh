# Python Numpy 教程:安装、数组和随机采样

> 原文：<https://blog.quantinsti.com/python-numpy-tutorial-installation-arrays-random-sampling/>

杰伊·帕尔马

**NumPy** ，数字 Python 的首字母缩写，是一个用 Python 高效执行科学计算的包。它包括随机数生成能力，基本线性代数函数等等。

今天我们将学习 Python Numpy 模块的基础知识以及理解一些代码。这篇博客文章摘自 [Python 基础手册](https://www.quantinsti.com/python-basics-handbook)，目的很简单，就是让读者理解 [Python 语言](https://blog.quantinsti.com/getting-started-python-trading/)的美丽和简单。

本文的内容包括:

*   [安装 NumPy](#Installing Numpy)
*   [NumPy 数组](#NumPy Arrays)
*   [使用内置函数创建数组](#Array creation using built-in functions)
*   [在 NumPy 中随机抽样](#Random Sampling in NumPy)
*   [数组属性和方法](#Array Attributes and Methods)
*   [数组操作](#Array Manipulation)
*   [数组索引和迭代](#Array Indexing and Iterating)
*   [总结](#Summary)
*   [结论](#Conclusion)

NumPy 不是 Python 标准库的一部分，因此，与任何其他此类库或模块一样，它需要安装在工作站上才能使用。

根据用户使用的 Python 发行版，可以通过命令提示符、conda 提示符或终端使用以下命令来安装。

```py
pip install numpy
```

需要注意的一点是，如果我们使用 Anaconda 发行版来安装 Python，大部分库(如 NumPy、pandas、scikit-learn、matplotlib 等。)是预装的。

**注意:** *如果我们使用 Python 或 iPython 控制台来安装 NumPy 库，安装它的命令前面会有字符！*

安装后，我们可以通过使用 import 语句将其导入到我们的程序中来使用。实际的导入方式如下所示:

```py
import numpy as np
```

这里，NumPy 库是用一个别名 np 导入的，因此可以方便地使用其中的任何功能。我们将在本节的所有示例中使用这种形式的别名。

Python 列表是一个非常强大的顺序数据结构，具有一些漂亮的特性，比如索引子设置和遍历。但是列表缺少一个重要的特性，即以高效的方式对整个元素集合执行操作。

例如，考虑我们计算前 5 天的 PCR(看跌期权比率)的情况。比方说，我们将卖出期权和买入期权分别存储在 call_vol 和 put_vol 列表中。

然后，我们通过将卖出量除以买入量来计算 PCR，如以下脚本所示:

```py
put_vol = [52.89, 45.14, 63.84, 77.1, 74.6] # Put volume in lacs

call_vol = [49.51, 50.45, 59.11, 80.49, 65.11] # Call volume in lacs

# Computing Put Call Ratio (PCR)
put_vol / call_vol
Traceback (most recent call last):

  File "<ipython-input-12-9f9b38fcc5f4>", line 1, in <module>
    put_vol / call_vol

TypeError: unsupported operand type(s) for /: 'list' and 'list'
```

不幸的是，Python 在计算 PCR 值时抛出了一个错误，因为它不知道如何在列表上进行计算。我们可以通过遍历列表中的每一项并分别计算每天的 PCR 来做到这一点。然而，这样做既低效又无聊。一种更好的解决方案是使用 Python NumPy 数组，这是常规 Python 列表的替代方法。

让我们使用 Python NumPy 数组执行同样的操作。为此，我们使用 NumPy 包中的 array()函数，并创建 put_vol 和 call_vol 列表的 Python NumPy 版本。
中的

```py
# Importing NumPy library
import numpy as np

# Creating arrays
n_put_vol = np.array(put_vol)

n_call_vol = np.array(call_vol)

n_put_vol 
```

Out[]
`array([52.89, 45.14, 63.84, 77.1 , 74.6 ])`

In[]
`n_call_vol`

Out[]
`array([49.51, 50.45, 59.11, 80.49, 65.11])`

这里我们有两个数组 n_put_vol 和 n_call_vol，分别存放 put 和 call 的音量。

**现在，我们可以用一行来计算 PCR:**
In[]

```py
# Computing Put Call Ratio (PCR)
pcr = n_put_vol / n_call_vol

pcr
```

Out[]

```py
array([1.06826904, 0.89474727, 1.0800203 , 0.95788297, 1.14575334])
```

这一次成功了，计算是按元素进行的。PCR 数组中的第一个观察值是通过将 n_put_vol 中的第一个元素除以 n_call_vol 数组中的第一个元素来计算的，依此类推。

Python NumPy 处理数组就像处理标量一样。但是我们需要注意这里。Python NumPy 可以很容易地做到这一点，因为它假设数组只能包含单一类型的值。

要么是整数数组，要么是浮点数数组，要么是布尔值数组等等。如果我们试图创建一个不同类型的数组，就像下面提到的那样，得到的 NumPy 数组将只包含一种类型。

**字符串在下面的情况下:**

在[]

```py
np.array([1, 'Python', True])
```

Out[]

```py
array(['1', 'Python', 'True'], dtype='<U11')
```

**注意:** *NumPy 数组被创建为同构数组，这是考虑到可以对它们执行的数学运算。对于异构数据集，这是不可能的。*

在上面给出的例子中，一个整数和一个布尔值都被转换为字符串。NumPy 数组是一种新型的数据结构类型，类似于我们之前看到的 Python 列表类型。这也意味着它有自己的方法，这些方法的行为与其他类型不同。

让我们在 Python list 和 NumPy 数组上实现+操作，看看它们有什么不同。
中的

```py
# Creating lists
list_1 = [1, 2, 3]

list_2 = [5, 6, 4]

# Adding two lists
list_1 + list_2
```

Out[]

```py
[1, 2, 3, 5, 6, 4]
```

在[]

```py
# Creating arrays
arr_1 = np.array([1, 2, 3])

arr_2 = np.array([5, 6, 4])

# Adding two arrays
arr_1 + arr_2
```

Out[]

```py
array([6, 8, 7])
```

从上面的例子中可以看出，使用 list_1 和 list_2 执行+运算，列表元素被粘贴在一起，生成一个包含 6 个元素的列表。

另一方面，如果我们用 NumPy 数组做这件事，Python 会对数组做元素求和。

### **N 维数组**

到目前为止，我们已经使用了两个数组:n_put_vol 和 n_call_vol。如果我们要使用 type()检查其类型，Python 会告诉我们它们属于 numpy.ndarray 类型，如下所示:

In[]

```py
# Checking array type
type(n_put_vol)
```

Out[]

```py
numpy.ndarray
```

根据我们收到的输出，可以推断它们的数据类型是 ndarray，它代表 Python NumPy 中的 n 维数组。

这些数组都是一维数组，但是 Python NumPy 也允许我们创建二维、三维等等。出于学习目的，我们将坚持二维。

我们可以从一个常规的 Python 列表中创建一个 2D(二维)Python NumPy 数组。

**让我们为所有的 put 和 call 卷创建一个数组。**中的

```py
# Recalling put and call volumes lists
put_vol
```

Out[]

```py
[52.89, 45.14, 63.84, 77.1, 74.6] 
```

在[]

```py
call_vol
```

Out[]

```py
[49.51, 50.45, 59.11, 80.49, 65.11]
```

在[]

```py
# Creating a two-dimensional array
n_2d = np.array([put_vol, call_vol]) 

```

```py
n_2d
```

Out[]

```py
array([[52.89, 45.14, 63.84, 77.1 , 74.6 ],
       [49.51, 50.45, 59.11, 80.49, 65.11]])
```

我们看到 n_2d 数组是一个矩形的数据结构。np.array 创建函数中提供的每个列表对应于二维 NumPy 数组中的一行。对于 2D 数组，NumPy 规则同样适用:一个数组只能包含一种类型。

如果我们在上面的数组定义中改变一个浮点值，所有的数组元素都会被强制转换成字符串，以一个同质数组结束。我们可以把 2D 数组看作是链表的高级版本。我们可以用 2D 进行元素运算，就像我们看到的一维数组一样。

## **![Anchor](img/4765334125b448ec4c4bdf8285a1da72.png "Anchor")** 创建数组

在创建 n_call_vol 和 n_put_vol 数组时提供了显式输入。相比之下，Python NumPy 提供了各种内置函数来创建数组，这些函数的输入将由 Python NumPy 生成。

**下面我们讨论几个这样的函数:**

**1。zeros(shape，dtype=float)** 返回给定形状和类型的数组，用零填充。如果 dtype 没有作为输入提供，数组的默认类型将是 float。
中的

```py
# Creating a one-dimensional array
np.zeros(5)
```

Out[]

```py
array([0., 0., 0., 0., 0.])
```

在[]

```py
# Creating a two-dimensional array
np.zeros((3, 5))
```

Out[]

```py
array([[0., 0., 0., 0., 0.],
       [0., 0., 0., 0., 0.],
       [0., 0., 0., 0., 0.]]) 
```

在[]

```py
# Creating a one-dimensional array of integer type
np.zeros(5, dtype=int)
```

out[]`array([0, 0, 0, 0, 0])`

**2。ones(shape，dtype=float)** 返回给定形状和类型的数组，用 1 填充。

```py
# Creating a one-dimensional array
np.ones(5)
```

Out[]

```py
array([1., 1., 1., 1., 1.])
```

在[]

```py
# Creating a one-dimensional array of integer type
np.ones(5, dtype=int)
```

Out[]

```py
array([1, 1, 1, 1, 1])
```

**3。full(shape，fill_value，dtype=None)** 返回一个给定形状和类型的数组，用输入参数中给定的 fill_value 填充。

在[]

```py
# Creating a one-dimensional array with value as 12
np.full(5, 12)
```

Out[]

```py
array([12, 12, 12, 12, 12])
```

在[]

```py
# Creating a two-dimensional array with value as 9
np.full((2, 3), 9)
```

Out[]

```py
array([[9, 9, 9],
       [9, 9, 9]])
```

**4。arange([start，]stop，[step])** 返回一个数组，其中的值在给定的间隔内均匀分布。这里，开始和步骤参数是可选的。如果提供了它们，Python NumPy 将在计算输出时考虑它们。否则，范围计算从 0 开始。对于所有情况，停止值将被排除在输出之外。

在[]

```py
# Creating an array with only stop argument
np.arange(5)
```

Out[]

```py
array([0, 1, 2, 3, 4])
```

在[]

```py
# Creating an array with start and stop arguments
np.arange(3, 8)
```

Out[]

```py
array([3, 4, 5, 6, 7])
```

在[]

```py
# Creating an array with given interval and step value as 0.5
np.arange(3, 8, 0.5)
```

Out[]

```py
array([3\. , 3.5, 4\. , 4.5, 5\. , 5.5, 6\. , 6.5, 7\. , 7.5])
```

**5。linspace(start，stop，num=50，endpoint=True)** 返回指定间隔内间隔相等的数字。要返回的样本数由 num 参数指定。可以选择性地排除区间的终点。

在[]

```py
# Creating an evenly spaced array with five numbers within interval 2 to 3
np.linspace(2.0, 3.0, num=5)
```

Out[]

```py
array([2\.  , 2.25, 2.5 , 2.75, 3\.  ]) 
```

在[]

```py
# Creating an array excluding end value
np.linspace(2.0, 3.0, num=5, endpoint=False)
```

Out[]

```py
array([2\. , 2.2, 2.4, 2.6, 2.8])
```

在[]

```py
# Creating an array with ten values within the specified interval
np.linspace(11, 20, num=10)

```

Out[]

```py
array([11., 12., 13., 14., 15., 16., 17., 18., 19., 20.])![Anchor](img/4765334125b448ec4c4bdf8285a1da72.png "Anchor")
```

除了上面讨论的内置函数，Python NumPy 中还有一个随机子模块，它提供了方便的函数来随机生成数据，并从各种分布中抽取样本。

**这里讨论了一些广泛使用的函数。**

**1。rand([d0，d1，...，dn])** 用于创建一个给定形状的数组，并用[0，1]上均匀分布的随机样本填充它。它只需要积极的论点。如果没有提供参数，则返回单个浮点值。

在[]

```py
# Generating single random number
np.random.rand()
```

Out[]

```py
0.1380210268817208
```

在[]

```py
# Generating a one-dimensional array with four random values
np.random.rand(4)
```

Out[]

```py
array([0.24694323, 0.83698849, 0.0578015 , 0.42668907])
```

在[]

```py
# Generating a two-dimensional array
np.random.rand(2, 3)
```

Out[]

```py
array([[0.79364317, 0.15883039, 0.75798628],
       [0.82658529, 0.12216677, 0.78431111]])
```

**2。randn([d0，d1，...，dn])** 用于创建一个给定形状的数组，并用来自标准正态分布的随机样本填充它。

它只接受正参数并生成一个形状数组(d0，d1，...，dn)填充有从均值为 0、方差为 1 的单变量正态分布中采样的随机浮点数。如果没有提供参数，则返回从分布中随机抽样的单个浮点数。

在[]

```py
# Generating a random sample
np.random.randn()
```

Out[]

```py
0.5569441449249491
```

在[]

```py
# Generating a two-dimensional array over N(0, 1)
np.random.randn(2, 3)
```

Out[]

```py
array([[ 0.43363995, -1.04734652, -0.29569917],
       [ 0.31077962, -0.49519421,  0.29426536]])
```

在[]

```py
# Generating a two-dimensional array over N(3, 2.25)
1.5 * np.random.randn(2, 3) + 3
```

Out[]

```py
array([[1.75071139, 2.81267831, 1.08075029],
       [3.35670489, 3.96981281, 1.7714606 ]])
```

**3。randint(low，high=None，size=None)** 从具有下限(含)和上限(不含)的离散均匀分布中返回一个随机整数。如果 high 为 None(默认值)，则结果从 0 到 low。如果指定了大小，它将返回指定大小的数组。

在[]

```py
# Generating a random integer between 0 and 6
np.random.randint(6)
```

Out[]

```py
2
```

在[]

```py
# Generating a random integer between 6 and 9
np.random.randint(6, 9)
```

`7`
出[]
入[]

```py
# Generating a one-dimensional array with values between 3 and 9
np.random.randint(3, 9, size=5)
```

Out[]

```py
array([6, 7, 8, 8, 5])
```

在[]

```py
# Generating a two-dimensional array with values between 3 and 9
np.random.randint(3, 9, size=(2, 5))
```

Out[]

```py
array([[5, 7, 4, 6, 4],
       [6, 8, 8, 5, 3]])
```

**4。random(size=None)** 返回一个从连续均匀分布中抽取的介于 0 和 1 之间的随机浮点值。

在[]

```py
# Generating a random float
np.random.random()
```

Out[]

```py
0.6013749764953444
```

在[]

```py
# Generating a one-dimensional array
np.random.random(3)

```

Out[]

```py
array([0.69929315, 0.61152299, 0.91313813])
```

在[]

```py
# Generating a two-dimensional array
np.random.random((3, 2))
```

Out[]

```py
array([[0.55779547, 0.6822698 ],
       [0.75476145, 0.224952  ],
       [0.99264158, 0.02755453]])
```

**5。binomial(n，p，size=None)** 返回从二项式分布中抽取的样本，该分布具有 n 次试验和 p 个成功概率，其中 n 大于 0，p 介于 0 和 1 之间。

在[]

```py
# Number of trials, probability of each trial
n, p = 1, .5

# Flipping a coin 1 time for 50 times
samples = np.random.binomial(n, p, 50)

samples
```

Out[]

```py
array([1, 1, 1, 0, 0, 0, 1, 1, 0, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 1, 0, 1,
       0, 0, 0, 0, 0, 1, 0, 1, 1, 1, 1, 1, 0, 1, 0, 0, 0, 0, 0, 1, 1, 0,
       0, 1, 0, 0, 1, 0])
```

**6。normal(mu=0.0，sigma=1.0，size=None)** 从正态(高斯)分布中抽取随机样本。如果没有提供参数，将从 N(0，1)中抽取一个样本。

在[]

```py
# Initialize mu and sigma
mu, sigma = 0, 0.1

# Drawing 5 samples in a one-dimensional array
np.random.normal(mu, sigma, 5)
```

Out[]

```py
array([ 0.06790522,  0.0092956 ,  0.07063545,  0.28022021, -0.13597963])
```

在[]

```py
# Drawing 10 samples in a two-dimensional array of shape (2, 5)
np.random.normal(mu, sigma, (2, 5))
```

out[]`array([[-0.10696306, -0.0147926 , -0.07027478, 0.04399432, -0.03861839], [-0.02004485, 0.08760261, 0.18348247, -0.09351321, -0.19487115]])`

**7。uniform(low=0.0，high=1.0，size=None)** 如果没有提供参数，则从间隔 0(包括)和 1(不包括)的均匀分布中抽取样本。换句话说，在区间内，任何得出的值都是同等可能的。

在[]

```py
# Creating a one-dimensional array with samples drawn within [-1, 0)
np.random.uniform(-1, 0, 10)
```

Out[]

```py
array([-0.7910379 , -0.64144624, -0.64691011, -0.03817127, -0.24480339,
       -0.82549031, -0.37500955, -0.88304322, -0.35196588, -0.51377252])
```

在[]

```py
# Creating a two-dimensional array with samples drawn within [0, 1)
np.random.uniform(size=(5, 2))
```

Out[]

```py
array([[0.43155784, 0.41360889],
       [0.81813931, 0.70115211],
       [0.40003811, 0.2114227 ],
       [0.95487774, 0.92251769],
       [0.91042434, 0.98697917]])
```

除了上面显示的函数，我们还可以从其他各种分布中抽取样本，如泊松分布、伽马分布、指数分布等。使用 Python NumPy。

我们现在对 Python NumPy 数组的工作有了一些了解。现在让我们来探索它们所提供的功能。与任何 Python 对象一样，

NumPy 数组也有一组丰富的属性和方法，这在很大程度上简化了数据分析过程。以下是最有用的数组属性。为了便于说明，我们将使用以前定义的数组。

**1。ndim** 属性显示一个数组的维数。在 n_call_vol 和 pcr 上使用这个属性，我们期望维度分别为 1 和 2。让我们检查一下。

在[]

```py
# Checking dimensions for n_call_vol array
np_call_vol.ndim
```

Out[]

```py
1
```

在[]

```py
n_2d.ndim
```

Out[]

```py
2
```

**2。shape** 返回数组维数的元组。它还可以通过向数组分配数组维度元组来就地重塑数组。

在[]

```py
# Checking the shape of the one-dimensional array
n_put_vol.shape
```

Out[]

```py
(5,)
```

在[]

```py
# Checking shape of the two-dimensional array
n_2d.shape
```

Out[]

```py
(2, 5) *# It shows 2 rows and 5 columns*
```

在[]

```py
# Printing n_2d with 2 rows and 5 columns
n_2d
```

Out[]

```py
array([[52.89, 45.14, 63.84, 77.1 , 74.6 ],
       [49.51, 50.45, 59.11, 80.49, 65.11]])
```

在[]

```py
# Reshaping n_2d using the shape attribute
n_2d.shape = (5, 2)

# Printing reshaped array
n_2d
```

Out[]

```py
array([[52.89, 45.14],
       [63.84, 77.1 ],
       [74.6 , 49.51],
       [50.45, 59.11],
       [80.49, 65.11]])

```

**3。size** 返回数组中元素的数量。

在[]

```py
n_call_vol.size
```

Out[]

```py
5
```

在[]

```py
n_2d.size
```

Out[]

```py
10
```

**4。dtype** 返回数组元素的数据类型。正如我们在上面了解到的，NumPy 自带了自己的数据类型，就像常规的内置数据类型一样，比如 int、float、str 等等。

在[]

```py
n_put_vol.dtype
```

Out[]

```py
dtype('float64')
```

在理想的数据分析过程中，我们通常有成千上万的数字需要分析。仅仅盯着这些数字不会给我们提供任何见解。相反，我们能做的是生成数据的汇总统计。在许多有用的特性中，Python NumPy 还提供了各种统计函数，可以很好地对数组进行统计。

让我们创建一个样本数组，用从均值为 5、标准差为 1.5 的正态分布中抽取的样本填充它，并计算它的各种统计数据。

在[]

```py
# Creating a one-dimensional array with 1000 samples drawn from a normal distribution
samples = np.random.normal(5, 1.5, 1000)

# Creating a two-dimensional array with 25 samples drawn from a normal distribution
samples_2d = np.random.normal(5, 1.5, size=(5, 5))

samples_2d
```

Out[]

```py
array([[5.30338102, 6.29371936, 2.74075451, 3.45505812, 7.24391809],
       [5.20554917, 5.33264245, 6.08886915, 5.06753721, 6.36235494],
       [5.86023616, 5.54254211, 5.38921487, 6.77609903, 7.79595902],
       [5.81532883, 0.76402556, 5.01475416, 5.20297957, 7.57517601],
       [5.76591337, 1.79107751, 5.03874984, 5.05631362, 2.16099478]])
```

**5。mean(a，axis=None)** 返回数组元素的平均值。默认情况下，平均值是在展平的数组上计算的，否则在指定的轴上计算。

average(a，axis=None)得出数组元素的平均值，工作方式类似于 mean()。

In[]

```py
# Computing mean
np.mean(samples)
```

Out[]

```py
5.009649198007546
```

In[]

```py
np.average(samples)
```

Out[]

```py
5.009649198007546
```

In[]

```py
# Computing mean with axis=1 (over each row)
np.mean(samples_2d, axis=1)
```

Out[]

```py
array([5.00736622, 5.61139058, 6.27281024, 4.87445283, 3.96260983]) 
```

In[]

```py
np.average(samples_2d, axis=1)
```

Out[]

```py
array([5.00736622, 5.61139058, 6.27281024, 4.87445283, 3.96260983])
```

**6\. max(a, axis=None)** returns the maximum of an array or maximum along an axis.

在[]

```py
np.max(samples)
```

Out[]

```py
9.626572532562523
```

在[]

```py
np.max(samples_2d, axis=1)
```

out[]

```py
array([7.24391809, 6.36235494, 7.79595902, 7.57517601, 5.76591337])
```

7 .**。median(a，axis=None)** 返回沿指定轴的中值。

在[]

```py
np.median(samples)
```

Out[]

```py
5.0074934668143865
```

在[]

```py
np.median(samples_2d)
```

Out[]

```py
5.332642448141249
```

**8。min(a，axis=None)** 返回一个数组的最小值或沿一个轴的最小值。

在[]

```py
np.min(samples)
```

Out[]

```py
0.1551821703754115
```

在[]

```py
np.min(samples_2d, axis=1)
```

Out[]

```py
array([2.74075451, 5.06753721, 5.38921487, 0.76402556, 1.79107751])
```

**9。var(a，axis=None)** 返回一个数组或沿指定轴的方差。

在[]

```py
np.var(samples)
```

Out[]

```py
2.2967299389550466
```

在[]

```py
np.var(samples_2d)
```

Out[]

```py
2.93390175942658
```

在[]

```py
np.var(samples_2d, axis=0) # Here, the variance is computed over each column of numbers
```

Out[]

```py
array([0.07693981, 4.95043105, 1.26742732, 1.10560727, 4.37281009])
```

10。std(a，axis=None) 返回一个数组或沿指定轴的标准偏差。

在[]

```py
np.std(samples)
```

Out[]

```py
1.5154965981337756
```

在[]

```py
np.std(samples_2d)
```

Out[]

```py
1.7128636137844075
```

**11。sum(a，axis=None)** 返回数组元素的和。

在[]

```py
# Recalling the array n_put_vol
n_put_vol
```

Out[]

```py
array([52.89, 45.14, 63.84, 77.1 , 74.6 ])
```

在[]

```py
# Computing sum of all elements within n_put_vol
np.sum(n_put_vol)
```

Out[]

```py
313.57
```

在[]

```py
# Computing sum of all array over each row
np.sum(samples_2d, axis=1)
```

Out[] `array([25.03683109, 28.05695291, 31.36405118, 24.37226413, 19.81304913])`

**12。cumsum(a，axis=None)** 返回给定坐标轴上元素的累积和。
中的

```py
np.cumsum(n_put_vol)
```

Out[]

```py
array([ 52.89,  98.03, 161.87, 238.97, 313.57])
```

上面讨论的方法也可以直接调用 NumPy 对象，如 samples、n_put_vol、samples_2d 等。而不是用 np。格式如下所示。

两种情况下输出都是一样的。

在[]

```py
# Using np. format to compute the sum
np.sum(samples)
```

Out[]

```py
5009.649198007546
```

在[]

```py
# Calling sum() directly on a NumPy object
samples.sum()
```

Out[]

```py
5009.649198007546
```

Python NumPy 为它创建的数组对象定义了一个名为 **ndarray** 的新数据类型。这也意味着各种运算符，如算术运算符、逻辑运算符、布尔运算符等。以我们目前所见的独特方式工作。

有一种灵活而有用的数组操作技术， **Python NumPy** 提供了这种技术，可以使用广播对其数据结构进行操作。

术语 broadcasting 描述了 Python NumPy 在算术运算过程中如何处理不同形状的数组(有一定的约束)。较小的阵列在较大的阵列中传播，因此它们具有兼容的形状。它还提供了一种向量化数组操作的方法。

Python NumPy 操作通常是在一个元素接一个元素的基础上对数组对进行的。在最简单的情况下，这两个数组必须具有与下例完全相同的形状。

在[]

```py
a = np.array([1, 2, 3])

b = np.array([3, 3, 3])

a * b
```

Out[]

```py
array([3, 6, 9])
```

当数组的形状满足某些约束时，Python NumPy 的广播规则放松了这种约束。

最简单的广播例子发生在一个数组和一个标量值在运算中组合在一起时，如下图所示:

在[]

```py
a = np.array([1, 2, 3])

b = 3

a * b
```

Out[]

```py
array([3, 6, 9])
```

结果相当于前一个例子，其中 b 是一个数组。我们可以把上面例子中的标量 b 在算术运算过程中拉伸成一个与 a 形状相同的数组

b 中的新元素只是原始标量的副本。这里，拉伸类比只是概念性的。Python NumPy 足够聪明，可以使用原始标量值，而无需实际制作副本，因此广播操作尽可能节省内存和提高计算效率。

最后一个例子中的代码效率更高，因为广播在乘法期间移动的内存比它上面定义的对应代码要少。

除了高效的数字处理能力，Python NumPy 还提供了多种数组操作方法，从而证明了它的通用性。

**我们在这里讨论其中的一些。**

**1。exp(*args)** 返回输入数组中所有元素的指数。这些数字将被提高到 e，也称为欧拉数。

在[]

```py
# Computing exponentials for the array 'a'
np.exp(a)
```

Out[]

```py
array([ 2.71828183,  7.3890561 , 20.08553692])
```

**2。sqrt(*args)** 按元素返回数组的正平方根。

在[]

```py
# Computing square roots of a given array
np.sqrt([1, 4, 9, 16, 25])
```

Out[]

```py
array([1., 2., 3., 4., 5.])
```

**3。reshape(new_shape)** 给一个数组一个新的形状，而不改变它的数据。

在[]

```py
# Creating a one-dimensional array with 12 elements
res = np.arange(12)

res
```

Out[]

```py
array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11]) 
```

在[]

```py
# Reshaping the 'res' array to 2-dimensional array
np.reshape(res, (3, 4))
```

Out[]

```py
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
```

在[]

```py
# Reshaping the dimensions from (3, 4) to (2, 6)
np.reshape(res, (2, 6))
```

Out[]

```py
array([[ 0,  1,  2,  3,  4,  5],
       [ 6,  7,  8,  9, 10, 11]])
```

**4。resize(a，new_shape)** 返回指定形状的新数组。如果新数组比原始数组大，那么新数组中会填充。

在[]

```py
# Creating a one-dimensional array
demo = np.arange(4)

demo
```

Out[]

```py
array([0, 1, 2, 3])
```

在[]

```py
# Resizing a 'demo' array to (2, 2)
np.resize(demo, (2, 2))
```

Out[]

```py
array([[0, 1],
       [2, 3]])
```

在[]

```py
# Resizing a 'demo' greater than its size.
np.resize(demo, (4, 2))
```

out[]`array([[0, 1], [2, 3], [0, 1], [2, 3]])`

**5。round(a，decimals=0)** 将数组舍入到给定的小数位数。如果没有给出小数，元素将被四舍五入为整数。

在[]

```py
# Creating a one-dimensional array
a = np.random.rand(5)

# Printing array
a
```

Out[]

```py
array([0.71056952, 0.58306487, 0.13270092, 0.38583513, 0.7912277 ])
```

在[]

```py
# Rounding to 0 decimals
a.round()
```

Out[]

```py
array([1., 1., 0., 0., 1.])
```

在[]

```py
# Rounding to 0 decimals using the np.round syntax
np.round(a)
```

Out[]

```py
array([1., 1., 0., 0., 1.])
```

在[]

```py
# Rounding to 2 decimals
a.round(2)
```

Out[]

```py
array([0.71, 0.58, 0.13, 0.39, 0.79])
```

在[]

```py
# Rounding to 3 decimals using the np.round syntax
np.round(a, 3)
```

Out[]

```py
array([0.711, 0.583, 0.133, 0.386, 0.791])
```

**6。sort(a，kind='quicksort')** 返回一个数组的排序副本。使用的默认排序算法是快速排序。其他可用的选项有 mergesort 和 heapsort。

在[]

```py
np.sort(n_put_vol)
```

Out[]

```py
array([45.14, 52.89, 63.84, 74.6 , 77.1 ])
```

在[]

```py
np.sort(samples_2d)
```

Out[]

```py
array([[2.74075451, 3.45505812, 5.30338102, 6.29371936, 7.24391809],
       [5.06753721, 5.20554917, 5.33264245, 6.08886915, 6.36235494],
       [5.38921487, 5.54254211, 5.86023616, 6.77609903, 7.79595902],
       [0.76402556, 5.01475416, 5.20297957, 5.81532883, 7.57517601],
       [1.79107751, 2.16099478, 5.03874984, 5.05631362, 5.76591337]])
```

**7。vstack(tup)** 将通过 tup 提供的数组垂直按顺序(按行)堆叠。

*   **hstack(tup)** 将通过 tup 提供的数组按顺序水平堆叠(按列)。
*   **column_stack(tup)** 将一维数组作为列堆叠成二维数组。它接受一系列一维数组，并将它们按列堆叠起来，形成一个二维数组。

在[]

```py
# Creating sample arrays
a = np.array([1, 2, 3])

b = np.array([4, 5, 6])

c = np.array([7, 8, 9])

# Stacking arrays vertically
np.vstack((a, b, c))
```

Out[]

```py
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

在[]

```py
# Stacking arrays horizontally
np.hstack((a, b, c))
```

Out[]

```py
array([1, 2, 3, 4, 5, 6, 7, 8, 9])
```

在[]

```py
# Stacking two arrays together
np.column_stack((a, b))
```

Out[]

```py
array([[1, 4],
       [2, 5],
       [3, 6]]) 
```

在[]

```py
# Stacking three arrays together
np.column_stack((a, b, c))
```

Out[]

```py
array([[1, 4, 7],
       [2, 5, 8],
       [3, 6, 9]])
```

**8。transpose()** 改变数组的维数。

在[]

```py
# Creating a two-dimensional array with shape (2, 4)
a = np.arange(8).reshape(2, 4)

# Printing it
a
```

Out[]

```py
array([[0, 1, 2, 3],
       [4, 5, 6, 7]])
```

在[]

```py
# Transposing the array
a.transpose()
```

Out[]

```py
array([[0, 4],
       [1, 5],
       [2, 6],
       [3, 7]])
```

NumPy 是一个优秀的库，可以高效地处理数字，并且易于使用。它与 Python 及其语法无缝集成。在这个属性之后，Python NumPy 提供了非常类似于列表的子集化和迭代技术。

我们可以用方括号对 NumPy 数组进行子集化，用 Python 内置的构造进行迭代，用其他内置的方法进行切片。

### **索引和子集化**

NumPy 数组遵循类似于 Python 列表的索引结构。Index 从 0 开始，数组中的每个元素都与一个唯一的索引相关联。下表显示了一维数组的 NumPy 索引。

index 0 1 2 3 4
NP . array 52 88 41 63 94

The index structure for a two-dimensional array with a shape of (3, 3) is shown below.

| 索引 | Zero | one | Two |
| --- | --- | --- | --- |
| Zero | a | b | c |
| one | d | e | f |
| Two | g | h | 我 |

描述上述结构的两个数组 arr_1d 和 arr_2d 已在下面创建:

在[]

```py
# Creating one-dimensional array
arr_1d = np.array([52, 88, 41, 63, 94])

# Creating two-dimensional array
arr_2d = np.array([['a', 'b', 'c'],
    ...:                    ['d', 'e', 'f'],
    ...:                    ['g', 'h', 'i']])
```

我们使用方括号[]来划分 NumPy 数组中每个元素的子集。让我们使用索引对上面创建的数组进行子集化。

在[]

```py
# Slicing the element at index 0
arr_1d[0]
```

Out[]

```py
52
```

在[]

```py
# Slicing the last element using negative index
arr_1d[-1]
```

Out[]

```py
94
```

在[]

```py
# Slicing elements from position 2 (inclusive) to 5 (exclusive)
arr_1d[2:5]
```

Out[]

```py
array([41, 63, 94])
```

在上面的例子中，我们对一维数组进行了切片。类似地，方括号也允许使用语法[r，c]进行二维切片，其中 r 是一行，c 是一列。

在[]

```py
# Slicing the element at position (0, 1)
arr_2d[0, 1]
```

Out[]

```py
'b'
```

在[]

```py
# Slicing the element at position (1, 2)
arr_2d[1, 2]
```

Out[]

```py
'f'
```

在[]

```py
# Slicing the element at position (2, 0)
arr_2d[2, 0]
```

Out[]

```py
'g'
```

在[]

```py
# Slicing the first row
arr_2d[0, ]
```

Out[]

```py
array(['a', 'b', 'c'], dtype='<U1')
```

在[]

```py
# Slicing the last column
arr_2d[:, 2]
```

Out[]

```py
array(['c', 'f', 'i'], dtype='<U1')
```

请注意上一个示例中的语法，我们对最后一列进行了切片。

“:”已作为输入提供，表示所有元素，然后过滤最后一列。仅使用“:”将返回数组中的所有元素。

在[]

```py
arr_2d[:]
```

Out[]

```py
array([['a', 'b', 'c'],
       ['d', 'e', 'f'],
       ['g', 'h', 'i']], dtype='<U1')
```

### **布尔索引**

NumPy 数组可以用其他数组(或列表)进行索引。用于索引其他数组的数组称为索引数组。大多数情况下，它是一个简单的数组，用来作为其他数组的子集。

索引数组的使用范围从简单、直接的情况到复杂、难以理解的情况。当使用另一个数组对一个数组进行索引时，返回的是原始数据的副本，而不是像获取切片那样的视图。

**来说明:**

在[]

```py
# Creating an array
arr = np.arange(1, 10)

# Printing the array
arr
```

Out[]

```py
array([1, 2, 3, 4, 5, 6, 7, 8, 9])
```

在[]

```py
# Subsetting the array `arr` using an anonymous array
arr[np.array([2, 5, 5, 1])]
```

Out[]

```py
array([3, 6, 6, 2])
```

在上面的例子中，我们创建了一个有十个元素的数组 arr。然后，我们尝试使用匿名索引数组对其进行子集化。

由值 2、5、5、1 组成的索引数组对应创建一个长度为 4 的数组，即与长度索引数组相同。

索引数组中的值作为子集的索引(在上面给出的操作中),它只是从数组中返回相应的值。

扩展这个概念，一个数组可以自己索引。使用逻辑运算符，可以根据需要过滤 NumPy 数组。考虑一个场景，我们需要过滤大于某个阈值的数组值。

**如下图:**

在[]

```py
# Creating an random array with 20 values
rand_arr = np.random.randint(1, 50, 20)

# Printing the array
rand_arr
```

Out[]

```py
array([14, 25, 39, 18, 40, 10, 33, 36, 29, 25, 27,  4, 28, 43, 43, 19, 30,
       29, 47, 41])
```

在[]

```py
# Filtering the array values which are greater than 30
rand_arr[rand_arr > 30]
```

Out[]

```py
array([39, 40, 33, 36, 43, 43, 47, 41])
```

这里，我们创建一个名为 rand_arr 的数组，包含 20 个随机值。然后，我们尝试使用逻辑运算符>，用大于 30 的值对其进行子集划分。当使用逻辑运算符

对数组进行切片时，Python NumPy 会生成一个包含真值和假值的匿名数组，然后使用该数组对数组进行子集化。为了说明这一点，让我们执行用于 rand_arr 子集的代码，即写在方括号内的代码。

在[]

```py
filter_ = rand_arr > 30

filter_
```

Out[]

```py
array([False, False,  True, False,  True, False,  True,  True, False,
       False, False, False, False,  True,  True, False, False, False,
        True,  True])
```

它返回一个只有 True 和 False 值的布尔数组。在这里，只要逻辑条件成立，就会出现 True。Python NumPy 使用这个输出的数组作为原始数组的子集，并且只返回那些为真的值。除了这种方法，Python NumPy 还提供了一个 where 方法，使用它我们可以获得相同的过滤输出。我们在 where 条件中传递一个逻辑条件，它将返回一个数组，其中包含条件为真的所有值。

在下面的例子中，我们使用 where 条件从 rand_arr 中过滤出所有大于 30 的值:

在[]

```py
# Filtering an array using np.where method
rand_arr[np.where(rand_arr > 30)]
```

Out[]

```py
array([39, 40, 33, 36, 43, 43, 47, 41])
```

我们通过执行 rand_arr[rand_arr > 30]和 rand _ arr[NP . where(rand _ arr > 30)]得到了相同的结果。然而，Python NumPy 提供的 where 方法并不过滤值。相反，它可以用于更通用的场景。

**下面给出的是官方语法:**

```py
np.where[condition[, x, y]]
```

它根据条件从 x 或 y 返回元素。作为这些参数，x 和 y 是可选的，如果给定为真，则条件为 x，否则为 y 或布尔值为假。下面我们创建一个包含 20 个元素的数组高度，高度范围从 150 到 160，看看 where 方法的各种用法。

在[]

```py
# Creating an array heights
heights = np.random.uniform(150, 160, size=20)

heights
```

Out[]

```py
array([153.69911134, 154.12173942, 150.35772942, 151.53160722,
       153.27900307, 154.42448961, 153.25276742, 151.08520803,
       154.13922276, 159.71336708, 151.45302507, 155.01280829,
       156.9504274 , 154.40626961, 155.46637317, 156.36825413,
       151.5096344 , 156.75707004, 151.14597394, 153.03848597])

```

**用法 1:不带 x 和 y 参数**
如下例所示，使用不带可选参数的 where 方法将返回条件为真的原始数组的索引值。

在[]

```py
np.where(heights > 153)
```

Out[]

```py
(array([ 0,  1,  4,  5,  6,  8,  9, 11, 12, 13, 14, 15, 17, 19],
       dtype=int64),)
```

上述代码返回高度数组的索引值，其中值大于 153。这个场景与我们在上面看到的随机数组 rand_arr 非常相似，我们试图过滤大于 30 的值。

在这里，输出仅仅是指标值。如果我们想要原始值，我们需要使用我们获得的输出对 heights 数组进行子集化。

**用法 2:x 为真，y 为假**
有了这些可选参数，将根据条件返回其中一个参数。如下例所示:

在[]

```py
np.where(heights > 153, True, False)
```

Out[]

```py
array([True, True, False,  False, True, True, True, False, True,
        True, False, True, True, True, True, True, False, True,
       False, True])
```

用法 2 的输出为 heights 数组中的所有元素提供 true 或 False，而用法 1 只返回条件为 True 的元素的索引值。

可选参数也可以是类似数组的元素，而不是标量或静态值，如 True 或 False。

**用法 3:x 和 y 是数组**
现在我们已经很好地理解了该方法的工作原理，猜测输出是相当容易的。根据第一个参数中的条件，输出将包含来自 x 数组或 y 数组的值。
例如:

在[]

```py
# Creating an array 'x_array'
x_array = np.arange(11, 31, 1)

x_array
```

Out[]

```py
array([11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27,
       28, 29, 30])
```

在[]

```py
# Creating an array 'y_array'
y_array = np.arange(111, 131, 1)

y_array
```

Out[]

```py
array([111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123,
       124, 125, 126, 127, 128, 129, 130]) 
```

在[]

```py
np.where(heights > 153, x_array, y_array)
```

Out[]

```py
array([ 11,  12, 113, 114,  15,  16,  17, 118,  19,  20, 121,  22,  23,
        24,  25,  26, 127,  28, 129,  30])
```

正如所料，当 heights 数组中的值大于 153 时，上述代码片段的输出包含来自数组 x_array 的值，否则，将输出来自 y_array 的值。理解了 Python NumPy 库提供的 where 方法的工作原理后，现在让我们看看它在回溯测试策略中是如何有用的。考虑一个场景，我们有生成交易信号所需的所有数据。

对于这个假设的例子，我们拥有的数据是一只股票 20 个周期的收盘价及其平均价格。

在[]

```py
# Hypothetical close prices for 20 periods
close_price = np.random.randint(132, 140, 20)

# Printing close_price
close_price
```

Out[]

```py
array([137, 138, 133, 132, 134, 139, 132, 138, 137, 135, 136, 134, 134,
       139, 135, 133, 136, 139, 132, 134])
```

我们将根据给我们的买入条件产生交易信号。即当收盘价高于平均价 135.45 时，我们做多或买入股票。使用 where 方法可以很容易地计算出来，如下所示:

在[]

```py
# Average close price
avg_price = 135.45

# Computing trading signals with 1 being 'buy' and 0 represents 'no signal'
signals = np.where(close_price > avg_price, 1, 0)

# Printing signals
signals
```

Out[]

```py
array([1, 1, 0, 0, 0, 1, 0, 1, 1, 0, 1, 0, 0, 1, 0, 0, 1, 1, 0, 0])

```

信号数组包含交易信号，其中 1 代表买入，0 代表没有交易信号。

### **迭代数组**

NumPy 数组是 Python 中的可迭代对象，这意味着我们可以像处理任何其他可迭代对象一样，使用 iter()和 next()方法直接迭代它们。这也意味着我们可以使用内置的循环结构来迭代它们。

下面的例子展示了**使用 for 循环迭代 NumPy 数组**。

在[]

```py
# Looping over a one-dimensional array
for element in arr_1d:
     print(element)
```

Out[]

```py
52
88
41
63
94
```

在一维数组上循环简单而直接。但是，如果我们要用 arr_2d 执行 for 循环，它将遍历所有行并提供输出。

如下例所示。

在[]

```py
for element in arr_2d:
  print(element)
```

Out[]

```py
['a' 'b' 'c']
['d' 'e' 'f']
['g' 'h' 'i']
```

为了迭代二维数组，我们需要考虑两个轴。可以在嵌套格式中使用单独的 for 循环来遍历每个元素，如下所示:

在[]

```py
for element in arr_2d:
 for e in element:
       print(e)
```

Out[]

```py
a
b
c
d
e
f
g
h
i
```

我们得到的输出也可以使用 Python NumPy 的 nditer()方法来实现，它的工作与维度无关。

在[]

```py
for element in np.nditer(arr_2d):
   print(element)
```

Out[]

```py
a
b
c
d
e
f
g
h
i
```

这就结束了 Python NumPy 模块的旅程。上面提供的例子只描述了 Python NumPy 功能的最小集合。虽然不全面，但它应该让我们对什么是 NumPy 以及为什么我们应该使用它有一个很好的感觉。

*   NumPy 库用于在 Python 中执行科学计算。
*   它不是 Python 标准库的一部分，需要在程序中使用之前明确安装。
*   它允许创建 ndarray 类型的 n 维数组。
*   NumPy 数组只能保存单一数据类型的元素。
*   可以使用任何顺序数据结构(如列表或元组)或内置的 NumPy 函数来创建它们。
*   NumPy 库的随机模块允许从各种数据分布中生成样本。
*   NumPy 支持使用广播功能的逐元素操作。
*   与列表类似，NumPy 数组也可以使用方括号[]切片，并从 0 开始索引。
*   也可以根据逻辑条件对 NumPy 数组进行切片。得到的数组将是一个布尔值 True 或 False 的数组，其他数组将基于该数组进行切片或过滤。这就是所谓的布尔索引。

重申一下，这篇文章是从 [Python 基础手册](https://www.quantinsti.com/python-basics-handbook)中摘录的，它是为这两者而创作的；刚开始使用 [Python](https://quantra.quantinsti.com/course/python-for-trading) 的新手，以及有成就的交易者，他们可以在编写策略时使用它作为方便的参考。

请在下面的评论中告诉我们你是否喜欢这篇文章以及其他反馈。

*<small>免责声明:股票市场的所有投资和交易都涉及风险。在金融市场进行交易的任何决定，包括股票或期权或其他金融工具的交易，都是个人决定，只能在彻底研究后做出，包括个人风险和财务评估以及在您认为必要的范围内寻求专业帮助。本文提到的交易策略或相关信息仅供参考。</small>T11】*