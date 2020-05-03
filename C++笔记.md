在线IDE

> https://www.codechef.com/ide



概念

> argument 实际参数
>
> parameter 形式参数
>
> bit 比特
>
> byte 字节

```
4 bytes = 32 bits
```

> Initialization 初始化
>
> Assignment 赋值

```
int x;  // Initialization
x = 50; // Assignment
```

> declaration 声明
>
> definition 定义

```
int x;
```

> 取址操作
>
> 提领操作

```
int *p = &x;
```

> 引用 reference
>
> 指针 pointer

> 左值 lvalue (有内存地址的，就是左值，左值的内存地址是可以被取到的)
>
> 右值 rvalue (地址是处于不可用状态的，即使有一个地址，但也是不可操作的)

> 引用必须初始化一次，也只能被初始化一次

```
int x = 5;
int *p = &x;
int &y = x;   // y是x的引用
```

> 引用为了避免频繁的指针调用

> 引用和指针都必须针对左值，只有左值有地址

```
int x = 5; // x represents a block of memory which holds value 5

int *p = &x;  // Fetch x's address and store it to p, which belongs to type int

int &rx = x;  // rx refers to x
```

> 引用是从一而终的，引用是不能二次绑定的

> 数组 Array

```
index 索引/下标
offset 偏移量
```

```
int age[5]; 

> age == &age[0]
> age + 1 == &age[1]

指针算数
> age + n == &age[n] 
> *(age+n) == age[n]
```

> Idiom 习惯用法

```
int age[5] = {8, 17, 65, 52, 33}; // Modern C++ Brace init
```
指针算术（在数组里面）
```
int arr[5];
int *p = arr;
p = arr + 3; // Offset by size of 3 ints
```

指针的唯一一个字面量的值 nullptr

```
p = nullptr; // Only literal value that can assign to a pointer (Modern C++ only!)
p = 0;  // C++98 only!
```



> 分配 allocate
>
> 释放 free

动态内存分配

```
int *p = new int; // p owns the newly constructed int
...
delete p;

> new delete pair 必须成对出现
> 这个指针也叫原生指针，或者裸指针 raw pointer
```

> ownership 所有权

> 内存泄漏 memory leak / 内存所有权丢失 ownership lost

数组的内存分配和回收
```
int *pa = new int[100];
...
delete[] pa;
```

> 编译器管理的内存 -> 栈 stack
>
> 动态管理的内存 -> 堆 heap
>
> 静态内存
>
> 全局内存

现代C++

> 智能指针 Smart Pointer
>
> 也是STL的一部份

空悬指针

```
int *p = new int;
int *q = p;
*q = 10;
delete p;
cout << *q << endl; // Dangling pointer
```



关键字

> auto 让程序推断变量类型

```
auto x = 5;
```

> const 只读变量

```
const int i = 50;
```

```
const int *p = &x; // const before *: dereferenced location is readonly

int * const q = &x; // const after *: point itself is readonly

const int *const m = &x; // m即不能赋值，也不能指向另一个地址
```

```
const int &r = x; //r是一个只读的引用，不能再赋值
```

书藉

> 《Effective Modern C++》
>
> 《Effective C++》
>
> 《More Effective C++》