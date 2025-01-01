---
layout: post
title: "基础语法"
subtitle: "快速入门学习"
author: "Aoma"
header-style: text
hidden: true
tags:
  - Python
---

### 输出数据 `print()`
```Python
print("你好")
print(666)
print("hello")
```

### 注释
注释不会影响程序的执行，可以使代码更易于阅读和理解。Python 中的注释有**单行注释**和**多行注释**。
**单行注释： 以`#`开头**
``python
  #输出整数数据 123
  print(123)
```

**多行注释：由三个单引号`'''`或三个双引号`"""`包围的文本块**
```python
'''
第一行输出整数数据 123
第二行输出小数数据 3.14
第三行输出字符串数据 apple
'''
print(123)
print(3.14)
print("apple")
```

### 缩进
python最具特色的就是使用缩进来表示代码块，不需要使用大括号{}。
缩进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进空格数。
```python
if True:
    print ("True")
else:
    print ("False")
    print ("0")
    print ("假")
```
