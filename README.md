# CPlusplus-Interview

[TOC]

------



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


### 5.  说一下C++代码文件到可执行程度，经历了哪些过程？
- 预处理（Preprocessing）：在编译前，对代码中的预处理指令进行处理，例如宏定义、条件编译等。这一步会将宏定义做字符串替换，以及include指令替换为实际的头文件内容，处理后的代码会保存在一个临时文件中，通常以.i或者.ii作为文件扩展名。
> // 比如现在有一个hello.c的代码文件
> gcc -E hello.c -o hello.i
- **编译（Compiling）**：将预处理后的代码编译成汇编代码，这个过程包括词法分析、语法分析、语义分析和生成中间代码等步骤，通常以.s作为文件扩展名。
> gcc -S hello.i -o hello.s
- **汇编（Assembling）**：将汇编代码转换成机器语言指令，生成目标文件（Object File），通常以.o或.obj作为文件扩展名。
> gcc -c hello.s -o hello.o
- **链接（Linking）**：将目标文件和系统库文件链接起来，生成可执行文件，通常以.exe或.out作为文件扩展名。在链接过程中，链接器将解析目标文件中的符号（函数、变量等），并将其与系统库文件中的符号进行匹配，生成最终的可执行文件。
> gcc hello.o -o hello
>
> 
在上述过程中，编译器和链接器是最重要的工具。编译器将C++代码转换成汇编代码，而链接器则将目标文件和库文件链接成可执行文件。
// 也可以一步到位，直接用一个指令得到可执行
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
- 将整数位化 1,  即1101  =  1. 101  *  2  ^ 1
- 按顺序存储符号位（这里是正数，符号位为 1） ，指数部分（这里为 1） ，小数部分（这里为101） 

下面是float浮点数的存储方式，一共有 23 位可供小数位存储

![img](https://cdn.nlark.com/yuque/0/2023/gif/2625673/1680331635283-19d177c7-29bf-4e1c-a9c2-4ec1aba3afec.gif)

下面是double浮点数的存储方式，一共有 52 位可供小数位存储

![img](https://cdn.nlark.com/yuque/0/2023/gif/2625673/1680331667134-54bb1d28-c10e-4f9a-b318-2db455a98895.gif)


### 9.  C语言struct和C++struct区别
- C语言中，struct只是不同数据的集合，不能包含函数，以及所有面向对象的概念。
- 在C++中，struct基本上和class类似，只是内部成员默认为public，class中内部成员默认为private，其他行为相同。


### 10 . `extern`有什么作用，`extern C`有什么作用
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

### 11 . C中int fun() 和 int fun(void)的区别?
int func()可以接收任意类型和任意数量的参数，而int fun(void) 则不接收任何参数。

### 12 . const int*p 和 int const *p的区别
- const int *p 表示指针指向的值不可被修改

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

  

- int const *p 表示指针的指向不可被修改

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

  

### 13 . 引用和指针的区别
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

### 14 . 如何避免“野指针”
野指针指的时指向无效或者未知地址的指针，直接访问可能导致意外的不可预知的结果。
- 创建指针时，尽量做初始化，如果不确定指向什么位置，将其初始化成nullptr。
- 在访问指针指向的资源之前，判断指针是否为nullptr。
- 释放指针资源之后，将指针置为nullptr。
- 使用智能指针，它可以自动的帮助我们管理内存。
- 尽量使用引用来代替指针。

### 15 . 说一下数组名和指针的区别

数组名和指针，在很多地方具有相似之处，比如可以使用解引用符号，但它们本质上时不同的，主要区别如下
- 数组名本质上并不是一个指针，但是它具有和指针类似的行为，可以理解为一个指向不可变的指针类型（type *const p），无法进行赋值操作。
- 数组名占用的内存大小是整个数组的大小，而指针的大小则是4个 字节或者8个 字节。
- 数组名在初始化时，就会分配数组大小的空间，而指针初始化时，只会创建指针大小的空间。

### 16 . 简述strcpy、sprintf与memcpy的区别
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



- sprintf是一个格式化输出函数，用于将多个变量格式化为一个字符串，和strcpy类似，同样是当遇到\0结 束，它和strcpy一样，同样需要注意缓冲区溢出的问题。因此实际使用中，更推荐使用snprintf，代替sprintf
  ```c++
  char str1[ ] = "Hello\0  Geeks!";
  char str2[ ] = "GeeksforGeeks";
  char str[10 0] ;
  sprintf(str, "x=%s, y=%s", str1,  str2) ;
  // 输出：x=Hello, y=GeeksforGeeks 
  cout << str;
  ```

- memcpy
  memcpy可以用于任意类型数据的复制，使用memcpy需要指定复制的字节数，当复制字符串时，它不会在字符串结尾添加\0， 需要手动添加

  ```c++
  char str1[ 10 0]  = "Hello Cplusplus!";
  char str2[ 10 ];
  
  memcpy(str2,  str1,  9) ;
  
  // 手动添加 \0
  str2[ 9]  = '\0' ;
  
  cout << str2  << endl;;
  ```

  

### 17 . 解释一下mutable关键字
mutable允许在常量函数中修改变量。

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





### 18 . 参数传递
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



### 19 . new 和malloc的区别
- new是操作符，而malloc是函数
- new 返回的是一个对象指针，而malloc返回的是一个void类型的指针
- new 不需要指定大小，而malloc必须指定分配的内存大小
- new一个对象失败会抛出异常，而malloc失败会返回null_ptr
- new的内部实现调用了malloc函数。
- new 操作符无法被重载，而malloc函数可以被重载

### 20 . delete 和free的区别
- delete是操作符，而free是函数。
- delete的内部实现调用了free函数。
- delete 操作符无法被重载，而free函数可以被重载

### 21 . new和delete操作符的实现原理

new操作符
- 使用operator new函数，在内存中（heap上）创建一个足够大的空间。
- 将创建的空间地址赋给this指针。
- 调用类的构造函数，进行成员变量的初始化，如果对象是一个数组，那么new运算符会为数组中的每个元素调用构造函数。

delete 操作符
- 调用类的析构函数。
- 调用operator delete函数，释放内存空间。

### 22 . free和malloc的实现原理
malloc的实现原理：
- malloc函数会在堆区中申请一段连续的内存空间，返回该空间的首地址。
- malloc函数的原型为：void* malloc(size_t size)。
- malloc函数需要指定所需内存大小，如果内存分配成功，就会返回所分配的内存的起始地址。如果内存分配失败，返回null_ptr。
free的实现原理：
- free函数用于释放由malloc分配的内存空间，使得该空间可以被重新利用。
- free函数的原型为：void free(void* ptr)。
- free函数需要用户传入一个指向先前由malloc返回的指针，以告诉系统要释放的内存地址。如果该指针是null_ptr，则不会执行任何操作。

### 23 . free是如何知道释放内存的大小的
free用于释放由malloc分配的内存，其实在malloc分配内存的时候，除了分配指定大小的内存外，还会内存块的头部分配一小块内存（Header）用于保存内存块信息（包括分配内存的大小，内存块的边界，是否被占用等信息），free可以根据header中内存块信息，来决定释放多大的内存。因此，实际释放的内存是指针实际占用的空间加上Header块的空间。

### 24 . malloc申请的存储空间能用delete释放吗？

不可以，可能会出现未定义的行为，malloc需要和free配套使用。

当使用malloc为一个复杂类型的对象分配内存时，由于malloc并不会调用类的构造函数，也就是对象的成员变量不会进行初始化等操作。
而delete操作符，首先会调用对象的析构函数，回收类成员变量，由于此时成员变量未被初始化，因此很可能导致不可预知的结果。
所以，malloc分配的内存，应该使用free来回收。同理，new创建的对象，也不能通过free来释放。

### 25 . malloc，calloc以及realloc之间的区别？
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

### 26 . 说一下c/c++的内存分配
c++中内存的分区包括5个 部分
- 栈：由编译器自动分配和释放，存储局部变量和函数调用信息等，空间有限。
- 堆：由程序员手动分配和释放，存储动态分配的内存，空间只受限于物理内存。
- 静态存储区：用于存储全局变量、静态变量等，程序运行期间一直存在，由系统自动分配和释放。
- 常量存储区：用于存储常量，程序运行期间一直存在，不允许修改。
- 程序代码区：用于存储程序的指令代码，程序运行期间一直存在，不允许修改。


### 27 . 为什么static成员变量不能在类内做初始化，加了const为什么就可以了？
static成员变量，在类的对象没有被构建之前就已经存在，且每个对象共享一份。
如果static变量在类内初始化，就意味着，每次创建类的实例，都会做一次初始化，分配一次内存。


### 28 . static变量和全局变量的区别
static变量和全局变量都存储在静态存储区，最主要的区别时使用范围，static变量只能在当前文件中被访问，而全局变量可以在其他文件中被访问。

### 29 . static 变量的特点
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

### 30 . static函数的特点
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

### 31 . const和宏定义的区别？
- const变量具有类型，在编译阶段会做类型安全检查，而宏定义常量没有类型
- const变量存储在静态代码区，宏定义不分配内存，不占内存空间
- 宏定义在预处理阶段处理（字符串替换），而const变量在编译阶段处理（定义初始化）。
- 宏定义可以通过undef取消定义

### 32 . typedef和define有什么区别？
- 作用域：typedef定义的类型别名具有作用域，在其作用域内可以被使用；而define定义的常量没有作用域的概念，展开后的代码在整个文件中都是生效的。
- 类型检查：typedef定义的类型别名具有类型信息，编译器可以对其进行类型检查，避免类型错误；而define定义的常量只是简单的文本替换，不会进行类型检查。
- 扩展性：typedef可以为结构体、联合体、函数指针等复杂类型定义类型别名，提高了可读性和可维护性；而define只能定义简单的常量，不能使用复杂的类型。

### 33 . typedef和using的区别？
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



### 34 . 说一下在函数中不同位置使用const的情况，并解释不同位置下，const的作用？
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

  

### 35 . 什么内联函数，说一下inline的优缺点，它和宏定义有什么区别？
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

### 36 . struct和class的区别
- struct 中的成员默认都是public的，而class中的成员默认都是private的
- struct 默认都是public继承的，而class默认都是private继承

### 37 . explicit 的作用，为什么要用它
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

### 38 . 说一下友元的应用场景，它会有什么问题
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

### 39 . 解释一下C++中的类型转换
- **dynamic_cast** 
  dynamic_cast 是专门用于沿继承层次关系的类型装换。
  ○ 使用dynamic_cast 进行指针或者引用类型转换，指针指向的对象必须具有继承关系，并且必须是多态类型（类内部包含虚函数）
  ○ dynamic_cast 转换会做运行时类型检查（Run-Time Type Information：RTTI ），有一定的性能开销（关闭运行时类型检查后，dynamic_cast会报错）

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



- **static_cast**
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



- **const_cast**
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

- **reinterpret_cast**
  ○ 用户对不相关类型指针或引用的转换，可以对任意类型的指针和引用做类型转换，它最灵活的一种类型转换方式。
  ○ 对于static_cast操作符,如果需要截断，补齐或者指针偏移编译器都会自动完成.注意这一点,是和 reinterpret_cast 的一个根本区别.
  ○ 简单来说，就是reinterpret_cast，只是简单改变指针的类型，至于指针指向的内容，不会有任何变化。（就像是本来是一个红色的盒子，然后，把红色的盒子换成了绿色，盒子里面的东西还是一模一样）

下面的代码可以实现和b = reinterpret_cast<type1  *>(a)同样的目的，只不过reinterpret_cast不会操作内存，只改变编译器对数据的解释方式（用reinterpret_cast将一个int型的指针转换为float类型的指针后，然而其实内存中的内存没有改变，只是告诉编译器，这块内存存储的是float，不再是int型，然后，编译器会把这块内存当做float类型来解释，得到的结果自然是无意义的值，因为两种类型在内存中的布局不同）。	

```c++
type *a;

type1  *b;

memcpy((void *)b, (void *)a, sizeof(type));
```



### 40 . 介绍一下RAII
 RAII（Resource Acquisition Is Initialization）是一种利用对象生命周期来控制程序资源（如内存、文件句柄、网络连接、互斥量等等）的简单技术。它通过类的构造函数和析构函数来实现对资源在对象整个生命周期内的管理。即构造函数中申请资源，析构函数中释放资源。

### 41 . const常量在C和C++中有什么区别
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

  

### 42 . 说一下C++模板的偏特化与全特化它们的应用场景
https://zhuanlan.zhihu.com/p/34 64 00 61 6

### 43 . 解释一下C++中的内存对齐？
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




### 44 . 解释一下volatile关键字
在 C++ 中，volatile 是一个关键字，它用于修饰变量，告诉编译器该变量的值可能会在程序运行期间发生变化。
使用 volatile 修饰的变量，编译器不能对其进行优化，必须按照程序代码的顺序读取和写入该变量的值，以保证程序的正确性。
具体来说，使用 volatile 关键字修饰的变量，其在程序中的读取和写入操作不会被编译器优化为寄存器操作或常量表达式。这是因为编译器会认为这个变量的值可能会在程序运行期间被其它线程或硬件设备修改，因此需要每次从内存中读取该变量的最新值，以避免出现未定义的行为。

volatile 变量通常用于以下场景：
- 多线程访问共享变量时，需要使用 volatile 关键字保证变量的值能被正确地读取和修改。
- 在嵌入式系统或硬件驱动开发中，经常需要使用 volatile 关键字来声明硬件寄存器变量，以保证每次访问该寄存器都能反映其最新状态。

### 45 . 浅拷贝和深拷贝有什么区别？
- 浅拷贝只拷贝对象的引用。
- 深拷贝则是真正的完全复制，它会递归的复制对象的所有内容。

### 46 . sizeof和strlen有什么区别？
- sizeof用于计算对象在内存中占用的字节数。
- 而strlen用来计算以\0结 尾的字符串的长度。

### 47 . 说一下类的初始化列表，为什么说它可以提高效率?
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

### 48 . 内存泄漏的场景一般有哪些情况
- 程序执行过程中，出现异常，但堆上分配的内存未得到释放。
- new和delete未成对使用
- 基类的析构函数未定义为虚函数，导致子类的析构函数未被调用。
- 指针赋值错误，导致原有指向的内容无法被释放。
- 循环引用，导致对象无法被释放，从而导致内存泄漏。

### 49 . 解释一下constexpr关键字？

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



### 50 . const和constexpr有什么区别？

- 修饰函数时，两者的作用不同，const既可以用在修饰函数参数也可以修饰函数返回值，用来限定函数参数或者返回值只读，而constexpr修饰函数则表示，希望该函数被当做常量表达式函数，在编译期就可以确定函数返回的值。

- 修饰变量，const常量不一定是编译期确定，而constexpr常量一定是在编译期确定的。



### 51 . 什么是union，它和类有什么区别？



------



## C++面向对象



### 1.  构造函数能否为虚函数
不能

### 2.  构造函数调用虚函数会发生什么
### 3.  为什么内联函数，构造函数，静态成员函数不能为virtual函数？
### 4.  C++虚函数表和虚函数指针机制
### 5.  构造函数和析构函数能否重载？
### 6.  复合对象和继承对象，构造函数和析构函数的调用顺序？
### 7.  C++中类成员的访问权限
### 8.  说一下类的访问权限
### 9.  解释一下this指针
### 10 . override和overload的区别
### 11 . 面向对象的3大 特性
### 12 . 虚函数和纯虚函数
### 13 . 私有继承的作用是什么？
### 14 . 拷贝构造函数的参数类型必须是引用
### 15 . 什么是多态
### 16 . C++如何实现多态
### 17 . 解释一下虚函数和虚表
### 18 . 解释一下多继承下类的内存布局？
### 19 . 基类析构函数为什么要定义为虚函数？
### 20 . C++如何计算一个类的大小，空类的大小是多少？
### 21 . 简述类成员函数的重写、重载和隐藏的区别
### 22 . 用C++设计一个不能被继承的类
### 23 . 如何定义一个只能在堆上（栈上）生成对象的类？
  a. 定义一个只能在堆上的方法：将析构函数设置为私有
原因：C++ 是静态绑定语言，编译器管理栈上对象的生命周期，编译器在为类对象分配栈空间时，会先检查类的析构函数的访问性。若析构函数不可访问，则不能在栈上创建对象。
  b.  定义一个只能在栈上的方法：将 new 和 delete 重载为私有。
原因：在堆上生成对象，使用 new 关键词操作，其过程分为两阶段：第一阶段，使用 new 在堆上寻找可用内存，分配给对象；第二阶段，调用构造函数生成对象。将 new 操作设置为私有，那么第一阶段就无法完成，就不能够在堆上生成对象。


### 24 . 一个类默认有哪几个构造函数
### 25 . 如何让一个类无法实例化，解释一下这样做有什么应用
### 26 . 什么场景下使用继承方式，什么场景下使用组合？
### 27 . enum 和 enum class有什么区别？
### 28 . delete this 合法吗？
合法，但：
- 必须保证 this 对象是通过 new（不是 new[]、不是 placement new、不是栈上、不是全局、不是其他对象成员）分配的
- 必须保证调用 delete this 的成员函数是最后一个调用 this 的成员函数
- 必须保证成员函数的 delete this  后面没有调用 this 了
- 必须保证 delete this 后没有人使用了

### 29 . 哪些情况下会显示调用this指针



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
### 10 . list的实现原理
### 11 . list的常用函数
### 12 . deque的底层原理
### 13 . 什么情况下用vector，什么情况下用list，什么情况下用deque
### 14 . deque的常用函数
### 15 . priority_queue的底层原理
### 16 . priority_queue的常用函数
### 17 . map 、set、multiset、multimap的底层原理
### 18 . map 、set、multiset、multimap的特点
### 19 . 为何map和set的插入删除效率比其他序列容器高，而且每次insert之后，以前保存的iterator不会失效？
### 20 . 为何map和set不能像vector一样有个reserve函数来预分配数据?
### 21 . map 、set、multiset、multimap的常用函数
### 22 . unordered_map、unordered_set的底层原理

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
### 10 . C++ 中的协程是什么？
### 11 . 请说明 C++ 中的线程安全性。
### 12 . 什么是原子操作？在 C++ 中如何使用？

### 13. 如何实现线程数据的同步，有哪些方式？



------



## 设计模型

### 1.  单例模式
### 2.  工厂模式
### 3.  适配器模式
### 4.  
