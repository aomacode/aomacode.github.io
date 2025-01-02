---
layout: post
title: "第三章 选择结构"
subtitle: "条件运算符 | 单分支 | 双分支 | 多分支 | switch"
author: "Aoma"
header-style: text
hidden: true
tags:
  - C++基础

---



  ### if 实现选择结构示例

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3;
    if (a < b){
    	cout << "小于" << endl;
    }
    else{
    	cout << "大于" << endl;
    }

    return 0;
}
```

**解释：**

如果判断表达式 `a<b`  为`true` ，输出`大于`；否则就输出`小于`


### 关系运算符

关系运算符实现条件判断，专门用于选择结构。
假设`整型变量a`的值为 5，变量 b 的值为 3

| 运算符 | 描述                                                         | 实例             |
| :----- | :----------------------------------------------------------- | :--------------- |
| ==     | 检查两个操作数的值是否相等，如果相等则条件为真。             | (a == b) 为false |
| !=     | 检查两个操作数的值是否相等，如果不相等则条件为真。           | (a != b) 为true  |
| >      | 检查左操作数的值是否大于右操作数的值，如果是则条件为真。     | (a > b) false    |
| <      | 检查左操作数的值是否小于右操作数的值，如果是则条件为真。     | (a < b) 为true   |
| >=     | 检查左操作数的值是否大于或等于右操作数的值，如果是则条件为真。 | (a >= b) false   |
| <=     | 检查左操作数的值是否小于或等于右操作数的值，如果是则条件为真。 | (a <= b) true    |

```c++
#include <iostream>
using namespace std;
int main()
{
    int a = 5;
    int b = 3;
    
    cout << a == b << endl ;
    cout << a != b << endl ;
    cout << a > b << endl ;
    cout << a < b << endl ;
    cout << a >= b << endl ;
    cout << a <= b << endl ;
    
    return 0;
}
```



### 单分支语句

用于实现一个判断表达式的真假对应的一种结果

**格式:**

```c++
if (表达式) {
    语句1
}
```

**解释：**

（1）判断表达式必须加上括号，通常用条件运算符实现，但也可以直接输入值。
（2）后面的语句需要用大括号括起来，表现为判断真假后需要执行的内容。
（3）大括号中的语句理论上可以有无限个。
（4）判断表达式为真，执行语句1。



**样例1：** 条件表达式实现

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3;
    if (a < b){
    	cout << "小于" << endl;
    }
    return 0;
}
```

**样例2：**直接输入值

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2;
    if (a){
    	cout << "小于" << endl;
    }
    return 0;
}
```

**样例2解释：**

（1）在C++中，所有if语句的判断表达式都可以直接输入值
（2）该值一共有两种：`0、false` 与 `其他任何值`

`0、false` 表示假
`其他任何值` 表示真

所以样例2输出小于。



**单分支缺陷：**

一种条件只有一种结果，具有局限性。
因此下面这种情况就要多写一次判断，程序要多判断一次。

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3;
    if (a < b){
    	cout << "小于" << endl;
    }
    if (a > b){
        cout << "大于" << endl;
    }
    return 0;
}
```

**单分支优点:**

虽然写的判断多，但是条理分明，特别适合入门编程人员使用。



### 双分支语句

**格式:**

```c++
if (表达式) {
    语句1
}
else {
    语句2
}
```

**解释：**

（1）一个条件控制两种执行结果
（2）判断表达式为`真`执行语句1，为`假`执行语句2

**样例：**

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2, b=3;
    if (a < b){
    	cout << "小于" << endl;
    }
    else {
        cout << "大于" << endl;
    }
    return 0;
}
```



**双分支缺陷：**

（1）依然是只能判断一种条件，只是多了一个选择情况。
（2）else后的结果太局限，也就是不是第一种情况就一定要是第二种。
（3）但很多时候不是确定，还有很多情况需要去判断

**双分支优点：**

适合一种情况判断，执行两种结果的情况，例如：不是...就是...



### 多分支语句

**格式:**

```c++
if (表达式1) {
    语句1
}
else if (表达式2){
    语句2
}
else if (表达式3){
    语句3
}
else {
    语句4
}    
```

**解释：**

（1）多个条件控制多种结果，理论上else if可以无限个。
（2）执行逻辑是，从上往下执行，如果表达式1为真，直接执行语句1，后面的所有判断包括所有语句都直接忽略，否则接着判断表达式2，以此类推，都不满足才会执行else的语句。
（3）可以理解为多个判断但总的只会执行一种结果。

**样例：**

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2;
    if (a == 1){
    	cout << "a为1" << endl;
    }
    else if (a == 2){
        cout << "a为2" << endl;
    }
    else if (a == 3){
        cout << "a为3" << endl;
    }
    esle {
        cout << "其他" << endl;
    }
    return 0;
}
```

执行输出a为2



**多分支缺陷：**

（1）判断逻辑较为复杂，不适合新手。
（2）else执行语句不可控，难以合理运用。

**多分支优点：**

简洁，判断条件多，判断快速。



### switch多分支

**格式:**

```c++
switch (表达式) {
    case 常量1: 
        语句1
        break
    case 常量1: 
        语句2
        break
    case 常量1: 
        语句3
        break
	default:
        语句4 
}
```

**解释：**

（1）一个表达式，实现不同结果
（2）break的作用是结束整个判断
（3）default 可以理解为else

**样例：**

```c++
#include <iostream>
using namespace std;
int main() {
    int a=2;
    switch (a){
        case 1:
            cout << "a是1" << endl;
            break;
      	case 2:
            cout << "a是2" << endl;
            break;
        case 3:
            cout << "a是3" << endl;
            break;
        case 4:
            cout << "a是4" << endl;
            break;
        default:
            cout << "其他" << endl;
    }
    return 0;
}
```

执行输出a是2

**switch多分支缺陷：**

使用局限，要一些特定的情况才好使用。

**switch多分支优点：**

合适的情况用来判断，会非常省心。


**注意：**switch语句现在很少人用了，因为它的使用条件具有特殊性。


