---
title: "Portability Issues"
date: 2022-05-01T16:41:35+08:00
tag: #Reading Notes
---
When reading C standard documents, we usually see phrases like "**Implementation-defined**", "**Unspecified**",.etc.

So, what do they really mean? 
## 术语
我们将这些难以直接理解的词汇称为**术语**，在ANSI C中，术语可以分为描述不可移植代码(unportable), 坏代码(bad), 可移植的代码(portable)三类. 
### unportable code
**Implementation-defined** 

需要由编译器设计者决定采取何种行为，他们可能不同，但都不能说是错误的.  
例如：当整型数右移时，是否需要扩展符号位. [右移代替除法可能导致的灾难](https://www.cnblogs.com/bluettt/p/16186598.html).

**unspecified**

在某些正确情况下的做法，标准并未明确规定应该怎样做.  
例如：参数求值的顺序.

### bad code
**undefined**

在某些不正确情况下的做法，但标准并未规定应该怎样做。意味着你可以采取任何行动，可以什么都不做，也可以发出一条警告信息, 或者终止CPU重启等等. 你甚至可以发射核导弹(只要你安装了能发射核导弹的硬件系统).  
例如：当一个有符号整数溢出时该采取什么行动.

**constraint**

这是一个必须遵守的限制或要求. 如果你不遵守, 那么你的程序的行为就会变成如上所说的`undefined`. 这出现了一种很有意思的情况: 分辨某种东西是否是一个`constaint`是很容易的, 因为每个标准的主题都附有一个`constraint`小节, 列出了所有的约束条件。  
例如: `%`操作符的操作数必须为整型. 所以,在非整型数据上使用`%`操作符肯定会导致`undefined`.

### portable code
**strictly conforming**

严格遵守标准的. 符合该条件的程序应当是:
* 只使用已确定的特性
* 不突破任何由编译器实现(Implementation-defined)的限制.
* 不使用`unspecified`和`undefined`特性

这样规定的目的是最大程序保证代码的可移植性. 但符合该术语的代码并不常见, 例如`INT_MAX`的值在不同架构的机器上结果可能不同.

**comforming**

遵循标准的; 一个遵循标准的程序可以依赖一些对于某种编译器特有的**不可移植**的特性. 这样一个程序对于某个编译器可能是遵循标准的, 但对于另外一个编译器又是不遵循标准的. 
