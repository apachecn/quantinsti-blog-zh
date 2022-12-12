# Python 中的面向对象编程(OOP)

> 原文：<https://blog.quantinsti.com/object-oriented-programming-python/>

杰伊·帕尔马

Python 作为一种通用编程语言，支持多种编程范式，即过程式、函数式和面向对象编程(OOP)。每个 Pythoneer 爱好者经常使用这些编程风格的组合，并且通常有自己喜欢的编码风格。作为一名 Python 程序员，你可以用自己喜欢的风格编写代码。

考虑到 OOP 包含的概念数量及其受欢迎程度，它需要的不仅仅是一篇文章。然而，在这里我将把讨论限制在一些最广泛使用的面向对象编程概念上。

我将介绍以下主题及其在 Python 中的实现:

*   [过程编程和函数编程的区别](#difference-between-procedural-programming-and-functional-programming)
*   什么是 OOP，为什么需要它？
*   什么是类及其对象？
*   [有哪些属性和方法？](#what-are-the-attributes-and-methods)
*   [什么是 init 方法？](#what-is-init-method)
*   什么是自我关键字，我们为什么要使用它？

**注意:**本文假设您对 Python 编程有所了解。如果你想重温 Python 的知识，我强烈建议你浏览一下 [Python 手册](https://www.quantinsti.com/python-basics-handbook)的最初几章。在我们开始讨论 OOP 之前，让我们先弄清楚过程式编程和函数式编程的区别。

* * *

## **过程编程和函数编程的区别**

过程化编程是我们在开始编程时学习的。最简单的形式是，过程化编程采用自顶向下的方法执行代码。代码将按照编写的顺序逐行执行。对了，这就是你的程序设计。

如果你通过例子来学习，这里是: