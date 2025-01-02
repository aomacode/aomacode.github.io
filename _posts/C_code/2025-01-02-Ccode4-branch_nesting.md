---
layout: post
title: "第四章 分支嵌套"
subtitle: "条件运算符 | 逻辑运算符 | 分支嵌套 | sizeof"
author: "Aoma"
header-style: text
hidden: true
tags:
  - C++基础
---



### 条件运算符 `?:`

三目运算符。它是双分支选择结构的另一种简写。还可以直接赋值。

**格式：**

```python
表达式 ? 语句1 : 语句2
```

**样例1：**

```c++
//双分支结构样例
if (2>3){
	cout << "yes" << endl;
}
else {
	cout << "no" << endl;
}

//条件运算符简写
2>3 ? cout << "yes" << endl : cout << "no" << endl;

```



**样例2：** 常用于此概况

```c++
//双分支结构样例:两数比大小
int a=2, b=3, maxc=0;
if (a > b){
	maxc = a;
}
else {
	maxc = b;
}


//条件运算符简写
maxc = a>b ? a endl : b;
```

**注意：** 此方法可以先了解，后续再返回来学习，理解起来就非常容易。



### 分支嵌套示例

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3;
    if (a == 2){
    	if (b > 2){
    		cout << "a为2，b大于2" << endl;
    	}
    	else{
    		cout << "no" << endl;
    	}
	}
    return 0;
}
```

**解释：**

先判断表达式a==2为真，接着判断表达式b>2，代码最终执行输出：*a为2，b大于2*



### 逻辑运算符

逻辑运算符中&&与||主要用于连接比较运算符，它常常用于拆分分支嵌套结构，是代码更加简洁。
假设`整型变量a`的值为1，变量 b 的值为 0

| 运算符 | 描述                                                         | 实例               |
| :----- | :----------------------------------------------------------- | :----------------- |
| &&     | 称为逻辑与运算符。如果两个操作数都 true，则条件为 true。     | (a && b) 为 false  |
| \|\|   | 称为逻辑或运算符。如果两个操作数中有任意一个 true，则条件为 true。 | (a \|\| b) 为 true |

```c++
#include <iostream>
using namespace std;
int main()
{
    int a = 1;
    int b = 0;
    
    cout << a && b << endl ;
    cout << a || b << endl ;
    cout << !a << endl ;
    cout << !(a && b) << endl ;

    return 0;
}
```



### 分支嵌套

**格式之一:**

```c++
if (表达式1) {
    if (表达式2){
        语句1
    }
}
else {
    语句2
    if (表达式3){
        语句3
    }
}
```

**解释：**

（1）分支嵌套的格式千变万化，其实只需记住一点，就是任何分支结构都可以在里面放置任何分支结构
（2）他的执行逻辑是先判断最外层表达式，依次往里判断，直到结束

**样例：**

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3, c=5;
    if (a > b){
        if (a > c)
    		cout << "a最大" << endl;
    }
    return 0;
}
```

**使用逻辑运算符简化：**

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3, c=5;
    if (a > b && a > c){
        cout << "a最大" << endl;
    }
    return 0;
}
```

**注意：** 根据实际情况，一般可以使用逻辑运算符进行简化，但较为复杂的情况依然要使用分支嵌套。



### 查询字节 `sizeof()`

用于判断数据类型的字节大小。就是第一章所展现的不同数据类型的字节大小不同，通常在考级中会考察，而在较为复杂的代码中，你需要直到数据的字节大小，从而才能更合理的编写程序。

```c++
#include <iostream>
using namespace std;
int main() {
    int a=146;
    double b = 2.45;
    
    cout << sizeof(a) << endl;
    cout << sizeof(b) << endl;
    cout << sizeof('2') << endl;
    cout << sizeof("123") << endl;

    return 0;
}
```
