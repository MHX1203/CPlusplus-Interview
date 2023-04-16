# CPlusplus-Interview
- [CPlusplus-Interview](#cplusplus-interview)
  - [C++基础](#c基础)
    - [1.  说一下C和C++的区别](#1--说一下c和c的区别)
    - [2.  include头文件的顺序以及双引号""和尖括号的区别？](#2--include头文件的顺序以及双引号和尖括号的区别)
    - [3.  什么时候会发生段错误？](#3--什么时候会发生段错误)
    - [4.  头文件中的`ifndef/define/endif` 是干什么用的? 该用法和`program once` 的区别？](#4--头文件中的ifndefdefineendif-是干什么用的-该用法和program-once-的区别)
    - [5.  说一下C++代码文件到可执行文件，经历了哪些过程？](#5--说一下c代码文件到可执行文件经历了哪些过程)
    - [6.  C++11 有哪些新特性](#6--c11-有哪些新特性)
    - [7.  C++堆和栈的区别](#7--c堆和栈的区别)
    - [8.  计算机内部如何存储负数和浮点数？](#8--计算机内部如何存储负数和浮点数)
    - [9.  C语言struct和C++中的`struct`有什么区别?](#9--c语言struct和c中的struct有什么区别)
    - [10. `extern`有什么作用，`extern C`有什么作用?](#10-extern有什么作用extern-c有什么作用)
    - [11. C中`int fun()` 和 `int fun(void)`的区别?](#11-c中int-fun-和-int-funvoid的区别)
    - [12. `const int*p` 和 `int const *p`的区别](#12-const-intp-和-int-const-p的区别)
    - [13. 引用和指针的区别](#13-引用和指针的区别)
    - [14. 如何避免“野指针”](#14-如何避免野指针)
    - [15. 说一下数组名和指针的区别](#15-说一下数组名和指针的区别)
    - [16. 简述`strcpy`、`sprintf`与`memcpy`的区别](#16-简述strcpysprintf与memcpy的区别)
    - [17. 解释一下`mutable`关键字](#17-解释一下mutable关键字)
    - [18. 参数传递](#18-参数传递)
    - [19. `new` 和`malloc`的区别](#19-new-和malloc的区别)
    - [20. `delete` 和`free`的区别](#20-delete-和free的区别)
    - [21. `new`和`delete`操作符的实现原理](#21-new和delete操作符的实现原理)
    - [22. `free`和`malloc`的实现原理](#22-free和malloc的实现原理)
    - [23. `free`是如何知道释放内存的大小的](#23-free是如何知道释放内存的大小的)
    - [24. `malloc`申请的存储空间能用`delete`释放吗？](#24-malloc申请的存储空间能用delete释放吗)
    - [25. `malloc`，`calloc`以及`realloc`之间的区别？](#25-malloccalloc以及realloc之间的区别)
    - [26. 说一下c/c++的内存分配](#26-说一下cc的内存分配)
    - [27. 为什么`static`成员变量不能在类内做初始化，加了`const`为什么就可以了？](#27-为什么static成员变量不能在类内做初始化加了const为什么就可以了)
    - [28. static变量和全局变量的区别](#28-static变量和全局变量的区别)
    - [29. static 变量的特点](#29-static-变量的特点)
    - [30. static函数的特点](#30-static函数的特点)
    - [31. `const`和宏定义的区别？](#31-const和宏定义的区别)
    - [32. `typedef`和`define`有什么区别？](#32-typedef和define有什么区别)
    - [33. using在c++中有哪些用法](#33-using在c中有哪些用法)
    - [34. `typedef`和`using`的区别？](#34-typedef和using的区别)
    - [35. 说一下在函数中不同位置使用const的情况，并解释不同位置下，const的作用？](#35-说一下在函数中不同位置使用const的情况并解释不同位置下const的作用)
    - [36. 什么内联函数，说一下`inline`的优缺点，它和宏定义有什么区别？](#36-什么内联函数说一下inline的优缺点它和宏定义有什么区别)
    - [37. `struct`和`class`的区别](#37-struct和class的区别)
    - [38. `explicit` 的作用，为什么要用它](#38-explicit-的作用为什么要用它)
    - [39. 说一下友元的应用场景，它会有什么问题](#39-说一下友元的应用场景它会有什么问题)
    - [40. 解释一下C++中的类型转换](#40-解释一下c中的类型转换)
    - [41. 介绍一下RAII](#41-介绍一下raii)
    - [42. const常量在C和C++中有什么区别](#42-const常量在c和c中有什么区别)
    - [43. 说一下C++模板的偏特化与全特化它们的应用场景](#43-说一下c模板的偏特化与全特化它们的应用场景)
    - [44. 解释一下C++中的内存对齐？](#44-解释一下c中的内存对齐)
    - [45. 解释一下`volatile`关键字](#45-解释一下volatile关键字)
    - [46. 浅拷贝和深拷贝有什么区别？](#46-浅拷贝和深拷贝有什么区别)
    - [47. `sizeof`和`strlen`有什么区别？](#47-sizeof和strlen有什么区别)
    - [48. 说一下类的初始化列表，为什么说它可以提高效率?](#48-说一下类的初始化列表为什么说它可以提高效率)
    - [49. 内存泄漏的场景一般有哪些情况](#49-内存泄漏的场景一般有哪些情况)
    - [50. 解释一下`constexpr`关键字？](#50-解释一下constexpr关键字)
    - [51. `const`和`constexpr`有什么区别？](#51-const和constexpr有什么区别)
    - [52. `enum`和`enum class`的区别？](#52-enum和enum-class的区别)
  - [C++面向对象](#c面向对象)
    - [1.  构造函数能否为虚函数](#1--构造函数能否为虚函数)
    - [2.  构造函数调用虚函数会发生什么](#2--构造函数调用虚函数会发生什么)
    - [3.  为什么内联函数，构造函数，静态成员函数不能为virtual函数？](#3--为什么内联函数构造函数静态成员函数不能为virtual函数)
    - [4.  C++虚函数表和虚函数指针机制](#4--c虚函数表和虚函数指针机制)
    - [5.  构造函数和析构函数能否重载？](#5--构造函数和析构函数能否重载)
    - [6.  override的作用](#6--override的作用)
    - [7. `->*`,`::*`以及`.*`分别是什么意思](#7--以及分别是什么意思)
    - [8. 复合对象，继承对象以及复合继承对象，构造函数和析构函数的调用顺序？](#8-复合对象继承对象以及复合继承对象构造函数和析构函数的调用顺序)
    - [9.  C++中类的访问权限](#9--c中类的访问权限)
    - [9. 类继承有哪些方式](#9-类继承有哪些方式)
    - [10. 解释一下this指针](#10-解释一下this指针)
    - [11. 解释一下this指针](#11-解释一下this指针)
    - [12. override和overload的区别](#12-override和overload的区别)
    - [13. 面向对象的3大特性](#13-面向对象的3大特性)
    - [14. 虚函数和纯虚函数](#14-虚函数和纯虚函数)
    - [15. 为什么拷贝构造函数的参数类型必须是引用](#15-为什么拷贝构造函数的参数类型必须是引用)
    - [16. C++实现多态有哪些方式](#16-c实现多态有哪些方式)
    - [17. 解释一下虚函数和虚表](#17-解释一下虚函数和虚表)
    - [18. 虚函数和虚表示如何实现多态的](#18-虚函数和虚表示如何实现多态的)
    - [19. 解释一下虚函数和虚表](#19-解释一下虚函数和虚表)
    - [20. 解释一下多继承下类的内存布局？](#20-解释一下多继承下类的内存布局)
    - [21. 基类析构函数为什么要定义为虚函数？](#21-基类析构函数为什么要定义为虚函数)
    - [22. C++如何计算一个类的大小，空类的大小是多少？](#22-c如何计算一个类的大小空类的大小是多少)
    - [23. 简述类成员函数的重写、重载和隐藏的区别](#23-简述类成员函数的重写重载和隐藏的区别)
    - [24. 用C++设计一个不能被继承的类](#24-用c设计一个不能被继承的类)
    - [25. 如何定义一个只能在堆上（栈上）生成对象的类？](#25-如何定义一个只能在堆上栈上生成对象的类)
    - [26. 一个类默认有哪几个构造函数](#26-一个类默认有哪几个构造函数)
    - [27. 如何让一个类无法实例化](#27-如何让一个类无法实例化)
    - [28. 什么场景下使用继承方式，什么场景下使用组合？](#28-什么场景下使用继承方式什么场景下使用组合)
    - [29. delete this 合法吗？](#29-delete-this-合法吗)
    - [30. 哪些情况下会显示调用this指针](#30-哪些情况下会显示调用this指针)
  - [STL](#stl)
    - [1.  介绍下STL](#1--介绍下stl)
    - [2.  解释下各种容器的特点和适用情况](#2--解释下各种容器的特点和适用情况)
    - [3.  vector的实现原理](#3--vector的实现原理)
    - [4.  vector中的reserve和resize的区别](#4--vector中的reserve和resize的区别)
    - [5.  vector中的size和capacity的区别](#5--vector中的size和capacity的区别)
    - [6.  vector的元素类型可以是引用吗？](#6--vector的元素类型可以是引用吗)
    - [7.  vector迭代器失效的情况？](#7--vector迭代器失效的情况)
    - [8.  vector 扩容为什么要以1. 5倍 或者2倍 扩容?](#8--vector-扩容为什么要以1-5倍-或者2倍-扩容)
    - [9.  vector的常用函数](#9--vector的常用函数)
    - [10. list的实现原理](#10-list的实现原理)
    - [11. list的常用函数](#11-list的常用函数)
    - [12. deque的底层原理](#12-deque的底层原理)
    - [13. 什么情况下用vector，什么情况下用list，什么情况下用deque](#13-什么情况下用vector什么情况下用list什么情况下用deque)
    - [14. deque的常用函数](#14-deque的常用函数)
    - [15. priority\_queue的底层原理](#15-priority_queue的底层原理)
    - [16. priority\_queue的常用函数](#16-priority_queue的常用函数)
    - [17. map 、set、multiset、multimap的底层原理](#17-map-setmultisetmultimap的底层原理)
    - [18. map 、set、multiset、multimap的特点](#18-map-setmultisetmultimap的特点)
    - [19. 为何map和set的插入删除效率比其他序列容器高，而且每次insert之后，以前保存的iterator不会失效？](#19-为何map和set的插入删除效率比其他序列容器高而且每次insert之后以前保存的iterator不会失效)
    - [20. 为何map和set不能像vector一样有个reserve函数来预分配数据?](#20-为何map和set不能像vector一样有个reserve函数来预分配数据)
    - [21. map 、set、multiset、multimap的常用函数](#21-map-setmultisetmultimap的常用函数)
    - [22. unordered\_map、unordered\_set的底层原理](#22-unordered_mapunordered_set的底层原理)
  - [Effictive C++](#effictive-c)
    - [1.  解释一下左值引用和右值引用](#1--解释一下左值引用和右值引用)
    - [2.  右值的应用场景](#2--右值的应用场景)
    - [3.  介绍一下智能指针](#3--介绍一下智能指针)
    - [4.  解释一下shared\_ptr的内部实现](#4--解释一下shared_ptr的内部实现)
    - [5.  说一下assert](#5--说一下assert)
    - [6.  动态链接库和静态链接库的区别是什么？](#6--动态链接库和静态链接库的区别是什么)
    - [7.  平时会用到function、bind、lambda吗，都什么场景下会用到？](#7--平时会用到functionbindlambda吗都什么场景下会用到)
    - [8.  了解auto和decltype吗？](#8--了解auto和decltype吗)
    - [9.  了解移动语义和完美转发吗？](#9--了解移动语义和完美转发吗)
    - [10 . unique\_ptr如何转换所有权](#10--unique_ptr如何转换所有权)
  - [C++并发编程](#c并发编程)
    - [1.  什么是并发编程？](#1--什么是并发编程)
    - [2.  线程与进程的区别？](#2--线程与进程的区别)
    - [3.  多线程有几种实现方法，都是什么？](#3--多线程有几种实现方法都是什么)
    - [4.  C++ 中的同步和异步操作有什么区别？](#4--c-中的同步和异步操作有什么区别)
    - [5.  使用 C++ 实现锁的方法有哪些？](#5--使用-c-实现锁的方法有哪些)
    - [6.  使用多线程编程时如何避免数据竞争？](#6--使用多线程编程时如何避免数据竞争)
    - [7.  C++ 11  中的 std::thread 如何使用？](#7--c-11--中的-stdthread-如何使用)
    - [8.  线程间通信的方法有哪些？](#8--线程间通信的方法有哪些)
    - [9.  如何使用 C++ 实现高效的线程池？](#9--如何使用-c-实现高效的线程池)
    - [10. C++ 中的协程是什么？](#10-c-中的协程是什么)
    - [11. 请说明 C++ 中的线程安全性。](#11-请说明-c-中的线程安全性)
    - [12. 什么是原子操作？在 C++ 中如何使用？](#12-什么是原子操作在-c-中如何使用)
    - [13. 如何实现线程数据的同步，有哪些方式？](#13-如何实现线程数据的同步有哪些方式)
  - [设计模型](#设计模型)
    - [1.  单例模式](#1--单例模式)
    - [2.  工厂模式](#2--工厂模式)
    - [3.  适配器模式](#3--适配器模式)
  - [Reference](#reference)


## C++基础

### 1.  说一下C和C++的区别
- **编程范式**：C是一种面向过程的编程语言，它侧重于程序的结构和流程控制，而C++可以理解为C的超集，它具有多种不同的编程范式，包括面向过程，面向对象，泛型编程等。

- **执行效率**：C语言以执行效率为重点，因此它支持指针、位运算等底层操作，并且不提供内置的面向对象的特性，C++增加了许多高级特性，如类、继承、多态等，在一定程度上降低了执行效率。

- **内存管理**：C语言不提供内存管理机制，开发者需要手动分配和释放内存，容易出现内存泄漏和悬空指针等问题。而C++提供了RAII（Resource Acquisition Is Initialization）机制和智能指针等高级的内存管理方式，能够更加安全和高效地管理内存。

- **标准库**：C标准库提供了一系列底层的函数和宏，用于处理字符、字符串、文件、输入输出等。C++标准库则不仅包括C标准库，还增加了STL（Standard Template Library）等高级特性，提供了大量的容器、算法和迭代器等，能够更加方便地处理数据结构和算法问题。

### 2.  include头文件的顺序以及双引号""和尖括号的区别？
主要的区别在于，头文件的搜索顺序不同（编译时也可使用-I显式指定搜索路径），其次两种不同的include方式，也可以区分库的类型
- 尖括号(<>) 用来来包含系统库和第三方库的头文件，只会在系统路径下查找，文件的搜索顺序为
  ○ 编译器设置的头文件查找路径，编译器有默认的头文件查找路径
  ○ 系统变量`CPLUS_INCLUDE_PATH`/`C_INCLUDE_PATH`指定的头文件路径
- 双引号用来包含自定义的头文件，文件的搜索顺序为
  ○ 先在当前源文件所在的工作目录中进行查找
  ○ 编译器设置的头文件查找路径，编译器有默认的头文件查找路径
  ○ 系统变量`CPLUS_INCLUDE_PATH`/`C_INCLUDE_PATH`指定的头文件路径

### 3.  什么时候会发生段错误？



段错误通常是由于对内存的错误操作导致的，以下是导致段错误的可能原因。

- 空指针，使用一个未初始化的指针。
- 野指针，访问一个未知的地址，或者访问一个已释放的指针。
- 数组越界。
- 栈空间溢出，比如函数递归过深。
- 程序试图修改只读内存，也有可能发生段错误



### 4.  头文件中的`ifndef/define/endif` 是干什么用的? 该用法和`program once` 的区别？
  - `ifndef`/`define`/`endif` 通常是在头文件中做防卫式声明的，用来避免重复`include`，如果一个头文件具有多份拷贝，也能避免重复`include`的问题，编译器支持的更好，通用性更强。


```c++
#ifndef __HEADER__
#define __HEADER__

/*

header content
*/

#endif
```

- `program once`和`ifndef/define/endif` 的作用相同，更简洁，如果一个头文件具有多份拷贝，无法避免重复include的问题，此外，这种方式编译器会检查文件的所有内容，会降低编译效率，最后并不是所有的编译器都支持这种方式，因此不推荐使用。

```c++
#program once

/*

header content
*/

```


### 5.  说一下C++代码文件到可执行文件，经历了哪些过程？
- **预处理（Preprocessing）**：在编译前，对代码中的预处理指令进行处理，例如宏定义、条件编译等。这一步会将宏定义做字符串替换，以及include指令替换为实际的头文件内容，处理后的代码会保存在一个临时文件中，通常以.i或者.ii作为文件扩展名。
> // 比如现在有一个hello.c的代码文件
> gcc -E hello.c -o hello.i
- **编译（Compiling）**：将预处理后的代码编译成汇编代码，这个过程包括词法分析、语法分析、语义分析和生成中间代码等步骤，通常以.s作为文件扩展名。
> gcc -S hello.i -o hello.s
- **汇编（Assembling）**：将汇编代码转换成机器语言指令，生成目标文件（Object File），通常以.o或.obj作为文件扩展名。
> gcc -c hello.s -o hello.o
- **链接（Linking）**：将目标文件和系统库文件链接起来，生成可执行文件，通常以.exe或.out作为文件扩展名。在链接过程中，链接器将解析目标文件中的符号（函数、变量等），并将其与系统库文件中的符号进行匹配，生成最终的可执行文件。
> gcc hello.o -o hello
>

在上述过程中，编译器和链接器是最重要的工具。编译器将C++代码转换成汇编代码，而链接器则将目标文件和库文件链接成可执行文件。
> // 也可以一步到位，直接用一个指令得到可执行
>
> gcc -c hello.c -o hello

### 6.  C++11 有哪些新特性
- 智能指针
- 移动语义
- 自动类型推导
- lambda 表达式
- 初始化列表
- Ranged based for  loop
- nullptr 关键字
- 并发编程库
- constexpr 关键字
  

### 7.  C++堆和栈的区别
- 内存分配方式不同，栈上内存的分配和释放由编译器决定，而堆上的内存的分配和释放由用户自己决定。
- 内存管理方式不同，栈上的内存遵循后进先出的原则，而堆上的内存则是随意存放的方式。
-  可分配的内存大小不同，栈上分配的内存大小是由系统决定的，每个线程的栈大小是受限的，而堆上分配的内存，则只受限于物理内存的大小。  
- 变量的生命周期不同，栈上的变量的生命周期是由系统自动管理的，临时变量会在离开函数时自动被系统回收，堆中变量的生命周期需要手动管理，手动回收。

### 8.  计算机内部如何存储负数和浮点数？
负数的存储
计算机内部通常使用二进制补码来表示负数。补码是一种数值编码方式，它使用一个二进制数的最高位来表示符号0表示正数，1表 示负数。计算机对负数采用二进制补码进行存储和运算，具体的实现方式是：对于一个负数，先取其绝对值的二进制表示，然后对其进行取反操作，再加上 1。 

例如，对于 -3这 个数，其绝对值为 3， 对应的二进制数是 0011 ，取反后变成 1100 ，再加上1， 得到 1101 ，这就是-3的 二进制补码表示。

浮点数的存储
- 十进制浮点数转为二进制浮点数
- 二进制浮点数移位，转为指数形式
- 按顺序存储符号位，指数部分，小数部分

比如3. 25 
- 首先将 3. 25 转化为二进制的小数形式（小数位，可以使用乘2法 ，对小数位乘2， 不满1的取0， 满1的取1， 直至没有小数位为止），得到1101 
- 将整数位化 1,  即$$1101  =  1. 101  *  2  ^ 1$$
- 按顺序存储符号位（这里是正数，符号位为 1） ，指数部分（这里为 1） ，小数部分（这里为101） 

下面是float浮点数的存储方式，一共有 23 位可供小数位存储

![img](https://cdn.nlark.com/yuque/0/2023/gif/2625673/1680331635283-19d177c7-29bf-4e1c-a9c2-4ec1aba3afec.gif)

下面是double浮点数的存储方式，一共有 52 位可供小数位存储

![img](https://cdn.nlark.com/yuque/0/2023/gif/2625673/1680331667134-54bb1d28-c10e-4f9a-b318-2db455a98895.gif)


### 9.  C语言struct和C++中的`struct`有什么区别?
- C语言中，`struct`只是不同数据的集合，不能包含函数，以及所有面向对象的概念。
- 在C++中，`struct`基本上和class类似，只是内部成员默认为`public`，`class`中内部成员默认为`private`，其他行为相同。


### 10. `extern`有什么作用，`extern C`有什么作用?
`extern`： 正常情况下，一个文件中，无法正常使用其他文件中定义的变量和函数，而通过使用extern声明，就能够调用在其他文件中定义的变量或者函数。

`extern C`： 某些情况下，你希望某些变量、函数或者代码段以C语言的形式编译和调用，这时可以将代码放在extern C scope中，比如

```c++
#ifdef __cplusplus
extern "C" {
#endif

void my_print()
{
///
}


#ifdef __cplusplus
}
#endif
```
在一个项目中，很可能既包含C代码，也包含C++代码，这时，在C++代码中调用C代码，如果不加extern C，在链接的过程中，很可能会导致无法链接的错误，因为C和C++的编译过程，对于函数的处理是不同的。由于C++支持函数重载，因此编译器编译函数的过程中会将函数的参数类型也加到编译后的代码中，而不仅仅是函数名；而C语言并不支持函数重载，因此编译C语言代码的函数时不会带上函数的参数类型，一般只包括函数名。

### 11. C中`int fun()` 和 `int fun(void)`的区别?
`int func()`可以接收任意类型和任意数量的参数，而`int fun(void)` 则不接收任何参数。

### 12. `const int*p` 和 `int const *p`的区别
- `const int *p` 表示指针指向的值不可被修改

  ```c++
  
  
  int main()
  {
  
    int a =  0; 
  
    // p指向的值不可被修改，只有指针的指向可以被修改
    const int *p = &a;
  
    // Error
    *p =  2; 
  }
  
  ```

  

- `int const *p` 表示指针的指向不可被修改

  ```c++
  
  
  int main()
  {
    	int a = 0; 
  	// p指向的地址不可被修改，只有指针指向的值可以被修改
    	int const *p = &a;
  	int b = 2; 
  
    	// Error
    	p = &b;
  }
  ```

  

### 13. 引用和指针的区别
- 引用一旦创建，无法被修改，而指针可以进行多次赋值

```c++
int a = 0; 

// ref_a 一旦指向a，无法被修改，无法再作为其他变量的别名
int &ref_a = a;

// Error
int b = 2; 
&ref_a = b;
  b. 引用只是变量的别名，它不占用额外空间，指针在32 位系统占用4个 字节，64 位系统占用8个 字节。
int a = 0; 

int &ref_a = a;

// ref_a 和a 具有相同的内存地址
cout << "Addr of a: " << &a << ", Addr of ref_a: " << &ref_a << endl;
```





- 访问操作符不同，引用通过 . 访问对象的成员，而指针通过 -> 访问对象成员

  ```c++
  Obj obj;
  
  Obj &ref_obj = obj;
  
  Obj *p_obj = &obj;
  
  ref_obj.get_name();
  
  p_obj -> get_name();
  ```

- 指针可以指向任意地址，可以指向NULL，而引用必须指向一个已有的变量。
- 指针可以做位移运算，引用不存在位移运算。

### 14. 如何避免“野指针”
野指针指的时指向无效或者未知地址的指针，直接访问可能导致意外的不可预知的结果。
- 创建指针时，尽量做初始化，如果不确定指向什么位置，将其初始化成nullptr。
- 在访问指针指向的资源之前，判断指针是否为nullptr。
- 释放指针资源之后，将指针置为nullptr。
- 使用智能指针，它可以自动的帮助我们管理内存。
- 尽量使用引用来代替指针。

### 15. 说一下数组名和指针的区别

数组名和指针，在很多地方具有相似之处，比如可以使用解引用符号，但它们本质上时不同的，主要区别如下
- 数组名本质上并不是一个指针，但是它具有和指针类似的行为，可以理解为一个指向不可变的指针类型（type *const p），无法进行赋值操作。
- 数组名占用的内存大小是整个数组的大小，而指针的大小则是4个 字节或者8个 字节。
- 数组名在初始化时，就会分配数组大小的空间，而指针初始化时，只会创建指针大小的空间。

### 16. 简述`strcpy`、`sprintf`与`memcpy`的区别
- strcpy 用于字符串复制，将一个字符串复制到另一个字符串，当遇到\0结 束复制。
  ```c++
  - char str1[ ] = "Hello\0  Geeks! ";
    char str2[ ] = "GeeksforGeeks";
  
  strcpy(str2,  str1) ;
  
  // 输出：Hello
  cout << str2  ;
  ```

  


strcpy在进行字符串复制时，并不会考虑目标字符串长度不够所导致的溢出问题，因此它是不安全的，在进行复制之前，应该确保目标字符串具有足够的大小，比如下面演示了字符串溢出的例子

下面的例子中，首先定义了2个 字符串和1个 int类型的变量a，str1  的大小为10 0， str2的 大小为10 。3个 变量都在栈上，由于栈上的地址是从高地址向低地址增长，3个 变量的地址顺序是 str2  -> a -> str1,  将str1的 内容复制到str2， 会导致缓冲区溢出的情况，即在复制完成之后，超出的字符串部分，会覆盖掉其他变量，也就是会将a以及str1的 一部分覆盖，所以产生了未知的结果。

在实际使用中，更推荐使用strncpy来进行字符串的复制。
```c++
char str1[ 10 0]  = "Hello Cplusplus!";
int a = 10 ;
char str2[ 10 ] = "01 23 45 67 8" ;
cout << "str1:  " <<str1  << endl;
cout << "str2:  " <<str2  << endl;

strcpy(str2,  str1) ;
cout << "------------------------------------------\n";
cout << "str1:  " << str1  << endl;
cout << "str2:  " <<str2  << endl;


```



```
/*
输出：

str1:  Hello Cplusplus!
str2:   01  23  45 67 8
------------------------------------------
str1:  s!
str2:  Hello Cplusplus!

*/
```



- `sprintf`是一个字符串格式化输出函数，用于将多个变量格式化为一个字符串，和`strcpy`类似，同样是当遇到`\0`结束，它和`strcpy`一样，同样需要注意缓冲区溢出的问题。因此推荐使用`snprintf`，而不是`sprintf`
  
  ```c++
  char str1[ ] = "Hello\0  Geeks!";
  char str2[ ] = "GeeksforGeeks";
  char str[10 0] ;
  sprintf(str, "x=%s, y=%s", str1,  str2) ;
  // 输出：x=Hello, y=GeeksforGeeks 
  cout << str;
  ```
  
- `memcpy`
  `memcpy`可以用于任意类型数据的复制，使用`memcpy`需要指定复制的字节数，当复制字符串时，它不会在字符串结尾添加\0， 需要手动添加

  ```c++
  char str1[ 10 0]  = "Hello Cplusplus!";
  char str2[ 10 ];
  
  memcpy(str2,  str1,  9) ;
  
  // 手动添加 \0
  str2[ 9]  = '\0' ;
  
  cout << str2  << endl;;
  ```

  

### 17. 解释一下`mutable`关键字
`mutable`允许在常量函数中修改变量。

```c++
class Entity
{
    private:
        int m_age;

    	// mutable 关键字，可以让该变量在const域的成员函数中被修改
        mutable int m_call_time;
    
    public:
    	Entity(){}
    
    	// m_call_time 可以被修改
        const int get_age() const
    	{
            m_call_time++;
            return m_age;
        }

};
int main()
{
    const Entity en;
    en.get_age();
    return 0; 
}
```





### 18. 参数传递
- 值传递
需要在栈上分配内存，并对实参做拷贝，效率低，尤其是是一些复杂对象的时候。	
值传递，在函数中对于函数形参的任意修改，都不会影响到实参。

```c++
int func(int num1,  int num2) 
{
	return num1  + num2; 
}

int main()
{
	int a = 12 , b=5; 
	int c = func(a, b);
	cout << c <<  endl;
    return 0; 
}
```



- 引用传递
引用传递，不会做任何的拷贝动作，对于形参的任意修改，都会同时影响到实参，需要注意。因此在大多数时候，会在参数之前加上const，避免参数在函数内被修改。
除了函数内部创建的临时值，需要返回值类型以外，其他时候，函数的参数和返回值，最好都采用引用的方式。

```c++
int func(const int& num1,  const int& num2) 
{
	int ret = num1  + num2; 
    return ret;
}

int main()
{
	int a = 12 , b=5; 
	int c = func(a, b);
	cout << c <<  endl;
    return 0; 
}
```



### 19. `new` 和`malloc`的区别
- new是操作符，而malloc是函数
- new 返回的是一个对象指针，而malloc返回的是一个void类型的指针
- new 不需要指定大小，而malloc必须指定分配的内存大小
- new一个对象失败会抛出异常，而malloc失败会返回null_ptr
- new的内部实现调用了malloc函数。
- new 操作符无法被重载，而malloc函数可以被重载

### 20. `delete` 和`free`的区别
- delete是操作符，而free是函数。
- delete的内部实现调用了free函数。
- delete 操作符无法被重载，而free函数可以被重载

### 21. `new`和`delete`操作符的实现原理

`new`操作符

- 使用`operator new`函数，在内存中（heap上）创建一个足够大的空间。
- 将创建的空间地址赋给this指针。
- 调用类的构造函数，进行成员变量的初始化，如果对象是一个数组，那么new运算符会为数组中的每个元素调用构造函数。

`delete` 操作符

- 调用类的析构函数。
- 调用`operator delete`函数，释放内存空间。

### 22. `free`和`malloc`的实现原理
`malloc`的实现原理：

- `malloc`函数会在堆区中申请一段连续的内存空间，返回该空间的首地址。
- `malloc`函数的原型为：`void* malloc(size_t size)`。
- `malloc`函数需要指定所需内存大小，如果内存分配成功，就会返回所分配的内存的起始地址。如果内存分配失败，返回null_ptr。
free的实现原理：
- `free`函数用于释放由`malloc`分配的内存空间，使得该空间可以被重新利用。
- `free`函数的原型为：`void free(void* ptr)`。
- `free`函数需要用户传入一个指向先前由`malloc`返回的指针，以告诉系统要释放的内存地址。如果该指针是null_ptr，则不会执行任何操作。

### 23. `free`是如何知道释放内存的大小的
`free`用于释放由`malloc`分配的内存，其实在`malloc`分配内存的时候，除了分配指定大小的内存外，还会内存块的头部分配一小块内存（header）用于保存内存块信息（包括分配内存的大小，内存块的边界，是否被占用等信息），`free`可以根据header中内存块信息，来决定释放多大的内存。因此，实际释放的内存是指针实际占用的空间加上Header块的空间。

### 24. `malloc`申请的存储空间能用`delete`释放吗？

不可以，可能会出现未定义的行为，`malloc`需要和`free`配套使用。

当使用`malloc`为一个复杂类型的对象分配内存时，由于`malloc`并不会调用类的构造函数，也就是对象的成员变量不会进行初始化等操作。
而`delete`操作符，首先会调用对象的析构函数，回收类成员变量，由于此时成员变量未被初始化，因此很可能导致不可预知的结果。
所以，`malloc`分配的内存，应该使用`free`来回收。同理，`new`创建的对象，也不能通过`free`来释放。

### 25. `malloc`，`calloc`以及`realloc`之间的区别？
- 分配的内存大小不同：
  ○ malloc：只分配指定字节数的内存空间；
  ○ calloc：会分配指定数量的连续内存空间，并且每个字节都初始化为0； 
  ○ realloc：改变已分配内存的大小，或重新分配新的内存空间。
- 函数声明的参数不同：
  ○ malloc：只有一个参数，即需要分配的字节数；
  ○ calloc：有两个参数，第一个参数是需要分配的元素个数，第二个参数是每个元素的大小；
  ○ realloc：有两个参数，第一个参数是之前已经分配过的内存地址，第二个参数是需要重新分配的字节数。
  ○ 
- 内存分配成功后的初始化情况不同：
  ○ malloc 和 realloc 分配的内存空间中的内容是未初始化的，里面可能包含任意值；
  ○ calloc 分配的内存空间中的内容全部初始化为0。 
- 返回值不同：
  ○ malloc 和 calloc 的返回值是一个指向已分配内存起始地址的指针；
  ○ realloc 的返回值是一个指向已重新分配内存起始地址的指针。
  需要注意的是，使用 malloc、calloc 和 realloc 分配的内存空间，都必须使用 free 函数释放，否则会导致内存泄漏。

### 26. 说一下c/c++的内存分配
c++中内存的分区包括5个 部分
- 栈：由编译器自动分配和释放，存储局部变量和函数调用信息等，空间有限。
- 堆：由程序员手动分配和释放，存储动态分配的内存，空间只受限于物理内存。
- 静态存储区：用于存储全局变量、静态变量等，程序运行期间一直存在，由系统自动分配和释放。
- 常量存储区：用于存储常量，程序运行期间一直存在，不允许修改。
- 程序代码区：用于存储程序的指令代码，程序运行期间一直存在，不允许修改。


### 27. 为什么`static`成员变量不能在类内做初始化，加了`const`为什么就可以了？
static成员变量，在类的对象没有被构建之前就已经存在，且每个对象共享一份。
如果static变量在类内初始化，就意味着，每次创建类的实例，都会做一次初始化，分配一次内存。


### 28. static变量和全局变量的区别
static变量和全局变量都存储在静态存储区，最主要的区别时使用范围，static变量只能在当前文件中被访问，而全局变量可以在其他文件中被访问。

### 29. static 变量的特点
- static成员变量
  ○ static成员变量属于整个类，不属于具体的对象实例，它被所有类的实例共享，既可以通过类名访问，也可以通过实例访问。
  ○ static成员变量在类中声明，类外分配内存，初始化（类外初始化，不需要加static），未在类外初始化的静态变量无法被使用。
  ○ static成员变量既可以被普通函数访问也可以被static成员函数访问。
  ○ static成员变量存储在静态存储区，不依赖于类，不计入类的大小。
  ○ 静态成员变量，可以通过设置public/protected/private ，对其进行权限控制。
  
  ```c++
  #include <iostream>
  using namespace std;
  
  class Base
  {
      public:
  		// 这里只是声明，并未分配内存
          static int m_a;
  };
  
  // 类外必须定义静态成员a，才能被适用，这里才是定义并分配内存
  int Base::m_a = 0; 
  
  int main()
  {
      Base a;
  
      // 下面种方式得到的是同一个变量
      cout << Base::m_a << ", "<< &(Base::m_a) <<  endl;
      cout << a.m_a << ", "<< &(a.m_a)  << endl;
      
      // 和空类的大小一样，等于1
      cout << sizeof(Base) << endl;
      return 0; 
  
  }
  ```
  
  

- static局部变量
  ○ 存储在静态存储区。
  ○ static局部变量在退出作用域之后，无法被访问，但仍然在内存中。
  
  ```c++
  - #include <iostream>
    using namespace std;
  
  // 用全局变量addr来记录static变量a的地址
  int addr;
  void func()
  {
      static int a = 10 ;
      addr = reinterpret_cast<int>(&a);
  }
  
  int main()
  {
      func();
      int a = *reinterpret_cast<int *>(addr);
      cout << a << endl;
      return 0; 
  }
  ```
  
    ○ 静态变量在程序运行时只会被初始化一次，因为静态变量是存储在静态数据区中的，只会在程序启动时被初始化。

```c++
#include <iostream>
using namespace std;

void print_()
{
    // 只有第一次会执行分配内存，并初始化
    // 后面每一次都不会再执行初始化的操作，而是保留上一次的值
    static int a = 10 ;

    for(int i = 0;  i < 5  ; i++)
    {
        a += i;
        cout << a << endl;
    }

}

int main()
{
    print_();
    cout << "-------------------------\n" ;
    print_();
    return 0; 
}
```



```
10 
11 
13 
16
20 
-------------------------
20 
21 
23
26
30 
```



- 静态全局变量
  ○ 静态全局变量只在定义它的文件内有效。

### 30. static函数的特点
- static 成员函数
  ○ 静态成员函数中只能调用其他静态成员函数和静态成员变量。
  ○ 静态成员函数在外部定义时，不能加static关键字
  ○ 静态成员函数，没有隐藏的this指针参数
  
  ```c++
  #include <iostream>
  using namespace std;
  
  class Base
  {
      public:
          static void do_something();
  };
  
  void Base::do_something()
  {
      cout << "Base do something." << endl;
  }
  
  int main()
  {
      Base::do_something();
      return 0; 
  }
  ```
  
  

- 静态函数
  ○ 静态函数与普通函数不同，它只能在声明它的文件当中可见，不能被其它文件使用。

### 31. `const`和宏定义的区别？
- `const`变量具有类型，在编译阶段会做类型安全检查，而宏定义常量没有类型
- `const`变量存储在静态代码区，宏定义不分配内存，不占内存空间
- 宏定义在预处理阶段处理（字符串替换），而`const`变量在编译阶段处理（定义初始化）。
- 宏定义可以通过`undef`取消定义

### 32. `typedef`和`define`有什么区别？
- 作用域：typedef定义的类型别名具有作用域，在其作用域内可以被使用；而define定义的常量没有作用域的概念，展开后的代码在整个文件中都是生效的。
- 类型检查：typedef定义的类型别名具有类型信息，编译器可以对其进行类型检查，避免类型错误；而define定义的常量只是简单的文本替换，不会进行类型检查。
- 扩展性：typedef可以为结构体、联合体、函数指针等复杂类型定义类型别名，提高了可读性和可维护性；而define只能定义简单的常量，不能使用复杂的类型。

### 33. using在c++中有哪些用法

- 定义别名

```cpp
#include<iostream>
#include<string>
#include <vector>
#include <map>
using namespace std;

int main()
{
    // 为类型std::map<std::string, std::vector<char>>，定义别名
    using map_type2 = std::map<std::string, std::vector<char>>;

    return 0;
}
```

- 修改类成员的可见性

```cpp
class Base
{
public:
    void public_func() {}
protected:
    void protected_func() {}
private:
    void private_func() {}
};

class Derived : private Base
{
public:
    using Base::public_func; // make public_func() public in Derived
    using Base::protected_func; // make protected_func() public in Derived
    // using Base::private_func; // Error: private member of Base
};

int main()
{
    Derived obj;
    obj.public_func();     // OK
    obj.protected_func();  // OK
    // obj.private_func(); // Error: private member of Base
    return 0;
}
```

- 用来将命名空间中的特定成员或所有成员引入当前作用域

```cpp
#include <iostream>

// 从std命名空间中引入cout和endl
using namespace std::cout;
using namespace std::endl;

int main() {
    cout << "hello, world." << endl;
    return 0;
}
```

- 继承构造器

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    Base(int x) { std::cout << "Base constructor.\n"; }
};

class Derived : public Base
{
public:
    // Derived(int x) :Base(x){}

	// 除了上面显示调用父类的构造函数，还可以用下面方式继承父类的构造器
	using Base::Base; // inherit Base's constructor
};

int main() {
    Derived  derived(1);
    return 0;
}
```

### 34. `typedef`和`using`的区别？

- typedef使用关键字typedef来定义类型别名，而using使用关键字using来定义类型别名。C++11 以后，using也可以用来定义模板别名和别名模板等复杂的类型别名。
- typedef是C和C++通用的语法，而using只在C++中可用。
- typedef定义的类型别名具有作用域，在其作用域内可以被使用；而using定义的类型别名也具有作用域，但在其作用域内使用时需要加上typename关键字。
总的来说，typedef通用性更好一些，使用的更多。

```c++
#include<iostream>
#include<string>
#include <vector>
#include <map>
using namespace std;

int main()
{
    // 使用using
    using map_type2  = std::map<std::string, std::vector<char>>;

    //  使用typedef
    typedef  std::map<std::string, std::vector<char>> map_type2; 
    
    return 0; 

}
```



### 35. 说一下在函数中不同位置使用const的情况，并解释不同位置下，const的作用？
- 修饰函数参数

```c++
// 传递过来的参数在函数内不可变
void function1( const int var);

// 参数指针所指内容为常量
void function2( const char* var);         

// 参数指针为常量
void function3( char* const var);         

// 引用参数在函数内为常量
void function4( const int& var);      
```

​    

- 修饰函数返回值
  ```c++
  - // 返回一个常数
  const int function5( );      
  
  // 返回一个指向常量的指针变量，使用：const int *p = function6( );
  const int* function6( );     
  
  // 返回一个指向变量的常指针，使用：int* const p = function7( );
  int* const function7( );     
  ```

  

- 修饰成员函数
  ```c++
  - // 类成员函数
    // 表示该函数不会修改成员变量，const放在函数声明和实现之间，这种用法只能用在类成员函数上，也叫常成员函数。 
    // 全局函数不能这样用
  
  /*
  
  const object 数据不能被修改
  common object 数据可能被修改
  const member function 函数内数据不会被修改
  common member function 函数内数据可能会被修改
  
  common object 可以同时调用const member function 和 common member function
  const object 只能调用const member function
  
  此外：
  	当一个函数同时存在const版本和common版本时
  	common object只能调用common member function，
  	const object只能调用const member function
  */
  class xxx
  {
  	...
  
  	int get_a() const {return a;}
  	...
  }
  ```

  

### 36. 什么内联函数，说一下`inline`的优缺点，它和宏定义有什么区别？
内联函数，内联函数是一种在编译时将函数体嵌入到调用点处的函数，而不是在运行时通过跳转到函数的地址来执行函数体，它的关键字是inline；
内联函数有以下几个特点

- 它把内联函数里面的内容写在调用内联函数处；
- 它减少了调用函数的步骤，直接执行函数体；
- 相比于宏定义，比宏多了类型检查，具有真正的函数特性；
- 是否将函数变为内联函数，由编译器决定，编译器一般不内联包含循环、递归、switch 等复杂操作的内联函数；
- 在类声明中定义的函数，除了虚函数的其他函数都会自动隐式地当成内联函数。

内联函数的优点
- 内联函数同宏函数一样将在被调用处进行代码展开，省去了参数压栈、栈帧开辟与回收，结果返回等，从而提高程序运行速度。
- 内联函数相比宏函数来说，在代码展开时，会做安全检查或自动类型转换（同普通函数），而宏定义则不会。
- 在类中声明同时定义的成员函数，自动转化为内联函数，因此内联函数可以访问类的成员变量，宏定义则不能。
- 内联函数在运行时可调试，而宏定义不可以。

内联函数带来的问题
- 代码膨胀。内联是以代码膨胀（复制）为代价，消除函数调用带来的开销。如果执行函数体内代码的时间，相比于函数调用的开销较大，那么效率的收获会很少。另一方面，每一处内联函数的调用都要复制代码，将使程序的总代码量增大，消耗更多的内存空间。
- inline 函数无法随着函数库升级而升级。inline函数的改变需要重新编译，不像 non-inline 可以直接链接。
- 是否内联，程序员不可控。内联函数只是对编译器的建议，是否对函数内联，决定权在于编译器。
因此，逻辑简单的并且经常使用的函数都建议加上inline，告诉编译器尽量把它变成inline。

### 37. `struct`和`class`的区别
- struct 中的成员默认都是public的，而class中的成员默认都是private的
- struct 默认都是public继承的，而class默认都是private继承

### 38. `explicit` 的作用，为什么要用它
使用explicit式为了避免隐式的类型转换所导致的意料之外的结果。
比如下面是未使用explicit的例子

```c++
#ifndef __FRACTION__
#define __FRACTION__
#include <iostream>
#include <ostream>
using namespace std;
class Fraction
{
    int molecular, denominator;
    public:
    	//  non-explicit one argument ctor
        Fraction(int _molecular, int  _denominator = 1) 
    	:molecular(_molecular), denominator(_denominator){ }
    
    	// 定义double 转换操作符，当Fraction 和 double类型进行计算时，Fraction类型会自动转换为double类型
    	inline operator double() const{ return (double)molecular / denominator;}
    
        inline int get_molecular(){return molecular;}
        inline int get_denominator(){return denominator;}

};

inline ostream& operator << (ostream & cout , Fraction frac)
{
    return cout << frac.get_molecular() << endl << "-" << endl << frac.get_denominator() << endl;
}

#endif // __FRACTION__

int main()
{
    Fraction frac(3,  10 );

    // frac被隐式转换为double类型，4也 被隐式转换为double
	double a = frac + 4; 
	cout << a << endl;   


    // 4也 被隐式转换为Fraction
    Fraction frac1  = frac + 4; 
	cout << frac1; 
    return 0; 
}
```

下面使用explicit的例子，对构造函数增加explicit关键字后，构造函数不会被隐式的调用。避免了不可测的行为。

```c++

#ifndef __FRACTION__
#define __FRACTION__
#include <iostream>
#include <ostream>
using namespace std;

class Fraction
{
    int molecular, denominator;
    public:
    	// explicit ctor, 这里必须加上关键字explicit，意思是告诉编译器，该构造函数必须显式的调用，而不能通过自动类型转换调用
        explicit Fraction(int _molecular, int  _denominator = 1) 
    	:molecular(_molecular), denominator(_denominator){ }
        
    	inline explicit operator double() const{ return (double)molecular / denominator;}
    
        inline int get_molecular(){return molecular;}
    
        inline int get_denominator(){return denominator;}
    
        inline Fraction operator + (const Fraction & frac)
        {
            // 这里只是随便返回一个对象，没有具体实现
            return Fraction(1) ;
        }
};

inline ostream& operator << (ostream & cout , Fraction frac)
{
    return cout << frac.get_molecular() << endl << "-" << endl << frac.get_denominator() << endl;
}
#endif // __FRACTION__

int main()
{
    Fraction frac(3,  10 );
    /* 
        构造函数前面加上explicit关键字之后，4  不会被隐式的转换为Fraction。
    	因此下面只会显式将frac转换为double，然后进行计算
    */ 
    double b = (explicit)frac + 4; 
    cout << b << endl;
    return 0; 
}
```

### 39. 说一下友元的应用场景，它会有什么问题
- 友元函数
友元函数是指可以访问类的私有成员的非成员函数，在函数声明时，需要使用friend关键字。

```c++
#ifndef __COMPLEX__
#define __COMPLEX__
#include <iostream>
using namespace std;
class complex
{
    public:
        complex(int a = 1,  int b = 0) 
        :real(a), imag(b)
        {    }
    
        int get_real() const {return real;}
        int get_imag() const {return imag;}
    
    private:
        int real, imag;
    
    	// 声明友元函数
        friend complex &  __doapl(complex* cpx_0,  const complex & cpx_1) ;
};

// 定义友元函数，无需加friend关键字
// 友元函数内，可以直接访问到类的私有成员
inline complex & __doapl(complex* cpx_0,  const complex & cpx_1) 
{
    cpx_0- >imag += cpx_1. get_imag();
    cpx_0- >real += cpx_1. get_real();
    return *cpx_0; 
}
#endif

```

- 友元类
友元类是指具有类的私有成员的访问权限的类，可以在友元类的成员函数中访问类的私有成员，友元类同样需要使用friend关键字进行声明

```c++
#include <iostream>
using  std::cout;

class Complex
{
    public:
        Complex(int a = 1,  int b = 0) :real(a), imag(b) {    }

        int get_real() const
        {
            return real;
        }
        int get_imag() const
        {
            return imag;
        }

		//  声明友元类
        friend class FriendClass;
    private:
        int real, imag;

        friend Complex &  __doapl(Complex* cpx_0,  const Complex & cpx_1) ;
};

inline Complex & __doapl(Complex* cpx_0,  const Complex & cpx_1) 
{
    cpx_0- >imag += cpx_1. get_imag();
    cpx_0- >real += cpx_1. get_real();
    return *cpx_0; 
}

class FriendClass
{
    public:
        int get_real(Complex com)
        {
            return com.real;
        }
};

int main()
{
    Complex comp(1,  2) ;
    FriendClass a;
    cout << a.get_real(comp);
    return 0; 
}
```

由于友元的特性，它会带来以下的问题

-  友元可以绕过类的访问控制机制，类的私有成员可以在外部访问， 这破坏了类的封装，有可能导致潜在的安全风险。

- 友元增加了类和类之间的依赖，降低了代码的可维护性，并且使得变量的修改很难被追踪。

### 40. 解释一下C++中的类型转换
- **`dynamic_cast`** 
  `dynamic_cast` 是专门用于沿继承层次关系的类型装换。
  ○ 使用`dynamic_cast` 进行指针或者引用类型转换，指针指向的对象必须具有继承关系，并且必须是多态类型（类内部包含虚函数）
  ○ `dynamic_cast` 转换会做运行时类型检查（Run-Time Type Information：RTTI ），有一定的性能开销（关闭运行时类型检查后，`dynamic_cast`会报错）

```c++
#include <iostream>
using namespace std;
class Entity
{
	public:
    	virtual void set_name() {}
};

class Player: public Entity{};
class Enemy: public Entity{};

int main()
{
    Entity *p1  = new Entity;
    Entity *p2  = new Player;
    Entity *p3  = new Enemy;
    Player *player1  = dynamic_cast<Player*>(p2) ;

    // 转换失败，返回NULL
    Player *player2  = dynamic_cast<Player*>(p3) ;

    if(player1  == nullptr) cout << "convert p2  to Player failure" << endl;

    if(player2  == nullptr) cout << "convert p3  to Player failure" << endl;

    cout << "Finished" << endl;
    return 0; 
}
```



- **`static_cast`**
  ○ 它可以用于相关类型的转换，可用于普通类型的转换。
  ○ 不带运行时类型检查（有编译期类型检查），这意味着，在转换之前，你必须明确知道一个对象的类型。
  ○ 对指针或者引用做类型转换，由于没有运行时检查，所以都会成功。

```c++
#include <iostream>
using namespace std;
class Entity
{
	public:
    	virtual void set_name() {}
};

class Player: public Entity{};
class Enemy: public Entity{};

int main()
{
    // 普通类型转换
    int a = 0; 
    float b = static_cast<float>(a);
    cout << b << endl;

    // 指针类型转换
    Entity *p1  = new Entity;
    Entity *p2  = new Player;
    Entity *p3  = new Enemy;
    
    // 下面的转换都会成功
    Player *player1  = static_cast<Player*>(p2) ;
    Player *player2  = static_cast<Player*>(p3) ;
    
    cout << "Finished" << endl;
    return 0; 

}
```



- **`const_cast`**
`const_cast`可以用来消除指针的`const`或者`volatile`属性

```c++
#include <iostream>
using namespace std;
int main()
{
  const int* const p = new int();
  int *p1  = const_cast<int*>(p);
  int a = 10 ;

  // 指针p1  既可以改变值，也可以改变指向
  p1  = &a;
  *p1  = 20 ;
  return 0; 
}
```

- **`reinterpret_cast`**
  ○ 用户对不相关类型指针或引用的转换，可以对任意类型的指针和引用做类型转换，它最灵活的一种类型转换方式。
  ○ 对于`static_cast`操作符,如果需要截断，补齐或者指针偏移编译器都会自动完成.注意这一点,是和 `reinterpret_cast` 的一个根本区别.
  ○ 简单来说，就是`reinterpret_cast`，只是简单改变指针的类型，至于指针指向的内容，不会有任何变化。（就像是本来是一个红色的盒子，然后，把红色的盒子换成了绿色，盒子里面的东西还是一模一样）

下面的代码可以实现和`b = reinterpret_cast<type1  *>(a)`同样的目的，只不过`reinterpret_cast`不会操作内存，只改变编译器对数据的解释方式（用`reinterpret_cast`将一个int型的指针转换为float类型的指针后，然而其实内存中的内存没有改变，只是告诉编译器，这块内存存储的是float，不再是int型，然后，编译器会把这块内存当做float类型来解释，得到的结果自然是无意义的值，因为两种类型在内存中的布局不同）。	

```c++
type *a;

type1  *b;

memcpy((void *)b, (void *)a, sizeof(type));
```



### 41. 介绍一下RAII
 RAII（Resource Acquisition Is Initialization）是一种利用对象生命周期来控制程序资源（如内存、文件句柄、网络连接、互斥量等等）的简单技术。它通过类的构造函数和析构函数来实现对资源在对象整个生命周期内的管理。即构造函数中申请资源，析构函数中释放资源。

### 42. const常量在C和C++中有什么区别
- c++中的const常量，在定义的时候，必须对其初始化，而C中，可以不做初始化。
- C++中，编译器对const修饰符，具有更严格的限制，比如不能直接将地址赋给非常量指针或者非常量引用，也不能通过指针强制转换的方式对其进行修改（const_cast除外）。
- const并未区分出编译期常量和运行期常量（可以是编译期常量，也可以是运行期常量，取决于编译器），而constexpr限定在了编译期常量。

```c++
- #include <stdio.h> 
  #include<iostream>
  using namespace std;

int main() {
    const int a = 10 ;
    int *p = (int *)(&a);
    *p = 20 ;

    // 取地址，也无法修改a的值	
    /*
    输出
    a = 10 , *p = 20  
    */
    cout << "a = " << a << ", *p = " << *p << endl;
    return 0; 

}


#include <stdio.h>
int main()
{
    const int a;
    int b = 4; 
    int *p = &a;
    *p = 20 ;


    /*
    输出：
    64 22 29 2,  64 22 29 6
    20 , 20   
    */
    printf("%d, %d\n", &b, p);
    printf("%d, %d", a, *p);
    return 0; 

}
```



- 对于定义为const的变量，编译器可以在编译时就将其值替换到代码中，这样在运行时就不需要从内存中读取值。这种优化技术称为“常量折叠”。在C++中，const常量意味着只读，正常情况下，不应该通过一些非法的方式，绕过编译器的限制去修改它。
  因此，下面非法的操作应该尽可能的避免

  ```c++
  
  - #include <stdio.h> 
    #include<iostream>
    using namespace std;
  
  int main() {
  
      // 第一种方式，使用volatile
      const volatile int a = 10 ;
      int *p = (int *)(&a);
      *p = 20 ;
      /*
      输出：
      a = 20 , *p = 20 
      */
      cout << "a = " << a << ", *p = " << *p << endl;
  
  
      // 第二种方式，使用const_cast，将常量指针转化为普通指针
      
      // 第三种方式，使用常量引用
      int aa = 3; 
      const int &b = aa;
      aa = 4; 
      cout << "aa = " << aa <<", b = " << b << std::endl;   
      return 0; 
  
  }
  ```

  

### 43. 说一下C++模板的偏特化与全特化它们的应用场景
模板是一种将类型参数化，从而达到高效的代码复用的工具，它可以分为类模板和函数模板。而模板特化是一种模板的定制化方式，它可以让模板针对某些特定的类型或形式进行不同的实现。模板特化分为全特化和偏特化。全特化是指为模板提供一个完整的类型列表，使得模板只适用于这些类型。



- 模板全特化

下面式全特化的例子，Compare是一个模板类，其中只有一个类型参数，Compare类的全特化就是固定所有类型参数的特化。在创建类的实例时，通过指定模板类型参数，对不同的全特化类实例化。

```c++
#include <iostream>
using namespace std;

// 泛化的Compare类模板
template<class T>
class Compare
{
public:
    bool equal(T a, T b);
};

template<class T>
bool Compare<T>::equal(T a, T b)
{
    return a == b;
}

// 基于Compare模板类，全特化的类
// T 被指定为float，但定义Compare<float>类时，就会使用下面的全特化的Compare类
template<>
class Compare<float>
{
public:
    bool equal(float a, float b);
};

bool  Compare<float>::equal(float a, float b)
{
    return std::abs(a - b) < 10e-3;
}

int main()
{
    Compare<float> a;
    return 0;
}

```

- 模板偏特化

模板偏特化是指为模板提供一个部分的类型列表，使得模板适用于这些类型的子集（函数没有偏特化的概念）。模板的偏特化分为两种，一种是个数的偏，即在特化的过程中，之间部分类型参数固定，其余的仍然可变，另一种是类型上的偏

a. 个数上的“偏”，部分类型被绑定

```cpp
template<typename T1, typename T2>
 class A
 { };

// T1 绑定成int类型
template<typename T2>
 class A<int, T2>
 { };
```

b. 范围上的“偏”，参数的范围进一步缩小

```cpp
template<typename T1>
 class A
 { };


// T1 类型缩小为指针类型
template<typename T1>
 class A<T1 *>
 { };


// T1 类型缩小为引用类型
template<typename T1>
 class A<T1 &>
 { };

// T1 类型缩小为T1的右值类型
template<typename T1>
 class A<T1 &&>
 { };
```

- 全特化的应用场景

  - 使用全特化来实现单例模式，用于保证类只有一个实例。

  - 使用全特化来实现hash函数，用于支持自定义类型作为unordered容器的键。

    

- 偏特化的应用场景
  - 使用偏特化来实现traits类，用于获取类型的属性或行为。
  - 使用偏特化来实现智能指针，用于管理不同类型的资源。



### 44. 解释一下C++中的内存对齐？
内存对齐可以理解为一种，内存加速访问的技巧，在实际应用上，每个成员的内存地址，并不会从上一个成员内存的末尾开始存储，而是从min(k, n)的整数倍的位置开始存（k为该成员的对齐字节数，n为有效对齐字节，即n和类中最大成员对齐字节数中较小的那个。通常而言，32 位平台n默认等于4个 字节， 64 位平台n默认等于8个 字节）。最后整个类的大小应该是n的整数倍。
内存对齐的目的是为了提高访问内存的效率，因为 CPU 访问内存时通常是以一个字节或多个字节为单位进行读写的。如果数据没有对齐，那么 CPU 需要进行多次读写操作才能获取或修改这个数据，这样会降低程序的执行效率，从而影响性能。
下面是一个解释内存对齐的例子

```c++
#include <iostream>
using namespace std;

class B{double m_a;};

class A
{
    char m_a;
    int m_b;
    B b;
};

class Base
{
    A a;
    char m_a[2] ;
};

/*

### 64 位操作系统下

类B的大小为8； 
然后看类A，m_a的大小是1， 存放在offset为0的 位置，m_b的大小是4， 存放在offset为4的 位置，b的大小为8， 存放在位置为8的 位置，所以，可以看出，类A的大小为16 ；
最后看Base类，a的大小为16 ，存放在offset为0的 位置，m_a的大小为2， 因为此时的对齐系数为8， 所以最后Base类的大小应该是8的 整数倍，所以结果为24 .
*/
int main() 
{
    cout << sizeof(A) << ", " << sizeof(Base) << endl;
    return 0; 
}
```

输出结果为：

> 16 , 24 

其中，有效对齐字节n可以通过pragma来设置
```c++
#include <iostream>
using namespace std;

// 设置对齐系数为4
#pragma pack(4) 

class A
{
    double m_a;
};

class Base
{
    A a;
    char m_a[2] ;
};

int main() {

    // 输出12 （类的大小对齐4的 倍数就行）
    cout << sizeof(Base) << endl;
    return 0; 

}
```




### 45. 解释一下`volatile`关键字
在 C++ 中，volatile 是一个关键字，它用于修饰变量，告诉编译器该变量的值可能会在程序运行期间发生变化。
使用 volatile 修饰的变量，编译器不能对其进行优化，必须按照程序代码的顺序读取和写入该变量的值，以保证程序的正确性。
具体来说，使用 volatile 关键字修饰的变量，其在程序中的读取和写入操作不会被编译器优化为寄存器操作或常量表达式。这是因为编译器会认为这个变量的值可能会在程序运行期间被其它线程或硬件设备修改，因此需要每次从内存中读取该变量的最新值，以避免出现未定义的行为。

volatile 变量通常用于以下场景：
- 多线程访问共享变量时，需要使用 volatile 关键字保证变量的值能被正确地读取和修改。
- 在嵌入式系统或硬件驱动开发中，经常需要使用 volatile 关键字来声明硬件寄存器变量，以保证每次访问该寄存器都能反映其最新状态。

### 46. 浅拷贝和深拷贝有什么区别？
- 浅拷贝只拷贝对象的引用。
- 深拷贝则是真正的完全复制，它会递归的复制对象的所有内容。

### 47. `sizeof`和`strlen`有什么区别？
- sizeof用于计算对象在内存中占用的字节数。
- 而strlen用来计算以\0结 尾的字符串的长度。

### 48. 说一下类的初始化列表，为什么说它可以提高效率?
在 C++ 中，初始化列表是一种特殊的语法，它可以用于在构造函数中初始化成员变量。初始化列表通过在构造函数的参数列表后面使用冒号(:)来实现。例如：

```c++
class MyClass 
{ 
	public:
		MyClass(int a, int b) : m_a(a), m_b(b) {} 
	private:     
		int m_a;     
		int m_b; 
};
```



在上面的例子中，初始化列表被用来初始化 MyClass 类中的成员变量 m_a 和 m_b。初始化列表可以提高效率，因为它们允许成员变量在对象构造时直接被初始化，而不是在构造函数的函数体中被赋值。这样可以避免在对象构造后额外执行一次赋值操作的开销。
另外，对于一些复杂的类，成员变量的初始化可能需要进行一些计算或者资源的分配，如果将这些操作放在构造函数的函数体中，可能会导致性能问题。使用初始化列表可以在对象构造时直接进行这些操作，从而避免了在构造函数体中的额外开销。

### 49. 内存泄漏的场景一般有哪些情况
- 程序执行过程中，出现异常，但堆上分配的内存未得到释放。
- new和delete未成对使用
- 基类的析构函数未定义为虚函数，导致子类的析构函数未被调用。
- 指针赋值错误，导致原有指向的内容无法被释放。
- 循环引用，导致对象无法被释放，从而导致内存泄漏。

### 50. 解释一下`constexpr`关键字？

constexpr 关键字的功能是使指定的常量表达式获得在程序编译阶段计算出结果的能力，而不必等到程序运行阶段。C++ 11及之后的标准中，constexpr 可用于修饰普通变量、函数（包括模板函数）以及类的构造函数。
**注意**，获得在编译阶段计算出结果的能力，并不代表 constexpr 修饰的表达式一定会在程序编译阶段被执行，具体的计算时机还是编译器说了算。

- constexpr修饰变量

```c++
#include <iostream>
using namespace std;
int main()
{
    // 合法           
	int array[4  + 6] ;

    int nums = 4; 
    // 不合法
    // int array1[ nums]
    
    constexpr int nums1  = 4; 
    // 合法
    int array1[ nums1] 

}
```



- constexpr修饰函数，这样的函数也叫常量表达式函数
  常量表达式函数需要满足以下3个 条件

  - 除了非代码语句（ using 指令、typedef 语句以及 static_assert 断言），只包含单一的return语句（C++14 标准以下）

  - 函数必须有返回值（即不能式void函数） 

  - 常量表达式函数在被使用之前必须已有定义。 

  - return返回语句表达式中不能使用非常量表达式的函数，全局数据，且必须是一个常量表达式。 

  constexpr函数是一种在编译期和运行期都能被调用并执行的函数，如果不满足任意一个条件，将只能被当做普通函数使用。


```c++
#include <iostream>
using namespace std;

constexpr int factorial(int n)
{
    return (n <= 1)  ? 1  : (n * factorial(n - 1) );
}

int main()
{
    //调用常量表达式函数
    const int num = 5; 
    int arr[factorial(num)];
    return 0; 

}
```



- constexpr 修饰成员变量和成员函数

下面的例子中，我们首先创建了一个常量Circle对象，然后计算它的面积，之所以可以在创建对象时，可以将其定义为constexpr，是因为我们将类的构造函数定义为常量表达式函数。
还有一点需要注意的是，常量表达式构造函数，必须使用初始化列表的方式对成员变量进行初始化，并且函数体中不能包含任何内容。
此外，除了构造函数外，其他函数均被constexpr修饰，和上面一样，它同样需要满足4个 条件，才能被当做常量表达式函数使用。

```c++
class Circle {
    public:
    // 没有带constexpr的构造函数，将无法构造constexpr类型的类对象
    // 必须使用初始化列表进行初始化
    // 函数体中不能包含任何内容
    constexpr Circle(double r) : radius(r) {}

    constexpr double get_radius() const { return radius; }
    constexpr double area() const { 
        return pi * radius * radius; 
}

private:
    static constexpr double pi = 3. 14 15 92 6; 
    double radius;
};

int main() {
    constexpr Circle c(2. 0) ;
    constexpr double circle_area = c.area(); // 在编译时求值
    return 0; 
}
```



### 51. `const`和`constexpr`有什么区别？

- 修饰函数时，两者的作用不同，const既可以用在修饰函数参数也可以修饰函数返回值，用来限定函数参数或者返回值只读，而constexpr修饰函数则表示，希望该函数被当做常量表达式函数，在编译期就可以确定函数返回的值。

- 修饰变量，const常量不一定是编译期确定，而constexpr常量一定是在编译期确定的。



### 52. `enum`和`enum class`的区别？



- enum class的枚举元素是局部的，不会污染所在的命名空间，而enum的枚举元素是全局的，可能会与其他名称冲突

```c++
//定义一个enum
enum Color {
  Red,
  Green,
  Blue
};

//定义一个enum class
enum class Fruit {
  Banana,
  Apple,
  Orange
};

//使用enum和enum class
//正确，Red是全局的
Color c = Red; 

//错误，Banana不是全局的，需要加上Fruit::
Fruit f = Banana; 

//正确，使用Fruit::Banana来表示枚举元素
Fruit f = Fruit::Banana; 
```

- enum class的枚举元素的值不会隐式转换为其他类型，而enum的枚举元素的值可以隐式转换为整数或其他类型

```c++

//定义一个enum
enum Color {
  Red,
  Green,
  Blue
};

//定义一个enum class
enum class Fruit {
  Banana,
  Apple,
  Orange
};

//正确，Red的值可以隐式转换为int
int n = Red; 

//错误，Fruit::Banana的值不能隐式转换为int，需要强制转换
int m = Fruit::Banana; 

//正确，使用static_cast来强制转换为int
int m = static_cast<int>(Fruit::Banana); 

//正确，Red的值可以与整数比较
if (Red == 0) { 
  cout << "Red is zero." << endl;
}

//错误，Fruit::Banana的值不能与整数比较，需要强制转换
if (Fruit::Banana == 0) { 
  cout << "Banana is zero." << endl;
}

//正确，使用static_cast来强制转换为Fruit
if (Fruit::Banana == static_cast<Fruit>(0)) { 
  cout << "Banana is zero." << endl;
}
```



- enum class可以指定枚举的底层类型，而enum不能

```c++
//定义一个enum class，并指定底层类型为char
enum class Fruit : char {
  Banana,
  Apple,
  Orange
};

//定义一个enum，并试图指定底层类型为char（错误）
enum Color : char {
  Red,
  Green,
  Blue
};

```



- enum class可以避免一些潜在的错误，例如相同值的枚举元素之间的比较或赋值

```c++

//定义两个不同的enum
enum Color {
  Red,
  Green,
  Blue
};

enum TrafficLight {
  Red,
  Yellow,
  Green
};

//使用两个不同的enum
//正确，Red是Color类型的枚举元素
Color c = Red; 

//正确，Red也是TrafficLight类型的枚举元素
TrafficLight t = Red; 

//正确，但可能是错误的逻辑，因为c和t是不同类型的枚举变量，但它们的值都是0
if (c == t) 
{ 
  cout << "c and t are equal." << endl;
}

//错误，Yellow不是Color类型的枚举元素
c = Yellow; 

//错误，c和t是不同类型的枚举变量，不能赋值
t = c; 

// ----------------------------------------------------------------------- //
//定义两个不同的enum class
enum class Shape {
  Circle,
  Square,
  Triangle
};

enum class Planet {
  Earth,
  Mars,
  Jupiter
};

//使用两个不同的enum class
//正确，Shape::Circle是Shape类型的枚举元素
Shape s = Shape::Circle; 

// 错误
Planet p = s
```



------



## C++面向对象



### 1.  构造函数能否为虚函数

不能

构造函数的作用在于创建一个类具体的对象，即它必须明确的类型信息，知道需要构造一个什么类的对象，而虚函数的调用，并不需要知道调用者的准确类型，比如，可以通过子类或者当前类调用。这和构造函数的作用是矛盾的。

### 2.  构造函数调用虚函数会发生什么

- 首先在构造函数中调用虚函数，语法上，并不会产生错误
- 但基类的构造函数对虚函数的调用，不会传递到派生类，从而导致意料之外的结果。

可以这么理解，在 C++ 中，调用虚函数时，会根据对象的动态类型来决定调用哪个版本的函数。但是，在构造函数中，对象的动态类型还没有完全确定，因为派生类的部分还没有被构造。所以，在基类的构造函数中，如果调用了虚函数，只会调用基类自己定义的版本，而不会调用派生类重写的版本。这是为了避免在对象还没有完全初始化的情况下，调用一个可能依赖于派生类成员变量或函数的虚函数。

比如下面的例子

```c
#include <iostream>
using namespace std;

class Base 
{
    public:
        Base() {
            cout << "Base constructor" << endl;
            foo();
        }
        virtual void foo() {
            cout << "Base foo" << endl;
        }
};

class Derived : public Base 
{
    public:
        Derived() {
            cout << "Derived constructor" << endl;
        }
    	// 该函数不会被调用
        void foo() override {
            cout << "Derived foo" << endl;
        }
};

int main() {
    Derived d;
    return 0;
}
```



在这个例子中，我们创建了一个 `Derived` 类的对象。在 `Derived` 类的构造函数中，它首先调用了基类 `Base` 的构造函数。在 `Base` 类的构造函数中，我们调用了虚函数 `foo()`。实际上，输出的是 `"Base foo"`。这是因为，在调用虚函数时，实际调用的是虚函数表中指向的函数。而在构造函数中，虚函数表尚未完全建立，因此调用虚函数可能不会产生预期的行为。

### 3.  为什么内联函数，构造函数，静态成员函数不能为virtual函数？

- 内联函数，在编译阶段会将函数展开，插到函数调用处，因此内联函数在编译阶段必须是可以确定的，而虚函数，是在运行时，通过虚函数指针来确定函数调用的。
- 静态成员函数，静态成员函数既可以通过类调用，也可以通过类对象调用，而虚函数只能通过类对象调用。



### 4.  C++虚函数表和虚函数指针机制

- 内存：由于编译器会为每个包含虚函数的类分配一个虚函数表，以及一个虚函数指针，会增加额外的内存，会影响内存的使用效率和缓存的命中率。
- 效率：虚函数的调用需要虚指针索引虚函数表，然后通过虚函数指针调用虚函数，存在一定的性能开销。从cache的角度来看，需要调用虚函数，这可能导致指令缓存未命中（instruction cache miss），因为虚函数的地址在运行时才确定，编译器无法预测和优化。
- 复杂度：虚函数会增加代码的复杂度，降低代码的可维护性和可读性。
- 优化：编译器会阻止一些优化，比如inline，常量折叠，死代码消除（删除无用代码）等编译器优化手段。

### 5.  构造函数和析构函数能否重载？

- 定义基类的指针指向派生类，它具有派生类的行为。
- 定义一个基类类型的数组，里面存放子类的对象。
- 定义基类的对象，指向派生类的引用。

### 6.  override的作用

`override` 关键字用于显式指示派生类中的函数重写了基类中的虚函数。这样，如果派生类中的函数签名与基类中的虚函数不匹配，编译器就会报错。这有助于防止意外地更改基类中虚函数的行为。

如果不使用 `override` 关键字，派生类中的函数仍然可以重写基类中的虚函数，但编译器不会检查函数签名是否匹配。这可能会导致意外的行为。

例如，假设我们有一个基类 `Base` 和一个派生类 `Derived`：

```c
class Base {
    public:
        virtual void foo(int x) {
            // ...
        }
};

class Derived : public Base {
    public:
        void foo(int x) override { // 使用 override 关键字
            // ...
        }
};
```

在这个例子中，派生类 `Derived` 中的 `foo` 函数重写了基类 `Base` 中的虚函数 `foo`。由于我们使用了 `override` 关键字，如果我们更改了基类中 `foo` 函数的签名（例如，将参数类型从 `int` 更改为 `double`），编译器就会报错，因为派生类中的 `foo` 函数不再重写基类中的虚函数。

### 7. `->*`,`::*`以及`.*`分别是什么意思

在C++中，`->*`,`::*`以及`.*`是指向成员指针运算符，用于通过指针或引用访问类的成员变量或成员函数。

`::*`是`**指向成员的指针运算符**`，用于`**定义指向类成员的指针或引用**`。具体来说，`::*`运算符的作用是将指针或引用与类成员关联起来，从而可以通过指针或引用来访问类成员。例如，`int (Base::*ptr)() = &Base::get_val`;定义了一个指向Base类成员函数`getval`的指针`ptr`，可以使用`(obj.*ptr)()`来调用Base类的getval函数。此外，可以使用typedef或using关键字为指向成员函数的函数指针定义别名，使代码更加清晰易读，方便维护和修改。

`->*`和`.*`都是`**指向成员的指针运算符**`，用于定义指向类成员的指针或引用。具体来说，`->*`运算符用于访问指向类成员的指针所指向的成员，而.*运算符用于访问指向类成员的引用所引用的成员。例如，假设有一个指向类成员函数的指针FuncPtr，可以使用`obj->*FuncPtr()`来调用类的成员函数，其中obj是一个指向类对象的指针。同样地，如果有一个指向类成员变量的引用RefVar，可以使用`obj.*RefVar`来访问类的成员变量，其中obj是一个类对象。需要注意的是，`->*`和`.*`只能用于指向类成员的指针或引用，不能用于普通指针或引用。



具体示例代码如下：

```cpp
#include <iostream>
using namespace std;
class Base {
    public:
        int x = 1;
        void foo(int n) {
            std::cout << "foo(" << n << ") is called" << std::endl;
        }
};

int main() {
	Base  base;

    // 定义一个指向Base类成员函数的指针类型，别名为Func
    // 该类型的函数签名是参数类型为int，返回值为void
    typedef void (Base::*Func)(int);

    // 定义指针fn，指向Base的成员函数foo
    Func fn = &Base::foo;

    // 通过对象调用
    (base.*fn)(3);

    Base *p = &base;

    // 通过对象指针调用
    (p->*fn)(4);


    int Base::*var = &Base::x;
    cout << base.*var << endl;

    return 0;
}
```

在上面的示例中，我们定义了一个名为MyClass的类，它有一个名为x的公共整型成员变量和一个名为foo的公共成员函数。我们首先创建了一个MyClass对象obj和指向该对象的指针p，并且定义了一个指向成员变量x的指针mp和一个指向成员函数foo的指针fp。

### 8. 复合对象，继承对象以及复合继承对象，构造函数和析构函数的调用顺序？

对于复合对象：

- 构造的顺序是：先构造成员对象，接着是构造自己
- 析构的顺序是：先析构自己，然后是析构成员对象

对于继承对象

- 构造的顺序是：先构造成员对象，接着是构造自己
- 析构的顺序是：先析构自己，然后是析构成员对象

对于复合继承对象

- 构造的顺序是：先构造基类对象，然后是成员对象，最后是构造自己
- 析构的顺序是：先析构自己，然后是析构成员对象，最后是基类对象

### 9.  C++中类的访问权限
类的访问权限可以通过public、protected和private关键字来指定。

- public成员可以被任何函数访问，包括类的成员函数、友元函数和全局函数；
- protected成员可以被`类的成员函数`和`友元函数`访问，但不能被全局函数访问；
- private成员只能被`类的成员函数`和`友元函数`访问，不能被全局函数访问。



默认情况下，类的成员和继承的成员都是private的。需要注意的是，类的访问权限只对类的外部代码起作用，对类的内部代码没有限制。

具体示例代码如下：

```cpp
#include <iostream>
using namespace std;
class Base
{
    public:
        int m_public;    // public member
    protected:
        int m_protected; // protected member
    private:
        int m_private;   // private member
};

class Derived : public Base
{
public:
    void foo()
    {
        m_public = 1;     // OK
        m_protected = 2;  // OK
        // m_private = 3; // Error: private member of Base
    }
};

int main()
{
    Base obj;
    obj.m_public = 1;     // OK
    // obj.m_protected = 2; // Error: protected member of Base
    // obj.m_private = 3;   // Error: private member of Base
    return 0;
}
```

### 9. 类继承有哪些方式

- public继承：父类的`public`成员继承之后还是`public`，父类的`protected`成员还是`protected`，父类的private成员继承之后不可访问。
- protected继承：父类的`public`成员和`protected`成员继承之后都变为`protected`成员，父类的`private`成员继承之后不可访问
- private继承（默认）：父类的`public`成员和`protected`成员继承之后都变为`private`成员，父类的`private`成员继承之后不可访问



private继承和protected继承，相当于基类对外完全封装了实现细节，并不希望外界访问到它（此时无法将一个子类对象转换为父类），当然如果又不想完全封闭，可以使用using暴露部分接口。

此外，使用private或者protected继承，可以避免一些语义上的错误，比如汽车类继承自发动机类，如果采用public继承，很多时候，我们将汽车类的对象传递给一个发动机类的引用或者指针，导致语义或者逻辑上的错误。

它们都可以看成是类的复合，但相比于类的复合，它们有一个好处是空类压缩，节省空间。

```cpp
#include <iostream>
using namespace std;
class Empty {};

class Derived: private Empty
{
    int x;
    // Empty a;
};

int main()
{
    std::cout << sizeof(Derived) << std::endl;  // Output: 4
    return 0;
}
```

### 10. 解释一下this指针

- this指针在类中，表示当前类的指针，指向当前类。

- 每个类的非静态成员函数都包含了一个隐藏的参数，就是this指针。

- this指针的指向是不可改变的，因此它的类型（隐式声明的类型）是 T* const this； 



### 11. 解释一下this指针

- this指针在类中，表示当前类的指针，指向当前类。

- 每个类的非静态成员函数都包含了一个隐藏的参数，就是this指针。

- this指针的指向是不可改变的，因此它的类型（隐式声明的类型）是 T* const this； 

### 12. override和overload的区别

- override表示覆盖，它表示在派生类中，重新定义父类中的虚函数，覆盖掉父类中的`虚函数`。
- overload表示重载，它表示在同一个作用域内，定义多个同名的当时具有不同签名的函数。

### 13. 面向对象的3大特性

- 封装：将实现细节封装在类的内部，只对外提供接口，可以保证代码的安全，并且避免内部变化影响接口。
- 继承：一个类可以继承自其它类，从而实现在实现更多功能的前提下，最大限度的实现代码复用。
- 多态：一个函数的调用者，可以根据参数的具体类型，从而表现出不同的行为。

### 14. 虚函数和纯虚函数
- 虚成员函数表示派生类可以在自己的实现中重写父类的虚成员函数。
- 纯虚函数表示派生类必须重写父类的纯虚函数，纯虚函数不能有任何实现，它的形式是：`type pure_virtual_func(type ...) = 0;`包含纯虚函数的类也叫做抽象类，抽象类无法被实例化。

```cpp
#include <iostream>
using namespace std;
class Base {
public:

	// 	纯虚函数
    virtual int get_val() const = 0;

	// 虚函数
     virtual void print()
    {
        cout << "Base::print\n";
    }

};

class Derived: public Base
{
public:
    int get_val() override
    {
        return 1;
    }

    void print() override
    {
        cout << "Derived::print\n";
    }
};

int main()
{
    Derived derived;
    return 0;
}
```

### 15. 为什么拷贝构造函数的参数类型必须是引用

- 从效率上来看，引用不需要执行拷贝操作，对于一些复杂类型效率更高。
- 如果拷贝构造函数的参数类型不是引用，那么在执行拷贝构造的时候，就会发生对象的拷贝，这就套娃了，陷入了无限递归的过程。（本来想通过拷贝构造函数拷贝一个新的对象，但在调用拷贝构造函数之前，你需要创建一个拷贝，嗯。。。）

### 16. C++实现多态有哪些方式

C++中的多态分为静态多态和动态多态，静态多态也叫编译器多态，动态多态也叫运行时多态。

编译器多态是通过函数重载和模板实现的，具体而言是在编译期，根据传入参数类型决定调用对应的函数，以及通过指定的模板参数来构造不同的模板类。

运行时多态是通过虚函数和继承实现的，具体而言是在基类中，定义虚函数，并在子类中重写父类的虚函数，这样在运行时，程序会根据具体的类型来调用不同的虚函数。

### 17. 解释一下虚函数和虚表

C++类中，对于一个非静态成员函数，增加virtual关键字，该函数就是虚函数。

而对于每一个包含虚函数的类，编译器都会为它创建一个虚函数表，虚函数表是一个指针数组，每个元素都对应一个虚函数地址，在运行时，通过索引来取得要运行的虚函数的地址，从而调用虚函数。此外，编译器还会创建一个虚指针，虚指针指向虚函数表的表头。

### 18. 虚函数和虚表示如何实现多态的

### 19. 解释一下虚函数和虚表
### 20. 解释一下多继承下类的内存布局？
### 21. 基类析构函数为什么要定义为虚函数？
### 22. C++如何计算一个类的大小，空类的大小是多少？

一个类的大小，除了考虑基本类型的大小以外，还需要考虑以下几个因素

- 是否包含虚函数，包含虚函数的类，包含一个虚函数指针；多继承下，会有多个虚函数指针。
- 静态成员不占类的大小
- 内存对齐原则

空类的大小为1

### 23. 简述类成员函数的重写、重载和隐藏的区别

- 重写（Override）

当一个派生类定义了一个与其基类中的函数同名、同参数列表、同返回类型的函数时，该函数被称为重写函数。在运行时，如果一个对象是派生类的实例，那么调用该函数时将调用派生类中的函数，而不是基类中的函数。

- 重载（Overload）

当一个类中有多个函数具有相同的名称，但是它们的参数列表不同，这些函数被称为重载函数。在运行时，编译器将根据函数调用中提供的参数类型和数量来确定要调用的函数。

- 隐藏（Hide）

当一个派生类定义了一个与其基类中的函数同名、但参数列表不同的函数时，该函数被称为隐藏函数。在运行时，如果一个对象是派生类的实例，那么调用该函数时将调用派生类中的函数，而不是基类中的函数。

### 24. 用C++设计一个不能被继承的类

- 使用`final`关键字

```cpp
class Base final {
public:
    // class implementation
};
```

- 将构造函数设置为private

```cpp
class Base {
private:
	Base(){}
    // class implementation
};
```

### 25. 如何定义一个只能在堆上（栈上）生成对象的类？
- 定义一个只能在堆上的方法：将析构函数设置为私有
  C++ 是静态绑定语言，编译器管理栈上对象的生命周期，编译器在为类对象分配栈空间时，会先检查类的析构函数的访问性。若析构函数不可访问，则不能在栈上创建对象。

- 定义一个只能在栈上的方法：将 new 和 delete 重载为私有。
  在堆上生成对象，使用 new 关键词操作，其过程分为两阶段：第一阶段，使用 new 在堆上寻找可用内存，分配给对象；第二阶段，调用构造函数生成对象。将 new 操作设置为私有，那么第一阶段就无法完成，就不能够在堆上生成对象。

### 26. 一个类默认有哪几个构造函数

- 默认构造函数
- 默认拷贝构造函数
- 默认移动构造函数
- 默认移动赋值函数
- 默认拷贝赋值函数
- 析构函数

### 27. 如何让一个类无法实例化

- 将构造函数设置为private
- 包含纯虚函数

### 28. 什么场景下使用继承方式，什么场景下使用组合？

- 继承： A继承B, A is B

- 继承： A包含B, A has B

### 29. delete this 合法吗？
- 必须保证 this 对象是通过 new（不是 new[]、不是 placement new、不是栈上、不是全局、不是其他对象成员）分配的
- 必须保证调用 delete this 的成员函数是最后一个调用 this 的成员函数
- 必须保证成员函数的 delete this  后面没有调用 this 了
- 必须保证 delete this 后没有人使用了



### 30. 哪些情况下会显示调用this指针

- 链式引用，成员函数返回自身（return *this）
- 重名变量，加上this避免冲突
- 一些数据结构的实现上，比如链表的实现，必须用到

```cpp
void insertAfter(Node* prev)
  {
    next = prev->next;
    prev->next = this;  // 这里必须用到 this。
  }
```

------



## STL

### 1.  介绍下STL
### 2.  解释下各种容器的特点和适用情况
### 3.  vector的实现原理
### 4.  vector中的reserve和resize的区别
### 5.  vector中的size和capacity的区别
### 6.  vector的元素类型可以是引用吗？
### 7.  vector迭代器失效的情况？
### 8.  vector 扩容为什么要以1. 5倍 或者2倍 扩容?
### 9.  vector的常用函数
### 10. list的实现原理
### 11. list的常用函数
### 12. deque的底层原理
### 13. 什么情况下用vector，什么情况下用list，什么情况下用deque
### 14. deque的常用函数
### 15. priority_queue的底层原理
### 16. priority_queue的常用函数
### 17. map 、set、multiset、multimap的底层原理
### 18. map 、set、multiset、multimap的特点
### 19. 为何map和set的插入删除效率比其他序列容器高，而且每次insert之后，以前保存的iterator不会失效？
### 20. 为何map和set不能像vector一样有个reserve函数来预分配数据?
### 21. map 、set、multiset、multimap的常用函数
### 22. unordered_map、unordered_set的底层原理

------



## Effictive C++

### 1.  解释一下左值引用和右值引用
### 2.  右值的应用场景
### 3.  介绍一下智能指针
### 4.  解释一下shared_ptr的内部实现
### 5.  说一下assert
### 6.  动态链接库和静态链接库的区别是什么？
### 7.  平时会用到function、bind、lambda吗，都什么场景下会用到？
### 8.  了解auto和decltype吗？
### 9.  了解移动语义和完美转发吗？
### 10 . unique_ptr如何转换所有权



------



## C++并发编程

### 1.  什么是并发编程？
### 2.  线程与进程的区别？
### 3.  多线程有几种实现方法，都是什么？
### 4.  C++ 中的同步和异步操作有什么区别？
### 5.  使用 C++ 实现锁的方法有哪些？
### 6.  使用多线程编程时如何避免数据竞争？
### 7.  C++ 11  中的 std::thread 如何使用？
### 8.  线程间通信的方法有哪些？
### 9.  如何使用 C++ 实现高效的线程池？
### 10. C++ 中的协程是什么？
### 11. 请说明 C++ 中的线程安全性。
### 12. 什么是原子操作？在 C++ 中如何使用？

### 13. 如何实现线程数据的同步，有哪些方式？



------



## 设计模型

### 1.  单例模式
### 2.  工厂模式
### 3.  适配器模式


## Reference

[1] [CPlusPlusThings](https://github.com/Light-City/CPlusPlusThings)

[2] https://github.com/huihut/interview

[3] https://github.com/rongweihe/CPPNotes
