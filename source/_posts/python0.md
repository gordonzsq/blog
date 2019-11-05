---
title: python 笔记 1
date: 2019-10-27 10:04:26
tags: python 基础笔记
categories: python
---

### 安装

不同环境安装可参见[Python官方网站](https://www.python.org)
<!--more-->

基于debin的linux发行版下
```Shell
sudo apt-get insatall python3

python3 -V
```
### 编辑环境

```Shell
sudo apt-get insatall ipython idle

```

图形IDE可安装 pycharm 参见：[pycharm官网](https://www.jetbrains.com)

### 运行和注释

```Shell
python3 hello.py

./hello.py
```
hello.py

    ```Python
    #!/usr/bin/python3

    import sys

    print(sys.version_info)
    print(sys.version)

    # ''' 
    red_balls = [x for x in range(1,34)]
    print(red_balls)
    print('\'\'\' 单引号 三个 注释多行')
    # '''

    print('# 空格 注释单行')
    print('hello word')

    ```


 
### 变量和类型
    
可以使用Python中内置的函数对变量类型进行转换。

- `int()`：将一个数值或字符串转换成整数，可以指定进制。
- `float()`：将一个字符串转换成浮点数。
- `str()`：将指定的对象转换成字符串形式，可以指定编码。
- `chr()`：将整数转换成该编码对应的字符串（一个字符）。
- `ord()`：将字符串（一个字符）转换成对应的编码（整数）。

%是占位符,后面接的数据类型同c的用法，但转义、占位均用的%
    
```Python
a=3
b=5
print('%d %% %d = %d' % (a, b, a % b))
print('%d ** %d = %d' % (a, b, a ** b))
```

### 运算符

Python支持多种运算符，下表大致按照优先级从高到低的顺序列出了所有的运算符，运算符的优先级指的是多个运算符同时出现时，先做什么运算然后再做什么运算。除了我们之前已经用过的赋值运算符和算术运算符，我们稍后会陆续讲到其他运算符的使用。

| 运算符                                                       | 描述                           |
| --------------------------------------------------- | ------------------------------ |
| `[]` `[:]`                                                  | 下标，切片                     |
| `**`                                                         | 指数                           |
| `~` `+` `-`                                             | 按位取反, 正负号               |
| `*` `/` `%` `//`                                        | 乘，除，模，整除               |
| `+` `-`                                                      | 加，减                         |
| `>>` `<<`                                               | 右移，左移                     |
| `&`                                                          | 按位与                         |
| `^` `\|`                                                      | 按位异或，按位或               |
| `<=` `<` `>` `>=`                                 | 小于等于，小于，大于，大于等于 |
| `==` `!=`                                                    | 等于，不等于                   |
| `is`  `is not`                                               | 身份运算符                     |
| `in` `not in`                                                | 成员运算符                     |
| `not` `or` `and`                                             | 逻辑运算符                     |
| `=` `+=` `-=` `*=` `/=` `%=` `//=` `**=` `&=` `|=` `^=` `>>=` `<<=` | （复合）赋值运算符             |



