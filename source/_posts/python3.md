---
title: python 中的类
date: 2019-11-22 16:44:42
tags: python 基础笔记
categories: python
---

python中的类亦如c++中的类，也是对对象进行封装的一种数据类型。
<!--more-->
### 类的定义和使用

在Python中可以使用`class`关键字定义类，然后在类中通过之前学习过的函数来定义方法，这样就可以将对象的动态特征描述出来，代码如下所示。

```Python
#class Student(object):
class Student:

    # __init__是一个特殊方法用于在创建对象时进行初始化操作
    def __init__(self, name = 'null', age = 0):
        self.name = name
        self.age = age

    def study(self, course_name):
        print('%s正在学习%s.' % (self.name, course_name))

    def watch_movie(self):
        if self.age < 18:
            print('%s正在观看 熊出没.' % self.name)
        else:
            print('%s正在观看 海贼王.' % self.name)


def main():
    stu1 = Student('l', 8)
    stu2 = Student('z', 20)
    stu3 = Student()
    stu1.study('python')
    stu2.watch_movie()
    stu3.watch_movie()

if __name__ == '__main__':
    main()
	
```
### 私有成员及访问
python中使用双下划线__name方式定义私有（private）成员，且依然可以通过 _classname\__name方式访问私有成员。
```Python
class Test:
    def __init__(self, foo):
        self.__foo = foo

    def __bar(self):
        print(self.__foo)
        print('__bar')


def main():
    test = Test('hello')
    # AttributeError: 'Test' object has no attribute '__bar'
    # AttributeError: 'Test' object has no attribute '__foo'
    #test.__bar()
    #print(test.__foo)

    # 正常访问
    test._Test__bar()
    print(test._Test__foo)


if __name__ == "__main__":
    main()
```


### 使用__slots__
如果我们想要限制实例的属性，比如student实例只允许添加name和age属性。
```Python
class student(object):
	def __init__(self, name, age):
		self.name = name
		self.age = age
	__slots__ = ('name', 'age') # 用tuple定义允许绑定的属性名称
	
	def __str__(self):
		return 'Student object (name: %s)' % self.name
	__repr__=__str__
	...
```
使用__slots__要注意，__slots__定义的属性仅对当前类实例起作用，对继承的子类是不起作用的。
 __str__返回用户看到的字符串，__repr__返回开发者看到的字符串，当打印实例信息时调用该函数
```Python
 >>> s = Student('bb')
 >>> s                    #调用__repr__
 >>> print(Student('bb')) #调用__str__
```
 
### 使用__iter__，\__next__

如果一个类想被用于for ... in循环，类似list或tuple那样，就必须实现一个__iter__()方法，该方法返回一个迭代对象，然后，Python的for循环就会不断调用该迭代对象的__next__()方法拿到循环的下一个值，直到遇到StopIteration错误时退出循环。

我们以斐波那契数列为例，写一个Fib类，可以作用于for循环：
```
class Fib(object):
    def __init__(self):
        self.a, self.b = 0, 1 # 初始化两个计数器a，b

    def __iter__(self):
        return self # 实例本身就是迭代对象，故返回自己

    def __next__(self):
        self.a, self.b = self.b, self.a + self.b # 计算下一个值
        if self.a > 100000: # 退出循环的条件
            raise StopIteration()
        return self.a # 返回下一个值
     def __getitem__(self, n):#定义下标访问返回值
        a, b = 1, 2
        for x in range(n):
            a, b = b, a + b
        return a

```
```
for n in Fib():
	print(n)
f = Fib()
print(f[0]) # 需定义__getitem__
```
### 多重继承
一个类可以继承自多个父类
```
class child(class_p1, class_p2, class_p3):
    pass
```
这种设计通常称为MixIn， MixIn的目的就是给一个类增加多个功能，这样，在设计类的时候，我们优先考虑通过多重继承来组合多个MixIn的功能，而不是设计多层次的复杂的继承关系。
### type()
type()函数既可以返回一个对象的类型，又可以创建出新的类型，比如，我们可以通过type()函数创建出Hello类，而无需通过class Hello(object)...的定义：
```
Hello = type('Hello', (object,), dict(hello=fn)) # 创建Hello class
```
要创建一个class对象，type()函数依次传入3个参数：

1. class的名称；
2. 继承的父类集合，注意Python支持多重继承，如果只有一个父类，别忘了tuple的单元素写法；
3. class的方法名称与函数绑定，这里我们把函数fn绑定到方法名hello上。

使用type()可以让python动态创建类，配合metaclass，但这种使用方式个人觉得代码可读性不好，对这种使用方式了解能看懂即可，不建议较多使用。