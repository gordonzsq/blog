---
title: python基本语法
date: 2019-10-27 10:04:26
tags: python 基础笔记
categories: python
---

python 笔记，记录python不同于其它语言语法的一些内容和一些随笔
<!--more-->
### 安装

不同环境安装可参见[Python官方网站](https://www.python.org)

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


### 内置函数

官方链接[https://docs.python.org/zh-cn/3/library/functions.html](https://docs.python.org/zh-cn/3/library/functions.html)


### 分支
```Python
if i == 1:
    print('if 条件+冒号')
elif i > 1:
    print('elif 条件+冒号')
else:
    print('else+冒号')
```

### 循环
```Python
for x in range(2, 101, 2):
    sum += x
    
while True:
    if (i > 5):
        break
print('end 格式例子')
```

### 函数
```Python
def add(*args):
    print('*args定义多个参数， def + 函数名 + （参数名）+冒号')
    
def add(arg1, arg2=1):
    arg1 = arg2
    global a    #定义全局变量关键字global
    print('args can be default val')

```

需要说明的是，如果我们导入的模块除了定义函数之外还中有可以执行代码，那么Python解释器在导入这个模块时就会执行这些代码，事实上我们可能并不希望如此，因此如果我们在模块中编写了执行代码，最好是将这些执行代码放入如下所示的条件中，这样的话除非直接运行该模块，if条件下的这些代码是不会执行的，因为只有直接执行的模块的名字才是"__main__"
example.py
如下 在其他模块import examle的时候便不会执行fun
```Python

def fun():
    pass

# __name__是Python中一个隐含的变量它代表了模块的名字
# 只有被Python解释器直接执行的模块的名字才是__main__
if __name__ == '__main__':
    print('call fun()')
    fun()
```
