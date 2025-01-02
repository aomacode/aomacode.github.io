---
layout: post
title: "先导 C++基础语法"
subtitle: "快速入门C++学习"
author: "Aoma"
header-style: text
hidden: true
tags:
  - C++基础
---

### C++程序结构

（1）基本程序
```c++
#include <iostream>
using namespace std;
// main() 是程序开始执行的地方
int main(){
   cout << "Hello World"; // 输出 Hello World
   return 0;
}
```

（2）解释
第1行  是C++语言定义了一些头文件，这些头文件包含了程序中必需的或有用的信息。
第2行  告诉编译器使用 std 命名空间。命名空间是 C++ 中一个相对新的概念。  
第3行  是一个单行注释。单行注释以 // 开头，在行末结束。
第4行  是主函数，程序从这里开始执行。 
第5行  会在屏幕上显示消息 "Hello World"。   
第6行  终止 main( )函数，并向调用进程返回值 0。


### 编译 & 执行 C++ 程序

C++程序是`先编译，再执行`
**编译：**是将`源代码`转换为计算机可以执行的`机器语言`代码的过程，也称为“翻译”或“转换”。编译器是将源代码转换为目标代码的程序。因为机器语言是计算机硬件可以直接执行的语言，所以编译器转换后的目标代码可以直接运行，而不需要解释执行。


### C++ 中的分号 & 语句块

（1）`分号`是语句结束符。也就是说，每个语句必须以分号结束。它表明一个逻辑实体的结束。

```c++
x = y;
y = y+1;
add(x, y);
```

（2）语句块是一组使用`大括号`括起来的按逻辑连接的语句。

```c++
{
   cout << "Hello World"; // 输出 Hello World
   return 0;
}
```



### 注释

程序的注释是解释性语句，这将提高源代码的可读性。所有的编程语言都允许某种形式的注释。

C++ 支持单行注释和多行注释。注释中的所有字符会被 C++ 编译器忽略。

注释只能放在代码的上方、右方、下方

单行注释：`//`  

多行注释：`/* ... \*/` 

```c++
#include <iostream>
using namespace std;
 
int main() {
  // 这是一个注释
  cout << "Hello World!"; //输出
  return 0;
  //结束程序  
}
```



```c++
#include <iostream>
using namespace std;
 
int main() {
    /* 
    第一行输出 Hello World!
    第二行输出 12345
    第三行输出 奥码
    */ 
    cout << "Hello World!";
    cout << 12345;
    cout << "奥码";
    return 0;
}
```

