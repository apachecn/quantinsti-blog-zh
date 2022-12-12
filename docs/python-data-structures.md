# Python 数据结构教程

> 原文：<https://blog.quantinsti.com/python-data-structures/>

杰伊·帕尔马

Python 有各种内置的数据结构，比如元组、列表、字典和集合。像变量一样，python 数据结构也用于存储值。与变量不同，它们不仅仅存储一个值，而是各种格式的值的集合。广义来说，python 数据结构分为*数组*、*列表*和*文件*。数组可以被认为是 python 数据结构的基本形式，而文件是存储复杂数据的更高级形式。

这篇博客文章是从 [Python 基础手册](https://www.quantinsti.com/python-basics-handbook)中摘录的，其创建的简单目的是让读者理解 [Python 语言](https://blog.quantinsti.com/getting-started-python-trading/)的美丽和简单。

我们将在本 python 数据结构教程中讨论以下主题:

*   [分度和切片](#index)
*   [数组](#array)
*   [元组](#tuples)
*   [列表](#lists)
*   [堆栈和队列](#stacks)
*   [字典](#dictionaries)
*   [设置](#sets)

在我们深入 python 数据结构的世界之前，让我们看一下适用于 Python 中所有数据结构的*索引*和*切片*的概念。

## 索引和切片

字符串可以被认为是一系列字符。类似地，python 数据结构存储对象序列(浮点、整数、字符串等。).

考虑一个从 A 到 J 的 10 个字符的序列，其中我们为序列中的每个字面值分配一个唯一的位置。分配给每个字符的位置是一个从 0 到最后一个字符的整数序列。如下所示，它们依次递增 1。

| 索引 | Zero | one | Two | three | four | five | six | seven | eight | nine |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **序列** | A | B | C | D | E | F | G | H | 我 | J |

在上面的序列中，字符`A`位于索引`0`，`B`位于`1`，`C`位于`2`，以此类推。注意指数是如何按时间顺序在每一步增加一个单位的。每当一个新字符被添加到这个序列中时，它将被添加到末尾，并被赋予下一个索引值(在上面的例子中，新字符的新索引将是`10`)。几乎所有的 python 数据结构都有一个定位元素的索引。

序列中的元素可以使用方括号`[]`来访问。它获取元素的`index`并返回元素本身。访问单个元素的语法如下:

```py
sequence[i]
```

上述语句将从索引`i`处的序列中返回元素。我们可以通过以下方式使用语法`[start index : end index]`从序列中访问多个元素:

```py
sequence[si : ei]
```

上述语句将返回从索引`si`开始的值，但不包括索引`ei`处的元素。这个操作被称为*切片*。例如:

```py
sequence[0:4] will return elements from 'A' to 'D' and not up to 'E'. Element at the last index in the provided range will not be returned.
```

Python 还支持从序列末尾访问元素的负索引，它从-1 开始，如下所示:

| 索引 | Zero | one | Two | three | four | five | six | seven | eight | nine |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **序列** | A | B | C | D | E | F | G | H | 我 | J |
| **负指数** | -10 | -9 | -8 | -7 | -6 | -5 | -4 | -3 | -2 | -1 |

也可以使用负索引对序列进行切片。为了访问最后一个元素，我们写

```py
sequence[-1]
```

它将返回元素`J`。类似地，可以提供一个范围来访问多个元素。

```py
sequence[-5:-1] will return elements from 'F' to 'I'
```

## 排列

数组可以被认为是一个容器，可以保存固定数量的相同类型的数据值。尽管与其他语言(如 C 和 Java)相比，python 中使用数组的情况较少，但大多数其他 Python 数据结构都在内部使用数组来实现它们的算法。一个数组由两部分组成，即**元素**和**索引**。

*   元素:这些是要存储在数组中的实际数据值。
*   Index:数组中的每个元素都位于由索引描述的特定位置。Python 遵循从零开始的索引，这意味着索引总是从 0 开始。

我们可以使用内置的`array`模块创建一个数组。它可以按如下方式创建:

```py
In [1]: from array import *
In [2]: arr = array('i', [2, 4, 6, 8])
In [3]: arr
Out[3]: array('i', [2, 4, 6, 8])
In [4]: type(arr)
Out[4]: array.array

```

在上面的 python 数据结构示例中，我们从`array`模块导入`array`方法，然后用方括号中的值`2`、`4`、`6`和`8`初始化变量`arr`。`i`代表数值的数据类型。在这种情况下，它表示一个整数。 [Python 数组文档](https://docs.python.org/3.4/library/array.html)提供了 Python 中各种类型代码的更多信息。

### 可视化数组

上面声明的数组可以用以下方式表示:

| 索引 | Zero | one | Two | three |
| --- | --- | --- | --- | --- |
| **元素** | Two | four | six | eight |

根据上图，以下是需要考虑的几点。

*   索引从 0 开始。
*   数组长度为 4，这意味着它可以存储 4 个值。
*   数组只能保存单一数据类型的值。
*   每个元素都可以通过它的索引来访问。

### 访问数组元素

我们使用切片操作来访问数组元素。使用方括号`[]`执行切片操作。它获取我们感兴趣的元素的索引。可以注意到，上述数组中第一个元素的索引为 0。因此，为了访问位置 3 的元素，我们使用符号`arr[2]`来访问它。

```py
# Here, 2 represents the index of element 6
In [5]: arr[2]
Out[5]: 6
In [6]: arr[0]
Out[6]: 2

```

### 操纵数组

现在让我们了解一下 python 数据结构教程中不同的数组操作。`array`模块提供了各种各样的操作，可以根据需求来执行。我们将学习一些最常用的操作。

我们使用插入操作将一个或多个数据元素插入到数组中。根据需要，可以使用`insert()`方法在开头、结尾或任何给定的索引处插入一个元素。

```py
# Inserting an element at the beginning
In [7]: arr.insert(0, 20)
In [8]: arr
Out[8]: array('i', [20, 2, 4, 6, 8])
# Inserting an element at the index 3
In [9]: arr.insert(3, 60)
In [10]: arr
Out[10]: array('i', [20, 2, 4, 60, 6, 8])

```

可以使用内置的`remove()`方法从数组中删除一个元素。

```py
In [11]: arr.remove(20)
In [12]: arr
Out[12]: array('i', [2, 4, 60, 6, 8])
In [13]: arr.remove(60)
In [14]: arr
Out[14]: array('i', [2, 4, 6, 8])

```

我们可以使用赋值操作符`=`以如下方式更新特定索引处的元素:

```py
# Update an element at index 1
In [15]: arr[0] = 1
In [16]: arr
Out[16]: array('i', [1, 4, 6, 8])
# Update an element at index 3
In [17]: arr[3] = 7
In [18]: arr
Out[18]: array('i', [1, 4, 6, 7])

```

除了上面提到的操作，`array`模块还提供了一堆可以在数组上执行的其他操作，如反转、弹出、追加、搜索、转换为其他类型等。更多细节可以在[这里找到](https://docs.python.org/3.4/library/array.html)

> 虽然 Python 允许我们在数组上执行各种各样的操作，但是内置的数组模块很少使用。相反，在实际编程中，大多数程序员更喜欢使用 NumPy 库提供的 NumPy 数组。

## 元组

在 Python 数据结构中，元组是标准库的一部分。像数组一样，元组中也包含多个值，用逗号分隔。此外，它还允许将不同类型的值存储在一起。元组是不可变的，通常包含通过解包或索引访问的异构元素序列。

为了创建一个元组，我们将所有元素放在括号`()`中。与数组不同，我们不需要导入任何模块来使用元组。现在让我们看看元组 python 数据结构上的一些操作。

```py
# Creating a tuple 'tup' with elements of the same data type
In [19]: tup = (1, 2, 3)
In [20]: tup
Out[20]: (1, 2, 3)
# Verifying the type
In [21]: type(tup)
Out[21]: tuple
# Creating a tuple 'tupl' with elements of different data types
In [22]: tupl = (1, 'a', 2.5)
In [23]: type(tupl)
Out[23]: tuple

```

上面创建的元组`tupl`可以用以下方式可视化:

| 索引 | Zero | one | Two |
| --- | --- | --- | --- |
| **元素** | one | 一个 | Two point five |

不使用括号也可以创建元组 python 数据结构。

```py
# Creating a tuple without brackets
In [24]: tup = 1, 2, 3
In [25]: type(tup)
Out[25]: tuple

```

我们可以在一个元组中多次重复一个值，如下所示:

```py
In [26]: tupl = (1,) * 5 # Note trailing comma
In [27]: tupl
Out[27]: (1, 1, 1, 1, 1)

```

### 访问元组元素

使用方括号`[]`执行的切片操作用于访问元组元素。我们传递方括号中的索引值来获取我们感兴趣的元素。像数组一样，元组 python 数据结构也有一个索引，所有元素都与特定的索引号相关联。同样，索引从“0”开始。

```py
# Access an element at index 0
In [28]: tup[0]
Out[28]: 1
# Access an element at index 2
In [29]: tup[2]
Out[29]: 1

```

如果我们试图访问一个不存在的元素，Python 会抛出一个错误。换句话说，如果我们对一个不存在的索引使用切片操作，我们将得到一个错误。

```py
In [30]: tup[3]
Traceback (most recent call last):
 File "<ipython-input-30-c965c442ca22>", line 1, in <module>
 tup[3]
IndexError: tuple index out of range

```

在上面的例子中，我们试图访问一个不存在的索引为`3`的元素。因此，Python 抛出了一个错误声明`index out of range`。

内置的`len()`函数用于检查一个元组的长度。

```py
In [31]: len(tup)
Out[31]: 3
In [32]: len(tupl)
Out[32]: 5

```

### 不变

在 Python 数据结构中，元组对象是不可变的。也就是说，一旦创建，就不能修改。如果我们试图修改一个元组，Python 会抛出一个错误。

```py
In [33]: tup[1] = 10
Traceback (most recent call last):
 File "<ipython-input-33-991819cff38c>", line 1, in <module>
 tup[1] = 10
TypeError: 'tuple' object does not support item assignment

```

不出所料，解释器抛出一个错误，将元组对象描述为不可变的。

### 连接元组

Python 允许我们组合两个或更多元组，或者直接将新值连接到现有元组。现在让我们看看如何连接元组 python 数据结构:

```py
In [34]: t1 = (1, 2, 3)
In [35]: t2 = (4, 5)
In [36]: t1 + t2
Out[36]: (1, 2, 3, 4, 5)

```

可以使用运算符`*=`和`+=`将元组连接起来。

```py
In [37]: t1 = (1, 2, 3)
In [38]: t1 += 4, 5
In [39]: t1
Out[39]: (1, 2, 3, 4, 5)

```

### 解包元组

在上面的一个例子中，我们遇到了语句`tup = 1, 2, 3`，它是*元组打包*的一个例子。也就是说，我们将不同的值打包成一个变量`tup`。相反的操作也是可能的:

```py
In [40]: tup
Out[40]: (1, 2, 3)
In [41]: x, y, z = tup

```

上述语句执行*解包*操作。它会将值`1`赋给变量`x`、`2`赋给`y`、`3`赋给`z`。该操作要求等号左侧的变量与元组 python 数据结构中的元素一样多。

### 元组方法

元组是 Python 数据结构中的简单对象之一，更易于维护。只有两种方法可用于元组对象:

*   index():这个方法返回元素的索引。

```py
In [42]: tup
Out[42]: (1, 2, 3)
In [43]: tup.index(3) # Returns the index of value '3'.
Out[43]: 2

```

*   count():这个方法计算一个值出现的次数。

```py
In [44]: tup = (1, 1, 1, 1, 1)
In [45]: tup.count(1)
Out[45]: 5

```

元组 python 数据结构有用的一些原因如下:

*   它们比列表更快。
*   它们保护数据，因为它们是不可变的。
*   它们可以用作字典上的键。

## 列表

一个`list`是一个 python 数据结构，它保存了一个有序的项目集合，也就是说，我们可以在一个列表中存储一个项目的*序列*。在 Python 数据结构中，列表是通过将所有项目放在由逗号分隔的方括号`[]`中创建的。

它可以有任意数量的项目，它们可以是不同的数据类型，并且可以通过以下方式创建:

```py
# Empty list
In [46]: list_a = []
In [47]: list_a
Out[47]: []
# List with integers
In [48]: list_b = [1, 2, 3]
In [49]: list_b
Out[49]: [1, 2, 3]
# List with mixed data types
In [50]: list_c =[1, 2.5, 'hello']
In [51]: list_c
Out[51]: [1, 2.5, 'hello']

```

一个列表也可以有另一个列表作为项目。这被称为*嵌套列表*。

```py
In [52]: a_list = [1, 2, 3, ['hello', 'stock'], 4.5]

```

### 访问列表项目

与任何其他 python 数据结构一样，slice 运算符用于访问列表项或一系列列表项。它可以按以下方式使用。

```py
In [53]: stock_list = ['HP', 'GOOG', 'TSLA', 'MSFT', 'AAPL', 'AMZN', 'NLFX']
# Accessing an element at index 2
In [54]: stock_list[2]
Out[54]: 'TSLA'
# Accessing multiple elements using slicing
In [55]: stock_list[1:4]
Out[55]: ['GOOG', 'TSLA', 'MSFT']
# Accessing last element using negative index
In [56]: stock_list[-1]
Out[56]: 'NLFX'

```

### 更新列表

与元组不同，列表 python 数据结构是可变的。也就是说，我们甚至可以在内容创建之后对其进行更改。同样，切片操作在这里帮助了我们

```py
In [57]: stock_list
Out[57]: ['HP', 'GOOG', 'TSLA', 'MSFT', 'AAPL', 'AMZN', 'NLFX']
# Updating the first element
In [58]: stock_list[0] = 'NVDA'
# Updating the last 3 elements
In [59]: stock_list[-3:] = ['AMD', 'GE', 'BAC']
In [60]: stock_list
Out[60]: ['NVDA', 'GOOG', 'TSLA', 'AMD', 'GE', 'BAC']

```

也可以向现有列表中添加新元素。本质上，列表是 Python 中的一个对象。因此，list 类提供了在 list 对象上使用的各种方法。有两种方法`append()`和`extend()`用于更新现有列表。

*   方法将单个元素添加到列表的末尾。它不返回新列表，只修改原始列表。
*   方法将 list2 中的元素添加到列表的末尾。

```py
In [61]: stock_list
Out[61]: ['HP', 'GOOG', 'MSFT']
In [62]: stock_list.append('AMZN')
In [63]: stock_list
Out[63]: ['HP', 'GOOG', 'MSFT', 'AMZN']

```

在上面的例子中，我们使用`append()`方法添加了一个新元素。让我们向列表中添加多个元素。在 Python 数据结构中，每当我们要向任何对象添加多个文字时，我们都将其包含在列表中，即使用方括号`[]`。我们期望的输出是附加了所有新元素的列表。

```py
In [64]: stock_list.append(['TSLA', 'GE', 'NLFX'])
In [65]: stock_list
Out[65]: ['HP', 'GOOG', 'MSFT', 'AMZN', ['TSLA', 'GE', 'NLFX']]

```

我们得到的产量没有达到我们的预期。Python 将新的元素作为一个元素添加到`stock_list`中，而不是添加三个不同的元素。在 lists python 数据结构中提供了`extend()`方法来实现这一点。

```py
In [66]: stock_list
Out[66]: ['HP', 'GOOG', 'MSFT', 'AMZN']
In [67]: stock_list.extend(['TSLA', 'GE', 'NLFX'])
In [68]: stock_list
Out[68]: ['HP', 'GOOG', 'MSFT', 'AMZN', 'TSLA', 'GE', 'NLFX']

```

为了简化起见，`append()`方法用于向现有列表添加单个元素，它将单个元素作为参数，而`extend()`方法用于向现有列表添加多个元素，它将一个列表作为参数。

### 列表操作

列表是最通用和最常用的 python 数据结构之一。除了上面讨论的方法，我们还有其他有用的方法。其中一些列举如下:

*   `insert(index, element)`:在给定位置插入一个项目。第一个参数是要插入的元素的索引，所以`list.insert(0, element)`在列表的开头插入。

```py
# Inserting an element at index position 1.
In [69]: stock_list.insert(1, 'AAPL')
In [70]: stock_list
Out[70]: ['HP', 'AAPL', 'GOOG', 'MSFT', 'AMZN', 'TSLA', 'GE', 'NLFX']

```

*   `remove(element)`:删除参数中提供的第一个值为`element`的项目。如果没有这样的项目，Python 将抛出一个错误。

```py
# Removing the element 'AAPL'
In [71]: stock_list.remove('AAPL')
In [72]: stock_list
Out[72]: ['HP', 'GOOG', 'MSFT', 'AMZN', 'TSLA', 'GE', 'NLFX']
# Again removing the element 'AAPL'.
In [73]: stock_list.remove('AAPL') # This line will throw an error as there is no element 'AAPL' the list.
Traceback (most recent call last):
 File "<ipython-input-73-8af176c2bd12>", line 1, in <module>
 stock_list.remove('AAPL')
ValueError: list.remove(x): x not in list

```

*   `pop()`:该函数删除并返回列表中的最后一项。如果我们提供`index`作为参数，它将移除列表中给定位置的项目并返回它。注意:这里提供一个参数是可选的。

```py
# Without providing index position as an argument. Returns and removes the last element in the list.
In [74]: stock_list.pop()
Out[74]: 'NLFX'
In [75]: stock_list
Out[75]: ['HP', 'GOOG', 'MSFT', 'AMZN', 'TSLA', 'GE']

```

#提供索引位置作为参数。返回并移除特定位置的元素。In[76]:stock _ list . pop(2)Out[76]:' MSFT ' In[77]:stock _ list Out[77]:['惠普'，'谷歌'，' AMZN '，' TSLA '，'通用电气']

*   `index(element)`:返回参数中第一个值为`element`的项目的索引。如果没有这样的项目，Python 将抛出一个错误。

```py
In [78]: stock_list.index('GOOG')
Out[78]: 1
In [79]: stock_list.index('GE')
Out[79]: 4

```

*   `count(element)`:返回`element`在列表中出现的次数。

```py
# Count the element 'GOOG'
In [80]: stock_list.count('GOOG')
Out[80]: 1
# Appending the same list with 'GOOG'
In [81]: stock_list.append('GOOG')
In [82]: stock_list
Out[82]: ['HP', 'GOOG', 'AMZN', 'TSLA', 'GE', 'GOOG']
# Again, counting the element 'GOOG'
In [83]: stock_list.count('GOOG')
Out[83]: 2

```

*   `sort()`:调用时，该方法返回排序后的列表。排序操作将会就绪。

```py
# Sorting the list. The same list will be updated.
In [84]: stock_list.sort()
In [85]: stock_list
Out[85]: ['AMZN', 'GE', 'GOOG', 'GOOG', 'HP', 'TSLA']

```

*   `reverse()`:该方法反转列表中的元素，执行的操作将就位。

```py
# Reversing the elements within the list.
In [86]: stock_list.reverse()
In [87]: stock_list
Out[87]: ['TSLA', 'HP', 'GOOG', 'GOOG', 'GE', 'AMZN']

```

## 堆栈和队列

list 方法使得将列表用作堆栈或队列变得非常容易。一个*栈*是 python 数据结构之一(虽然在 Python 中不能直接使用),其中最后添加的元素是第一个检索到的元素，也称为*后进先出(LIFO)* 。通过使用`append()`和`pop()`方法，可以将一个列表作为堆栈使用。为了将一个项目添加到堆栈的顶部，我们使用了`append()`，为了从堆栈的顶部检索一个项目，我们使用了没有显式索引的`pop()`。现在，我们将在 python 数据结构教程中看到一些例子:

```py
# (Bottom) 1 -> 5 -> 6 (Top)
In [88]: stack = [1, 5, 6]
In [89]: stack.append(4) # 4 is added on top of 6 (Top)
In [90]: stack.append(5) # 5 is added on top of 4 (Top)
In [91]: stack
Out[91]: [1, 5, 6, 4, 5]
In [92]: stack.pop() # 5 is removed from the top
Out[92]: 5
In [93]: stack.pop() # 4 is removed from the top
Out[93]: 4
In [94]: stack.pop() # 6 is removed from the top
Out[94]: 6
In [95]: stack # Remaining elements in the stack
Out[95]: [1, 5]

```

另一种可以使用 list 方法构建的 python 数据结构是 *queue* ，其中添加的第一个元素是检索的第一个元素，也称为*先进先出(FIFO)* 。考虑一下在售票柜台排队，根据人们到达的顺序为他们提供服务，因此第一个到达的人也是第一个离开的人。

为了实现一个队列，我们需要使用`collections.deque`模块；然而，列表 python 数据结构在这方面效率不高，因为每次插入和删除操作都需要使用大量内存来改变每个元素的位置。

它可以使用`append()`和`popleft()`方法创建。举个例子，

```py
# Import 'deque' module from the 'collections' package
In [96]: from collections import deque
# Define initial queue
In [97]: queue = deque(['Perl', 'PHP', 'Go'])
In [98]: queue.append('R') # 'R' arrives and joins the queue
In [99]: queue.append('Python') # 'Python' arrives and joins the queue
In [100]: queue.popleft() # The first to arrive leaves the queue
Out[100]: 'Perl'
In [101]: queue.popleft() # The second to arrive leaves the queue
Out[101]: 'PHP'
In [102]: queue # The remaining queue in order of arrival
Out[102]: deque(['Go', 'R', 'Python'])

```

## 字典

在 python 数据结构中，字典是项目的无序集合。它将数据存储在*键-值*对中。字典就像一本电话簿，我们可以通过知道一个人的名字来找到他/她的电话号码或联系方式，也就是说，我们将名字*(按键)*与相应的细节*(值)*联系起来。请注意，密钥必须是唯一的，就像它在电话簿中的方式一样，即我们不能有两个名字完全相同的人。

在 dictionary python 数据结构中，使用以下符号在花括号`{}`中指定键和值对:

```py
dictionary = {key1 : value1, key2 : value2, key3 : value3}

```

注意，键值对由冒号`:`分隔，键值对本身由`,`分隔。此外，我们只能使用不可变的对象，如字符串和元组作为字典的键。字典的值可以是可变或不可变的对象。我们创建的字典 python 数据结构是`dict`类的实例，它们是无序的，所以添加键的顺序不一定反映它们被检索回来时的顺序。

### 创建和访问词典

可以使用花括号`{}`或方法`dict()`来创建字典。例如:

```py
# Creating an empty dictionary using {}
In [103]: tickers = {}
In [104]: type(tickers)
Out[104]: dict
# Creating an empty dictionary using the dict() method
In [105]: tickers = dict()
In [106]: type(tickers)
Out[106]: dict

```

让我们用相同数据类型的值创建一个字典。

```py
In [107]: tickers = {'GOOG' : 'Alphabet Inc.',
 ...: 'AAPL' : 'Apple Inc.',
 ...: 'MSFT' : 'Microsoft Corporation'}
In [108]: tickers
Out[108]:
{'GOOG': 'Alphabet Inc.',
 'AAPL': 'Apple Inc.',
 'MSFT': 'Microsoft Corporation'}

```

接下来，我们将创建一个包含多种数据类型的字典。

```py
In [109]: ticker = {'symbol' : 'AAPL',
 ...: 'price' : 224.95,
 ...: 'company' : 'Apple Inc',
 ...: 'founded' : 1976,
 ...: 'products' : ['Machintosh', 'iPod', 'iPhone', 'iPad']}

```

我们还可以提供一个字典作为另一个字典键的值。这样的字典叫做*嵌套字典*。看看下面的例子:

```py
In [110]: tickers = {'AAPL' : {'name' : 'Apple Inc.',
 ...: 'price' : 224.95
 ...: },
 ...: 'GOOG' : {'name' : 'Alphabet Inc.',
 ...: 'price' : 1194.64
 ...: }
 ...: }

```

字典中的键应该是唯一的。如果我们为多个对提供相同的键，Python 将忽略与键相关联的前一个值，只存储最近的值。考虑下面的例子:

```py
In [111]: same_keys = {'symbol' : 'AAPL',
 ...: 'symbol' : 'GOOG'}
In [112]: same_keys
Out[112]: {'symbol': 'GOOG'}

```

在上面的例子中，Python 丢弃了值`AAPL`并保留了分配给同一个键的最新值。一旦我们创建了字典 python 数据结构，我们就可以在各自键的帮助下访问它们。我们使用切片操作符`[]`来访问这些值；然而，我们提供了一个`key`来获取它的值。使用上面创建的字典，我们可以通过以下方式访问值:

```py
In [113]: ticker
Out[113]:
{'symbol': 'AAPL',
 'price': 224.95,
 'company': 'Apple Inc',
 'founded': 1976,
 'products': ['Machintosh', 'iPod', 'iPhone', 'iPad']}
In [114]: tickers
Out[114]:
{'AAPL': {'name': 'Apple Inc.', 'price': 224.95},
 'GOOG': {'name': 'Alphabet Inc.', 'price': 1194.64}}
# Accessing the symbol name
In [115]: ticker['symbol']
Out[115]: 'AAPL'
# Accessing the ticker price
In [116]: ticker['price']
Out[116]: 224.95
# Accessing the product list
In [117]: ticker['products']
Out[117]: ['Machintosh', 'iPod', 'iPhone', 'iPad']
# Accessing the item at position 2 in the product list.
In [118]: ticker['products'][2]
Out[118]: 'iPhone'
# Accessing the first nested dictionary from the 'tickers' dictionary
In [119]: tickers['AAPL']
Out[119]: {'name': 'Apple Inc.', 'price': 224.95}
# Accessing the price of 'GOOG' ticker using chaining operation
In [120]: tickers['GOOG']['price']
Out[120]: 1194.64

```

### 修改字典

字典 python 数据结构中的值可以通过使用赋值运算符`=`为其对应的键赋值来更新。

```py
In [121]: ticker['price']
Out[121]: 224.95
In [122]: ticker['price'] = 226
In [123]: ticker['price']
Out[123]: 226

```

也可以用类似的方式添加新的键-值对。为了添加一个新元素，我们在方括号`[]`中写下新的`key`，并赋予一个新的值。例如:

```py
In [124]: ticker['founders'] = ['Steve Jobs', 'Steve Wozniak', 'Ronald Wayne']
In [125]: ticker
Out[125]:
{'symbol': 'AAPL',
 'price': 226,
 'company': 'Apple Inc',
 'founded': 1976,
 'products': ['Machintosh', 'iPod', 'iPhone', 'iPad'],
 'founders': ['Steve Jobs', 'Steve Wozniak', 'Ronald Wayne']}

```

在上面的例子中，我们添加了键`founders`并将列表`['Steve Jobs', 'Steve Wozniak', 'Ronald Wayne']`指定为值。如果我们要删除字典 python 数据结构中的任何键值对，我们使用内置的`del()`函数如下:

```py
In [126]: del(ticker['founders'])
In [127]: ticker
Out[127]:
{'symbol': 'AAPL',
 'price': 226,
 'company': 'Apple Inc',
 'founded': 1976,
 'products': ['Machintosh', 'iPod', 'iPhone', 'iPad']}

```

### 字典方法

`dict`类提供了各种方法，使用这些方法我们可以执行各种操作。除了这些方法，我们还可以使用内置的`len()`函数来获取字典的长度。

```py
In [128]: len(ticker)
Out[128]: 5
In [129]: len(tickers)
Out[129]: 2

```

现在我们讨论 python 数据结构中由`dict`类提供的一些流行方法。

*   `items()`:该方法返回一个包含调用对象中所有时间的对象。

```py
In [130]: ticker.items()
Out[130]: dict_items([('symbol', 'AAPL'), ('price', 226), ('company', 'Apple Inc'), ('founded', 1976), ('products', ['Machintosh', 'iPod', 'iPhone', 'iPad'])])

```

*   `keys()`:该方法返回调用字典中的所有键。

```py
In [131]: ticker.keys()
Out[131]: dict_keys(['symbol', 'price', 'company', 'founded', 'products'])

```

*   `values()`:该方法返回调用对象中的所有值。

```py
In [132]: ticker.values()
Out[132]: dict_values(['AAPL', 224.95, 'Apple Inc', 1976, ['Machintosh', 'iPod', 'iPhone', 'iPad']])

```

*   `pop()`:这个 python 数据结构方法弹出一个条目，它的关键字作为参数给出。

```py
In [133]: tickers
Out[133]:
{'GOOG': 'Alphabet Inc.',
 'AAPL': 'Apple Inc.',
 'MSFT': 'Microsoft Corporation'}
In [134]: tickers.pop('GOOG')
Out[134]: 'Alphabet Inc.'
In [135]: tickers
Out[135]: {'AAPL': 'Apple Inc.', 'MSFT': 'Microsoft Corporation'}

```

*   `copy()`:顾名思义，这个 python 数据结构方法将调用字典复制到另一个字典。

```py
In [136]: aapl = ticker.copy()
In [137]: aapl
Out[137]:
{'symbol': 'AAPL',
 'price': 224.95,
 'company': 'Apple Inc',
 'founded': 1976,
 'products': ['Machintosh', 'iPod', 'iPhone', 'iPad']}

```

*   `clear()`:这个方法清空调用字典。

```py
In [138]: ticker.clear()
In [139]: ticker
Out[139]: {}

```

*   `update()`:该方法允许从另一个字典添加新的密钥对值。

```py
In [140]: ticker1 = {'NLFX' : 'Netflix'}
In [141]: ticker2 = {'AMZN' : 'Amazon'}
In [142]: new_tickers = {}
In [143]: new_tickers.update(ticker1)
In [144]: new_tickers.update(ticker2)
In [145]: new_tickers
Out[145]: {'NLFX': 'Netflix', 'AMZN': 'Amazon'}

```

## 设置

在 python 数据结构中，集合是一个无序且无索引的项目集合。它是一个集合数据类型，是可变的、可迭代的，并且不包含重复值。Python 中的集合表示集合的数学概念。

在 Python 数据结构中，使用花括号以下列方式编写集合:

```py
In [146]: universe ={'GOOG', 'AAPL', 'NLFX', 'GE'}
In [147]: universe
Out[147]: {'AAPL', 'GE', 'GOOG', 'NLFX'}

```

我们不能通过引用索引(切片操作)来访问集合中的项，因为集合是无序的，项没有索引。但是我们可以使用`for`循环遍历所有项目。

一旦一个集合被创建，我们不能改变它的条目，但是我们可以使用`add()`方法添加新的条目。

```py
In [148]: universe.add('AMZN')
In [149]: universe
Out[149]: {'AAPL', 'AMZN', 'GE', 'GOOG', 'NLFX'}

```

Python 不会再次添加相同的项目，也不会抛出任何错误。

```py
In [150]: universe.add('AMZN')
In [151]: universe.add('GOOG')
In [152]: universe
Out[152]: {'AAPL', 'AMZN', 'GE', 'GOOG', 'NLFX'}

```

为了在集合 python 数据结构中添加多个条目，我们使用了`update()`方法，在列表中添加新的条目。

```py
In [153]: universe.update(['FB', 'TSLA'])
In [154]: universe
Out[154]: {'AAPL', 'AMZN', 'FB', 'GE', 'GOOG', 'NLFX', 'TSLA'}

```

我们可以使用内置的`len()`函数来确定一个集合的长度。

```py
In [155]: len(universe)
Out[155]: 7

```

要移除或删除一个项目，我们可以使用`remove()`或`discard()`设置 python 数据结构方法。举个例子，

```py
In [156]: universe.remove('FB')
In [157]: universe.discard('TSLA')
In [158]: universe
Out[158]: {'AAPL', 'AMZN', 'GE', 'GOOG', 'NLFX'}

```

如果我们试图使用集合中不存在的`remove()`删除一个项目，Python 将抛出一个错误。

```py
In [159]: universe.remove('FB')
Traceback (most recent call last):
 File "<ipython-input-159-3a137a1e6cce>", line 1, in <module>
 universe.remove('FB')
KeyError: 'FB'

```

如果我们试图丢弃一个不在集合中的项目，`discard()`方法不会抛出任何错误。

```py
In [160]: universe
Out[160]: {'AAPL', 'AMZN', 'GE', 'GOOG', 'NLFX'}
In [161]: universe.discard('FB')

```

我们使用`clear()`方法清空集合。

```py
In [162]: universe.clear()
In [163]: universe
Out[163]: set()

```

按照数学符号，我们可以执行集合运算，如并、交、差等。在 Python 中使用 set。让我们看看 python 数据结构教程中的一些例子:

*   我们定义两个集合`tech_stocks`和`fin_stocks`如下:

```py
In [164]: tech_stocks = {'AMD', 'GOOG', 'AAPL', 'WDC'}
In [165]: fin_stocks = {'BAC', 'BMO', 'JPLS'}

```

*   `union()`方法:这个*集合* python 数据结构方法允许在集合之间执行联合。该操作返回两个集合中的所有元素。

```py
# Performs the 'union` operation
In [166]: universe = tech_stocks.union(fin_stocks)
In [167]: universe
Out[167]: {'AAPL', 'AMD', 'BAC', 'BMO', 'GOOG', 'JPLS', 'WDC'} # 'universe' contains all elements of both sets

```

*   `intersection()`方法:这个*集合* python 数据结构方法执行集合之间的交集。它只返回在两个集合中都可用的元素。

```py
In [168]: universe.intersection(fin_stocks)
Out[168]: {'BAC', 'BMO', 'JPLS'} # Only elements present in the 'universe' set and 'fin_stocks` are returned

```

*   `difference()`方法:这个 sets python 数据结构方法执行差运算，返回一个包含调用对象所有元素的集合，但不包括第二个集合的元素。

```py
In [169]: universe.difference(fin_stocks)
Out[169]: {'AAPL', 'AMD', 'GOOG', 'WDC'} # All elements of the 'universe' set is returned except elements of the 'fin_stock'

```

*   `issubset()`方法:这个 sets python 数据结构方法检查调用集合的所有元素是否存在于第二个集合中。如果调用集合是第二个集合的子集，则返回 true，否则返回 false。

```py
In [170]: fin_stocks.issubset(universe) # True, as the 'universe' contains all elements of the 'fin_stocks'
Out[170]: True
In [171]: universe.issubset(tech_stocks) # Can you guess why it resulted in to False?
Out[171]: False

```

*   `isdisjoint()`方法:这个设置 python 数据结构的方法检查两个集合之间的交集。如果调用集合与第二个集合不相交，则返回 true，否则返回 false。

```py
In [172]: fin_stocks.isdisjoint(tech_stocks) # True, none of the set contains any element of each other
Out[172]: True
In [173]: fin_stocks.isdisjoint(universe) # False, the 'universe' set contains elements of the 'fin_stocks' set
Out[173]: False

```

*   `issuperset()`方法:这个 sets python 数据结构方法检查调用集合是否包含第二个集合的所有元素。如果调用集合包含第二个集合的所有元素，则返回 true，否则返回 false。

```py
In [174]: universe.issuperset(fin_stocks) # True, the 'universe' set contains all elements of the 'fin_stocks'
Out[174]: True
In [175]: universe.issuperset(tech_stocks) # True, the 'universe' set contains all elements of the 'tech_stocks'
Out[175]: True
In [176]: fin_stocks.issuperset(universe) # False, the 'fin_stocks' set does not contains all elements of the 'universe' set
Out[176]: False

```

## 结论

在本 python 数据结构教程中，我们了解到它们是编写程序的基本构件。我们还学习了数组、列表、元组、字典和集合。除了它们的用途，我们还研究了可以在这些 python 数据结构上执行的不同操作。

重申一下，Python 数据结构教程是从 [Python 基础手册](https://www.quantinsti.com/python-basics-handbook)中摘录的，它是为这两者而创建的；刚开始使用 [Python](https://quantra.quantinsti.com/course/python-for-trading) 的新手，以及有成就的交易者，他们可以在编写策略时使用它作为方便的参考。

请在下面的评论中告诉我们你是否喜欢这篇文章和任何其他反馈。

*免责声明:股票市场的所有投资和交易都涉及风险。在金融市场进行交易的任何决定，包括股票或期权或其他金融工具的交易，都是个人决定，只能在彻底研究后做出，包括个人风险和财务评估以及在您认为必要的范围内寻求专业帮助。本文提到的交易策略或相关信息仅供参考。T3】*