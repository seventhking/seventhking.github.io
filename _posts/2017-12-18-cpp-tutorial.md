---
layout: post
title: "C++"
subtitle: "C++"
date: 2017-12-18 09:50:00
author: "Deetch"
header-img: "img/home-bg-o.jpg"
catalog: true
tags:
    - C++
---

> "Let's go"

## 预处理器调试有用的常量
NDEBUG
__FILE__ 文件名
__LINE__ 当前行号
__TIME__ 文件被编译的时间
__DATE__ 文件被编译的日期


assert(expr)  //只要NDEBUG未定义，assert宏就执行


## 操作符重载
对称的操作符，如算术操作符、相等操作符、关系操作符和位操作符，最好定义为普通非成员函数


## 模板编译模型
标准C++为编译模板代码定义了两种模型。在两种模型中，构造程序的方式很大程度上是相同的：  
类定义和函数声明放在头文件中，而函数定义和成员定义放在源文件中。两种模型的不同在于，编译器  
怎么样使用来自源文件的定义。所有编译器都支持第一种模型，称为“包含”模型，只有一些编译器支持  
第二种模型，“分别编译”模型

### 包含编译
编译器必须看到用到的所有模板的定义，一般而言，可以通过在声明函数模板或类模板的头文件中添加  
一条#include指示使定义可用。如果两个或多个单独编译的源文件使用同一个模板，这些编译器将为  
每个文件中的模板产生一个实例。

~~~
//utilities.h
#ifndef A
#define A
template <typename T> int compare();

#include "utilities.cpp"
#endif

//utilities.cpp
template <typename T> int compare()
{}
~~~

### 分别编译模型
编译器会为我们跟踪相关的模板定义。但是，我们必须让编译器知道要记住给定的模板定义，可以使用export关键字  
来做这件事  
export关键字能够指明给定的定义可能会需要在其他文件中产生实例化。
函数：  
~~~
export template <typename Type>
Type sum()
{}
~~~
这个函数模板的声明像通常一样应放在头文件中，声明不必指定export

类模板使用export更复杂一些。通常，类声明必须放在头文件中，头文件中的类定义体不应该使用关键字export，  
如果在头文件中使用export，则该头文件只能被程序中的一个源文件使用。  
相反，应该在类的实现文件中使用export  
~~~
//.h
template <typename Type> class Queue { ... };

//.cpp
export template <typename type> class Queue;
#include "Queue.h"
~~~

到处成员函数的定义不必在使用成员时可见。任意非导出成员的定义必须像在包含模型中一样对待：  
定义应放在定义类模板的头文件中。


### 函数模板的特化

### 类模板的特化

### 特化成员而不特化类

### 类模板的部分特化


## C标准库

### 当以读和写类型打开一个文件时，具有以下限制
1. 如果中间没有fflush、fseek、fsetpos或rewind，则在输出的后面不能直接跟随输入  
2. 如果中间没有fseek、fsetpos或rewind，或者一个输入操作没有到达文件尾端，则在输入操作之后不能直接跟随输出  

