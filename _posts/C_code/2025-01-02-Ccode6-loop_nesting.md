---
layout: post
title: "第六章 循环嵌套"
subtitle: "循环嵌套 | 嵌套结构 | break语句 | continue语句 | goto语句 "
author: "Aoma"
header-style: text
hidden: true
tags:
  - C++基础
---



### 循环嵌套

**格式之一：**

```python
for (初始化1; 判断条件1; 变化值1){
    for (初始化2; 判断条件2; 变化值2){
    	循环主体2
	}
    循环主体1
}
```

**解释：**

1. 循环嵌套的格式千变万化，其实只需记住一点，就是任何循环结构都可以在里面放置任何循环结构
2. 以两层循环为例，他的执行逻辑是先判断执行最外层循环1次后，直到第二层的所有循环结束，接着往回到外层后，判断最外层是否可以循环，可以，又执行所有第二层循环，依次反复执行，直到所有循环结束
3. 循环次数：以两层循环为例：第一层次数 * 第二层次数

**样例：**

```c++
#include <iostream>
using namespace std;
int main() {
    
    for (int x=1; x<=5; x++){
        for (int y=1; y<=3; y++){
            cout << y << endl;
        }
        cout << endl;
    }
        
    return 0;
}
```

程序一共执行15次。



**总结：**

循环嵌套要掌握好非常困难，只有不断的刷题才能快速掌握。



### 嵌套结构

嵌套结构一般指分支嵌套与循环嵌套，但实际上只要是将任何语句放置到任何大括号中，都属于嵌套。

**嵌套结构1**

```c++
#include <iostream>
using namespace std;
int main() {
	if (3>2){
		cout << "大于" << endl;
	}
        
    return 0;
}
```

**嵌套结构2**

```c++
#include <iostream>
using namespace std;
int main() {
	for (int k=1; k<=5; k++){
        if (k>3){
            cout << k << endl;
        }
	}
        
    return 0;
}
```

**嵌套结构3**

```c++
#include <iostream>
using namespace std;
int main() {
	if (3>2){
        for (int k=1; k<=3; k++){
			cout << k << endl;	
        }
	}
        
    return 0;
}
```



**注意：**

1. 嵌套结构千变万化，理论上可以无限嵌套。
2. 目前常见的就是循环嵌套循环，分支嵌套分支，循环嵌套分支，分支嵌套循环



### break语句

**用法：**

1. 当 **break** 语句出现在一个循环内时，循环会立即终止，且程序流将继续执行紧接着循环的下一条语句。
2. 它可用于终止 **switch** 语句中的一个 case（目前不常用，主要用于循环）

**注意：**

1. 如果使用的是嵌套循环（即一个循环内嵌套另一个循环），break 语句会停止执行最内层的循环，然后开始执行该块之后的下一行代码。
2. 通常搭配`if语句`使用。

**样例1：**

```c++
#include <iostream>
using namespace std;
int main() {
    
    for (int k=1; k<=5; k++){
        cout << k << endl;
        if (k==3){
            break;
        }
    }
        
    return 0;
}
```

程序只会输出1 2 3，因为到达3后，break语句执行，退出循环。

**样例2：**

```c++
#include <iostream>
using namespace std;
int main() {
    
    for (int k=1; k<=5; k++){
        for (int h=1; h<=3; h++){
            cout << h << endl;
            if (h==1){
                break;
            }
        }
    }
        
    return 0;
}
```

程序只会执行5次，且输出1 1 1 1 1 ，因为内层循环每次执行到1时，break语句会执行，退出内层循环。



### continue语句

**用法：**

1. **continue** 会跳过当前循环中的代码，强迫开始下一次循环
2. 对于 **for** 循环，**continue**语句会回到执行条件测试和循环变化量部分。对于 **while** *和* **do...while** 循环，continue语句会回到条件测试上。

**注意：**

1. 仅仅是结束本次循环，且时该语句后的所有语句，接着回到下一次循环。
2. 通常搭配`if语句`使用。

**样例1：**

```c++
#include <iostream>
using namespace std;
int main() {
    
    for (int k=1; k<=5; k++){
        if (k==3){
            continue;
        }
        cout << k << endl;
    }
        
    return 0;
}
```

程序会输出1 2 4 5，因为第3这一次遇到continue，这一轮循环后面的语句不执行，直接跳到第4次。



### goto语句

**goto** 语句允许把控制无条件转移到同一函数内的被标记的语句。
**注意：** 在任何编程语言中，都不建议使用 goto 语句。因为它使得程序的控制流难以跟踪，使程序难以理解和难以修改。任何使用 goto 语句的程序可以改写成不需要使用 goto 语句的写法。
所以该语句了解即可。

**样例：**

```c++
#include <iostream>
using namespace std;
 
int main ()
{
   // 局部变量声明
   int a = 10;

   // do 循环执行
   LOOP:do
   {
       if( a == 15)
       {
          // 跳过迭代
          a = a + 1;
          goto LOOP;
       }
       cout << a << endl;
       a = a + 1;
   }while( a < 20 );
 
   return 0;
}
```



