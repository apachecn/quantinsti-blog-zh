# Python 函数教程:定义、类型、命名空间和范围

> 原文：<https://blog.quantinsti.com/python-function-tutorial/>

杰伊·帕尔马

今天，我们将探索几乎所有编程语言中都有的一个非常方便的特性:函数。Python 及其生态系统中有许多奇妙的内置函数。然而，作为 Python 程序员，我们经常需要编写自定义函数来解决我们特有的问题。这是函数的定义。

函数是一段代码(执行特定的任务),只有在被调用时才会运行。

从定义中可以推断出，编写这样的代码块，即函数，提供了如下好处

*   可重用性:在 python 函数中编写的代码可以在需要的时候被调用。因此，可以重用相同的代码，从而减少代码的总行数。
*   *模块化方法*:编写 python 函数隐含地遵循模块化方法。我们可以将我们试图解决的整个问题分解成更小的块，每个块依次通过一个函数来实现。

我们将在本 python 函数教程中讨论以下几点:

*   [内置 python 函数](#Built)
*   [用户定义的 python 函数](#User)
*   [变量名称空间和作用域](#Variable)
*   [λpython 函数](#Lambda)

在编写程序时，Python 函数可以被认为是构建模块，随着我们的程序不断变得更大、更复杂，函数有助于使它更有组织、更易于管理。它们允许我们给代码块起一个名字，允许我们在程序的任何地方使用给定的名字运行代码块任意次。这被称为*调用*一个 python 函数。例如，如果我们想计算一个列表的长度，我们调用一个内置的`len`函数。使用任何 python 函数意味着我们调用它来执行它被设计的任务。

我们需要在调用`len`函数时向它提供一个输入。我们提供给 python 函数的输入被称为*参数*。它可以是数据结构、字符串、值或引用它们的变量。根据功能的不同，函数可以有单个或多个参数。

python 函数有三种类型:

*   内置的 python 函数，比如在标准输出设备上打印的`print`，检查对象数据类型的`type`等。这些是 Python 提供的用于完成常见任务的函数。
*   用户定义的 python 函数:顾名思义，这些是帮助/解决/完成特定任务的自定义函数。
*   匿名 python 函数，也称为 lambda 函数，是定制的，没有任何名称标识符。

## 内置 python 函数

内置函数是 Python 提供的函数。我们现在将讨论其中的几个:

*   `type(object)`用于检查*对象*的数据类型。

*   `float([value])`返回由数字或字符串*值*构造的浮点数。

*   `int([value])`返回一个由浮点或字符串*值*构造的整数对象，如果没有给定参数，则返回 0。

*   `round(number[, ndigits])`用于将浮点数*的*四舍五入到 *ndigits* 指定的位数。

*   `abs(value)`返回作为参数提供的*值*的绝对值。

*   `format(value[, format_spec])`将一个*值*转换成一个‘格式化’的表示，由 *format_spec* 控制。

*   `str([object])`返回一个字符串版本的*对象*。如果未提供对象，则返回空字符串。

*   `bool([value])`返回一个布尔值，即`True`或`False`之一。*值*使用标准真值测试程序[1]进行转换。如果*值*为假或省略，则返回`False`；否则，它返回`True`。

*   `dir([object])`当未提供参数时，返回当前局部范围内的名称列表。如果使用参数，它会尝试返回该对象的有效属性列表。

*   `len(object)`返回一个*对象*的长度(项目数)。参数可以是序列(如字符串、字节、元组、列表或范围)或集合(如字典、集合或冻结集)。

值得注意的是，几乎所有内置 python 函数都接受一个或多个参数，对其执行特定操作并返回输出。随着我们 python 学习之旅的进展，我们将继续学习更多的内置 Python 函数。关于各种内置函数的更多信息可以从 Python 官方文档中获得

## 用户定义的 python 函数

尽管 python 提供了大量的内置 Python 函数，但它不足以解决我们在开发程序和应用程序时会遇到的问题。作为 Python 程序员，我们可能需要将编程挑战分解成更小的块，并以自定义或*用户定义的*函数的形式实现它们。编写函数的概念可能是任何编程语言的基本特征。

函数是用关键字`def`定义的，后面跟着一个*标识符*名和括号，最后是结束一行的冒号。构成函数的*主体*的语句块遵循*函数定义*。这里有一个简单的例子。

```py
def greet():
 """Block of statement.
 or Body of function."""
 print(' Hello from inside the function!')

```

上面定义的`greet`函数可以用它的名字调用，如下所示。

```py
# Calling the function
greet()

```

输出将会是

```py
Hello from inside the function.
```

### 只有一个参数的 Python 函数

我们可以任意多次调用一个函数，Python 会执行函数体中的语句。我们上面提到的 python 函数，既不接受任何输入，也不返回任何输出。它只是打印写在里面的语句。如果函数必须接受任何输入，那么在函数定义期间，它会作为一个*参数*放在括号中。参数是我们提供给函数的值，这样函数就可以利用这些值做一些事情。

请注意这里使用的术语:

*   *参数*:它们在函数定义中的括号内指定，用逗号分隔。
*   *Arguments* :当我们调用一个 python 函数时，参数的取值将以逗号分隔的格式作为参数给出。

上述简单 python 函数的修改版本解释了这两个术语:

```py
# Here 'person_name' is a parameter.
def greet(person_name):
 """Prints greetings along with the value received via the parameter."""
 print('Hello ' + person_name + '!')

```

上面的函数定义将`person_name`定义为函数`greet`的一个参数，可以如下调用:

```py
# Calling the function
greet('Amigo')

```

上面对函数`greet`的调用将字符串`Amigo`作为参数，输出如下:

```py
Hello Amigo!
```

### 带有多个参数和一个`return`语句的 Python 函数

上面定义的两个版本的`greet` python 函数实际上在它们执行的功能方面都很简单。函数能够执行的另一个功能是使用关键字`return`向调用语句返回值。考虑一个函数，它接受几个参数，对其执行一些数学计算并返回输出。例如:

```py
# Function with two parameters 'a' and 'b'
def add(a, b):
 """Computes the addition and returns the result.
 It does not implement the print statement."""
 result = a + b # Computes addition
 return result # Returns the result variable

```

这个用户定义函数`add`接受两个参数`a`和`b`，将它们相加，并将其输出赋给一个变量`result`，最终将该变量返回给调用语句，如下所示:

```py
# Calling the add function
x = 5
y = 6
print(f'The addition of {x} and {y} is {add(x, y)}.')

```

我们用两个参数`x`和`y`调用函数`add`(因为函数定义有两个参数)，分别用`5`和`6`初始化，函数返回的加法通过`print`语句打印出来，如下所示:

```py
The addition of 5 and 6 is 11.
```

类似地，python 函数也可以基于实现返回多个值。下面的函数演示了同样的情况。

```py
# Function definition
def upper_lower(x):
 """Returns the upper and lower version of the string.
 The value must be a string, else it will result in an error.
 This function does not implement any error handling mechanism."""
 upper = x.upper() # Convert x to upper string
 lower = x.lower() # Convert x to lower string
 return upper, lower # Return both variables upper and lower

```

上面的`upper_lower`函数接受一个参数`x`(一个字符串)并将其转换成它们的大写和小写版本。让我们调用它，看看输出。

> 注意:函数 upper_lower 隐式地假设有一个字符串作为参数。调用时提供整数或浮点值作为参数将导致错误。

```py
# Calling the function
upper, lower = upper_lower('Python')
# Printing output
print(upper)
PYTHON
print(lower)
python

```

这里，对`upper_lower`函数的调用被分配给了两个变量`upper`和`lower`，因为该函数返回两个值，这两个值将分别被解包到每个变量中，同样的情况可以在上面显示的输出中得到验证。

### 带默认参数的 Python 函数

比方说，我们正在编写一个接受多个参数的函数。通常，这些参数中的一些有共同的值。在这种情况下，我们希望能够在不明确指定每个参数的情况下调用函数。换句话说，我们希望一些参数有默认值，当它们没有在函数调用中被指定时，这些默认值将被使用。

要使用默认参数值定义 python 函数，我们需要在定义函数时为感兴趣的参数赋值。

```py
def power(number, pow=2):
 """Returns the value of number to the power of pow."""
 return number**pow

```

请注意，上面的 python 函数计算第一个参数的第二个参数的幂。后者的默认值为 2。所以现在当我们只使用一个参数调用 python 函数`power`时，它将被赋值给`number`参数，返回值将通过平方`number`得到。

```py
# Calling the power function only with required argument
print(power(2))
# Output
4

```

换句话说，第二个参数`pow`的参数值是可选的。如果我们想计算不同幂的数字，我们显然可以为它提供一个值，python 函数将返回相应的值。

```py
# Calling the power function with both arguments
print(power(2, 5)
# Output
32

```

python 函数中可以有任意数量的默认值参数。但是请注意，它们必须跟在定义中的非默认值参数后面。否则，Python 将抛出如下所示的错误:

```py
# Calling the power function that will throw an error
def power(pow=2, number):
 """Returns the raised number to the power of pow."""
 return number**pow
 File "<ipython-input-57-9d342db32aba>", line 1
 def power(pow=2, number):
 ^
SyntaxError: non-default argument follows default argument

```

### 具有可变长度参数的 Python 函数

让我们考虑一个场景，作为开发人员，我们不确定用户在调用 python 函数时想要传递多少个参数。例如，一个函数接受浮点数或整数(不管它们有多少)作为参数，并返回它们的和。我们可以实现如下所示的场景:

```py
def sum_all(*args):
 """Sum all values in the *args."""
 # Initialize result to 0
 result = 0
 # Sum all values
 for i in args:
 result += i
 # Return the result
 return result

```

在 python 函数定义中，可变参数被写成`*`，后跟参数名。参数`args`前面的`*`表示该参数长度可变。Python 然后将它解包到一个同名的*元组*中，这个元组可以在函数中使用。在上面的例子中，我们将变量`result`初始化为 0，它将保存所有参数的总和。然后我们循环遍历`args`来计算总和，并在每次迭代中更新`result`。最后，我们将总和返回给调用语句。可以使用任意数量的参数调用`sum_all` python 函数，它会将所有参数相加，如下所示:

```py
# Calling the sum_all function with arbitrary number of arguments.
print(sum_all(1, 2, 3, 4, 5))
# Output
15
# Calling with different numbers of arguments.
print(sum_all(15, 20, 6))
# Output
41

```

这里，`*args`被用作参数名(*参数*的简写)，但是我们可以使用任何有效的标识符作为参数名。它只需要在前面加一个`*`就可以使它的长度灵活。在同样的行中，Python 提供了另一种风格的灵活参数，前面有两个星号标记。使用时，它们被解释器解压到*字典*(同名)中，并且可以在函数中使用。例如:

```py
def info(**kwargs):
 """Print out key-value pairs in **kwargs."""
 # Run for loop to prints dictionary items
 for key, value in kwargs.items():
 print(key + ': ' + value)

```

这里，参数`**kwargs`被称为*关键字参数*，它们将被转换成同名的字典。然后我们对它进行循环，并打印所有的键和值。同样，使用不同于`kwargs`的标识符作为参数名是完全有效的。可以如下调用`info` python 函数:

```py
# Calling the function
print(info(ticker='AAPL', price='146.83', name='Apple Inc.', country='US'))
# Output
ticker: AAPL
price: 146.83
name: Apple Inc.
country: US

```

这就是所有关于默认和灵活的参数。我们现在试图转向 python 函数的文档部分。

### 文档字符串

Python 有一个很棒的特性，叫做*文档字符串*，通常用它的简称*文档字符串*来指代。这是一个重要但不是必需的工具，我们每次写程序时都应该使用，因为它有助于更好地记录程序，并使程序更容易理解。

文档字符串写在定义头后面的三个单引号/双引号内。它们写在 python 函数的第一个逻辑行。文档字符串不仅限于函数；它们也适用于模块和类。docstring 遵循的约定是多行字符串，其中第一行以大写字母开始，以点结束。第二行是空白，从第三行开始是任何详细的解释。强烈建议所有文档字符串都遵循这一约定。让我们通过一个例子来看看这一点:

```py
def power(x, y):
 """Equivalent to x**y or built-in pow() with two arguments.
 x and y should be numerical values else an appropriate error will be thrown for incompatible types.
 Parameters:
 x (int or float): Base value for the power operation.
 y (int or float): Power to which base value should be raised.
 Returns:
 int or float: It returns x raised to the power of y.
 """
 try:
 return x ** y
 except Exception as e:
 print(e)

```

上面定义的 python 函数`power`将参数`x`的提升值返回给`y`。我们感兴趣的是写在`'''`中的 docstring，它记录了函数。我们可以使用任何函数的`__doc__`属性(注意该函数的*双下划线*)来访问该函数的 docstring。可以使用以下代码访问`power`函数的 docstring:

```py
print(power.__doc__)

```

输出如下所示:

```py
Equivalent to x**y or built-in pow() with two arguments.
x and y should be numerical values else an appropriate error will be thrown for incompatible types.
Parameters:
x (int or float): Base value for the power operation.
y (int or float): Power to which base value should be raised.
Returns:
int or float: It returns x raised to the power of y.
```

我们已经在前面的章节中看到了 docstrings 的间接用法。当我们在 python 中使用 Python 函数`help`时，它会显示 docstring。它所做的是获取该函数的`__doc__`属性，并以简洁的方式显示出来。如果我们使用`print(help(power))`请求关于用户定义的`power`的帮助，Python 将返回与我们使用`print(power.__doc__)`得到的相同的输出，如上所示。

### 嵌套 python 函数和非局部变量

嵌套 python 函数是在另一个函数内部定义的函数。嵌套函数的语法与任何其他 python 函数的语法相同。尽管嵌套函数的应用在本质上是复杂的，有时也是有限的，即使在量子领域也是如此，但还是值得一提，因为我们可能会在野外遇到这种情况。下面是一个演示嵌套 python 函数的示例。

```py
# Defining nested function
def outer():
 """ This is an enclosing function """
 def inner():
 """ This is a nested function """
 print('Got printed from the nested function.')
 print('Got printed from the outer function.')
 inner()

```

我们定义了 python 函数`outer`，其中嵌套了另一个 python 函数`inner`。`outer`函数被称为包围函数的*，而`inner`被称为*嵌套*函数。它们有时也被称为*内部*函数。在调用`outer`函数时，Python 将依次调用嵌套在其中的`inner`函数并执行它。同样的输出如下所示:*

```py
# Calling the 'outer' function
outer()
# Output
Got printed from the outer function.
Got printed from the nested function.

```

我们在这里得到的输出是直观的。首先，`outer`函数中的`print`语句被执行，然后是`inner`函数中的`print`语句。此外，嵌套函数可以访问封闭函数的变量。即外部函数中定义的变量可以被内部函数访问。但是，内部或嵌套 python 函数不能修改外部或封闭 python 函数中定义的变量。

```py
def outer(n):
 number = n
 def inner():
 print('Number =', number)
 inner()

```

对`outer`函数的调用将打印以下内容

```py
outer(5)
# Output
Number = 5

```

虽然变量`number`没有在`inner`函数中定义，但是它可以访问并打印`number`。这是可能的，因为 Python 提供了范围机制。我们将在下一节详细讨论这一点。现在考虑一下，如果我们希望嵌套的 python 函数修改在封闭 python 函数中声明的变量，会怎么样呢？Python 的默认行为不允许这样做。如果我们试图修改它，我们将面临一个错误。为了处理这种情况，关键字`nonlocal`就来了。

在嵌套 python 函数中，我们使用关键字`nonlocal`来创建和更改封闭 python 函数中定义的变量。在下面的例子中，我们改变了变量`number`的值。

```py
def outer(n):
 number = n
 def inner():
 nonlocal number
 number = number ** 2
 print('Square of number =', number)
 print('Number =', number)
 inner()
 print('Number =', number)

```

对`outer` python 函数的调用现在将打印作为参数传递给它的数字、它的平方和新更新的数字(只是平方的数字)。

```py
outer(3)
# Output
Number = 3
Square of number = 9
Number = 9

```

请记住，为变量赋值只会在特定的 python 函数(或范围)内创建或更改变量，除非它们是使用非局部语句声明的。

## 变量的命名空间和作用域

如果我们阅读了*Python 的禅宗*(在 Python 控制台中尝试`import this`)，最后一行声明**名称空间是一个非常棒的想法——让我们做更多这样的事情吧！**让我们试着理解这些神秘的名称空间是什么。然而，在此之前，花点时间了解一下 Python 环境中的*名称*是值得的。

### Python 世界中的名称

一个*名*(也称为标识符)就是给一个对象起的名字。从 Python 基础知识中，我们知道 Python 中的一切都是对象。名称是访问底层对象的一种方式。让我们创建一个名为`price`的值为 144 的新变量，并检查 python 函数`id`可访问的*内存位置标识符*。

```py
# Creating new variable
price = 144
# Case 1: Print memory id of the variable price
print(id(price))
# Case 1: Output
1948155424
# Case 2: Print memory id of the absolute value 144
print(id(144))
# Case 2: Output
1948155424

```

有趣的是，我们看到两种情况下的内存位置(变量及其赋值)是相同的。换句话说，两者都引用同一个整数对象。如果您在工作站上执行上述代码，内存位置几乎肯定会不同，但对于变量和值来说是相同的。让我们给它增添更多的乐趣。考虑以下代码:

```py
# Assign price to old_price
old_price = price
# Assign new value to price
price = price + 1
# Print price
print(price)
# Output
145
# Print memory location of price and 145
print('Memory location of price:', id(price))
print('Memory location of 145:', id(145))
# Output
Memory location of price: 1948155456
Memory location of 145: 1948155456
# Print memory location of old_price and 144
print('Memory location of old_price:', id(old_price))
print('Memory location of 144:', id(144))
# Output
Memory location of old_price: 1948155424
Memory location of 144: 1948155424

```

我们将变量`price`的值增加了 1 个单位，看到它的内存位置发生了变化。您可能已经猜到，整数对象`145`的内存位置也将与`price`的内存位置相同。但是，如果我们检查变量`old_price`的内存位置，它将指向整数对象`144`的内存位置。这很有效，因为 Python 不需要创建重复的对象。这也使得 Python 功能强大，因为名字可以指代任何对象，甚至是函数。注意，python 函数也是 Python 中的对象。既然我们知道了 Python 中名称的本质，我们就可以仔细研究名称空间了。

### 命名空间

名字冲突在现实生活中时有发生。比如我们经常看到一个教室里有多个同名 X 的学生。如果有人必须呼叫学生 X，那么在确定哪个学生 X 实际上被呼叫时会有冲突的情况。在打电话时，可以使用学生的姓和名来确保打给正确的学生 x。

同样，这种冲突也会出现在编程中。当程序很小而没有任何外部依赖时，拥有唯一的名字是容易和可管理的。当程序变得更大和外部模块被合并时，事情开始变得复杂。当程序跨越数百行时，为程序中的所有对象指定唯一的名称变得困难和令人厌烦。

命名空间可以被认为是一个命名系统，以避免名称之间的歧义，并确保程序中的所有名称都是唯一的，并且可以在没有任何冲突的情况下使用。在 Python 中，大多数名称空间都是作为字典来实现的。有一个名称到对象的映射，名称作为键，对象作为值。多个名称空间可以使用相同的名称，并将其映射到不同的对象。名称空间是在不同的时刻创建的，具有不同的生存期。命名空间的示例有:

*   内置名称集:它包括内置函数和内置异常名称。
*   模块中的全局名称:它包括从程序中导入的各种模块的名称。
*   函数中的局部名字:它包括函数内部的名字。它是在调用 python 函数时创建的，一直持续到函数返回。

关于名称空间，需要知道的重要一点是，不同名称空间中的名称之间绝对没有关系；也就是说，两个不同的模块可以包含一个函数`sum`而没有任何冲突或混淆。但是，在使用它们时，必须以模块名为前缀。

### 领域

到目前为止，我们一直在程序的任何地方使用对象。然而，需要注意的一件重要事情是，并不是所有的对象在程序中的任何地方都是可访问的。这就是范围概念的由来。*范围*是 Python 程序的一个区域，在这里可以直接访问名称空间。即当对名称(列表、元组、变量等)的引用。)之后，Python 会尝试在名称空间中查找这个名称。不同类型的范围是:

*局部范围*:在局部范围内定义的名字意味着它们是在 python 函数内定义的。它们只能在函数中访问。在函数内部定义的名字不能在函数外部访问。一旦函数的执行结束，局部作用域内的名字就不复存在了。下图说明了这一点:

```py
# Defining a function
def print_number():
 # This is local scope
 n = 10
 # Printing number
 print('Within function: Number is', n)
print_number()
# This statement will cause error when executed
print('Outside function: Number is', n)
# Output
Within function: Number is 10
Traceback (most recent call last):
 File "<ipython-input-2-f44bdaae6d53>", line 8, in <module>
 print('Outside function: Number is', n)
NameError: name 'n' is not defined

```

*封闭作用域*:封闭作用域中的名字是指在封闭函数中定义的名字。当引用的名称在本地范围内不可用时，将在封闭范围内进行搜索。这就是所谓的范围解析。下面的例子有助于我们更好地理解这一点:

```py
# This is enclosing / outer function
def outer():
 number = 10
 # This is nested / inner function
 def inner():
 print('Number is', number)
 inner()
outer()
# Output
Number is 10

```

我们试图在没有定义变量`inner`的函数中打印变量`number`。因此，python 试图在作为封闭 Python 函数的`outer`函数中找到变量。如果在封闭范围内也找不到该变量怎么办？Python 将试图在我们接下来讨论的*全局*范围内找到它。

*全局作用域*:全局作用域中的名字意味着它们是在程序的主脚本中定义的。几乎在程序的任何地方都可以访问它们。考虑下面的例子，我们在函数定义之前定义了一个变量`n`(即在全局范围内),并在 python 函数中定义了另一个同名的变量`n`。

```py
# Global variable
n = 3
def relu(val):
 # Local variable
 n = max(0, val)
 return n
print('First statement: ', relu(-3))
print('Second statement:', n)
# Output
First statement: 0
Second statement: 3

```

这里，第一个 print 语句调用值为`-3`的`relu`函数，该函数将最大值赋值为 0，并将最大值赋给变量`n`，该变量又被返回，从而打印出 0。接下来，我们尝试打印`n`和 Python 打印`3`。这是因为 Python 现在引用了函数外部(全局范围内)定义的变量`n`。因此，我们得到了两个不同的值`n`,因为它们位于不同的范围内。这给我们带来了一个显而易见的问题，如果变量不是在局部范围内定义的，而是在全局范围内可用，并且我们试图访问那个全局变量，那该怎么办？答案很直观，我们将能够在 python 函数中访问它。然而，它是一个只读变量，因此我们不能修改它。试图修改全局变量会导致如下所示的错误:

```py
# Global variable
number = 5
# Function that updates the global variable
def update_number():
 number = number + 2
 print('Within function: Number is', number)
# Calling the function
update_number()
print('Outside function: Number is', number)
# Output
Traceback (most recent call last):
 File "<ipython-input-8-267134da25e4>", line 8, in <module>
 update_number()
 File "<ipython-input-8-267134da25e4>", line 4, in update_number
 number = number + 2
UnboundLocalError: local variable 'number' referenced before assignment

```

为了处理这种需要修改全局名称的情况，我们在 python 函数中定义了全局名称，后跟关键字`global`。`global`关键字允许我们在局部范围内访问全局名称。让我们运行上面的代码，但是使用`global`关键字。

```py
# Global variable
number = 5
# Function that updates the global variable
def update_number():
 global number
 number = number + 2
 print('Within function: Number is', number)
# Calling the function
update_number()
print('Outside function: Number is', number)
# Output
Within function: Number is 7
Outside function: Number is 7

```

关键字`global`允许我们从局部范围修改全局变量，没有任何问题。这与关键字`non-local`非常相似，它允许我们修改封闭范围中定义的变量。

*内置作用域*:该作用域由 Python 内置模块中预定义的名称组成，如`sum`、`print`、`type`等。尽管我们既没有在程序中的任何地方定义这些 python 函数，也没有从任何外部模块中导入它们，但是它们总是可以使用的。

总而言之，在执行 Python 代码时，会按以下顺序在各种范围内搜索名称:

1.  当地的
2.  封闭
3.  全球的
4.  内置的

如果在任何范围内都找不到它们，Python 将抛出一个错误。

## Lambda python 函数

我们已经使用`def`关键字、函数头、文档字符串和函数体编写了上面的函数。用 Python 编写动态函数有一种更快的方法，它们被称为 lambda 函数。它们有时也被称为匿名 python 函数。我们用关键字`lambda`来写这样的函数。lambda 函数的语法如下:

```py
lambda arguments: expression

```

首先，语法显示没有 python 函数名。其次，*实参*指参数，最后，*表达式*描绘了 python 函数体。让我们创建一个 python 函数`square`，它对提供给它的参数求平方并返回结果。我们使用关键字`def`创建这个 python 函数。

```py
# Function defnition
def square(arg):
 """Computes the square of an argument and returns the result.
 It does not implement the print statement."""
 result = arg * arg
 return result
# Calling the function and printing its output
print(square(3))
# Output
9

```

上面定义的 python 函数`square`可以使用关键字`lambda`重写为一行，如下所示:

```py
# Creating a lambda function and assigning it to square
square = lambda arg: arg * arg
# Calling the lambda function using the name 'square'
print(square(3))
# Outpuut
9

```

在上面的 lambda python 函数中，它接受一个由 *arg* 表示的参数，并返回它的平方。Lambda python 函数在定义期间，在关键字`lambda`之后可以有任意数量的参数。为了理解多个参数是如何工作的，我们将把我们的讨论限制到两个参数。我们创建另一个 lambda 函数，将第一个参数提升到第二个参数的幂。

```py
# Creating a lambda function to mimic 'raise to power' operation
power = lambda a, b: a ** b
# Calling the lambda function using the name 'power'
print(power(2, 3))
# Output
8

```

Lambda python 函数与内置的`map`和`filter`函数一起被广泛使用。

### `map()`功能

`map`函数有两个参数:一个函数和一个序列，比如一个列表。这个 python 函数创建了一个迭代器，它将函数应用于序列的每个元素。我们可以将 lambda python 函数传递给这个`map`函数，甚至不用命名它。在这种情况下，我们将 lambda 函数称为匿名函数。在下面的例子中，我们创建了一个由数字组成的列表`nums`，并将其传递给一个`map`函数和 lambda 函数，后者将对列表中的每个元素求平方。

```py
# Creating a list of all numbers
nums = [1, 2, 3, 4, 5]
# Defining a lambda function to square each number and passing it as an argument to map function
squares = map(lambda num: num ** 2, nums)

```

上例中的 lambda python 函数将对列表`nums`中的每个元素求平方，map 函数将每个输出映射到原始列表中的相应元素。然后，我们将结果存储到一个名为`squares`的变量中。如果我们打印出`square`变量，Python 会告诉我们这是一个地图对象。

```py
# Printing squares
print(squares)
# Output
<map object at 0x00000000074EAD68>

```

要查看该对象包含的内容，我们需要使用如下所示的`list` python 函数将其转换为 list:

```py
# Casting map object squares to a list and printing it
print(list(squares))
# Output
[1, 4, 9, 16, 25]

```

### `filter()`功能

`filter`函数有两个参数:一个函数或`None`和一个序列。这个函数提供了一种从列表中过滤掉不满足特定标准的元素的方法。在嵌入 lambda 函数之前，让我们先了解一下它是如何工作的。

```py
# Creating a list of booleans
booleans = [False, True, True, False, True]
# Filtering 'booleans', casting it to a list, and finally printing it
print(list(filter(None, booleans)))
# Output
[True, True, True]

```

在上面的例子中，我们首先创建一个随机布尔值列表。接下来，我们将它和指定返回为真的项目的`None`一起传递给`filter`函数。最后，我们将`filter`函数的输出转换为一个列表，因为它输出一个过滤器对象。在更高级的场景中，我们可以在`filter`函数中嵌入一个 lambda 函数。假设我们有一个场景，我们需要从一组给定的字符串中过滤出所有长度大于 3 的字符串。我们可以一起使用 filter 和 lambda 函数来实现这一点。下图说明了这一点:

```py
# Creating a pool of random strings
strings = ['one', 'two', 'three', 'four', 'five', 'six']
# Filtering strings using a lambda and filter functions
filtered_strings = filter(lambda string: len(string) > 3, strings)
# Casting 'filtered_strings' to a list and printing it
print(list(filtered_strings))
# Output
['three', 'four', 'five']

```

在上面的例子中，在`filter`函数中使用了 lambda python 函数，它检查`strings`列表中每个字符串的长度。然后`filter`函数将过滤出与 lambda 函数定义的标准相匹配的字符串。

除了上面讨论的`map`和`filter` python 函数，现在我们将学习另一个方便的函数`zip`，它可以用于同时遍历多个序列。

### `zip()`功能

作为普通的电脑用户，我们经常会遇到带有*的文件。zip* 扩展名又名 zip 文件。基本上，这些文件是压缩了其他文件的文件。换句话说，zip 文件就像一个容纳其他文件的容器。

在 Python 的世界里，`zip` python 函数或多或少地充当了可迭代对象的容器，而不是真正的文件。`zip`的语法如下所示:

```py
zip(*iterables)

```

它将一个 iterable 作为输入，并返回一个迭代器，该迭代器从每个 iterable 中聚合元素。输出包含一个元组的迭代器。迭代器中的第*个*元素是由每个输入的第*个*元素组成的元组。如果输入中的可迭代对象大小不相等，当最短的输入可迭代对象用尽时，输出迭代器停止。如果没有输入，它将返回一个空迭代器。让我们借助一个例子来理解`zip`的工作原理。

```py
# Defining iterables for the input
tickers = ['AAPL', 'MSFT', 'GOOG']
companies = ['Apple Inc', 'Microsoft Corporation', 'Alphabet Inc']
# Zipping the above defined iterables using the 'zip'
zipped = zip(tickers, companies)

```

我们定义了两个列表`tickers`和`companies`，它们被用作`zip`的输入。`zipped`对象是`zip`类型的迭代器，因此我们可以使用循环技术对其进行迭代以打印其内容:

```py
# Iterating over a zipped object
for ticker, company in zipped:
 print('Ticker name of {} is {}.'.format(ticker, company))
# Output
Ticker name of AAPL is Apple Inc.
Ticker name of MSFT is Microsoft Corporation.
Ticker name of GOOG is Alphabet Inc.

```

或者很容易将其转换为顺序数据结构，如列表或元组。

```py
# Casting the zip object to a list and printing it
print(list(zipped))
# Output
[('AAPL', 'Apple Inc.'),
 ('MSFT', 'Microsoft Corporation'),
 ('GOOG', 'Alphabet Inc.')]

```

正如我们所料，压缩对象包含一个元组序列，其中的元素来自相应的输入。一个`zip`对象和`*`一起像以前一样解压元素。例如:

```py
# Unzipping the zipped object
new_tickers, new_companies = zip(*zipped)
# Printing new unzipped sequences
print(new_tickers)
('AAPL', 'MSFT', 'GOOG')
print(new_companies)
('Apple Inc.', 'Microsoft Corporation', 'Alphabet Inc.')

```

我们将 zip 对象`zipped`解压成两个序列`new_tickers`和`new_companies`。通过打印这些序列，我们可以看到操作成功了，元素成功地解压缩到各自的元组中。

## 结论

因此，我们已经看到了不同类型的 python 函数以及如何调用它们。我们还看到了 python 函数如何让我们的编程生活变得更加轻松。我们还看到了 python 函数中的名称空间及其范围。

如果你想学习算法交易的各个方面，那就去看看算法交易的高管课程( [EPAT](https://www.quantinsti.com/) )。课程涵盖统计学&计量经济学、金融计算&技术和算法&定量交易等培训模块。EPAT 教你在算法交易中建立一个有前途的职业所需的技能。[立即报名！](https://www.quantinsti.com/epat/)

*免责声明:本文中提供的所有数据和信息仅供参考。QuantInsti 对本文中任何信息的准确性、完整性、现时性、适用性或有效性不做任何陈述，也不对这些信息中的任何错误、遗漏或延迟或因其显示或使用而导致的任何损失、伤害或损害承担任何责任。所有信息均按原样提供。*