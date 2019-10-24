# Python基础知识
## 1.数据类型
```python
"""
数据类型：
    Python是一个弱类型语言：可以根据使用时的要求，自动变更类型
        1.数字类型（Number）：整形（int）、浮点数(float)、复数。可以处理任意大小的数字
        2.字符串（String）：字符串就是一系列字符。在Python中，用引号括起的都是字符串，其中的引号可以是单引号，也可以是双引号
        3.布尔（Boolean）：true;false
        4.空置（None）
        5.列表（List）
        6.元祖（Tuple）
        7.字典（Dict）
        8.集合（Set）
        9.对象（Object）
标识符：只能有字母、下划线、数字组成（开头不能是数字，区分大小写）
Python的关键字：
    ['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del',
    'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal',
     'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
"""
import keyword

print("关键字：\n", keyword.kwlist)

age = 18
age = age + 2
# del age 删除变量
print("年龄：", age)
print("该数据的类型：", type(age))

"""
字符串
"""
strr = "hello world"
print("该数据的类型：", type(strr))
# title()以首字母大写的方式显示每个单词，即将每个单词的首字母都改为大写
print("首字母大写：", strr.title())

book = "PYTHON"
print(book)
print("全部小写：lower()-->", book.lower())
print("全部大写：upper()-->", book.upper())
name = ' python is a good language '
print("rstrip() 删除 string 字符串末尾的指定字符（默认为空格）：strip()-->", name.rstrip())
name1 = ' python is a good language '
print("lstrip() 删除 string 字符串首位的指定字符（默认为空格）：strip()-->", name1.lstrip())
print("strip()  删除 string 字符串首位的指定字符（默认为空格）：strip()-->", name.strip())

print(id(age))
age1 = age
print(id(age1))

# 连续定义变量
num1 = num2 = num3 = 0
print(num1, num2, num3)
# 作用域
print(id(num1), id(num1), id(num1))
# 交互式定义
num4, num5 = 1, 2
print(num4, num5)

print("================================================================")

"""
浮点数
"""
f1 = 1.2
f2 = 1.3
print(f1 + f2)
print("浮点数相加：", f1 + f2)
"""
复数
"""
p1 = 2 + 1J
p2 = 3 + 2J
print("复数：", p1 + p2)

"""
数字类型转换
"""
print("转整形：", int(1.9))  # 向下取整
print("转小数：", float(20))
print("str转数字：", int("123"))
print("str转小数：", float("123.06"))
# print("str有其他符号转小数：", float("123.06+3"))
# print("str有其他符号转小数：", int("123ac"))
print("str有其他符号转小数：", int("+123"))
print("str有其他符号转小数：", int("-123"))

# 乘方
print("乘方：", 2 ** 3)

# 但需要注意的是，结果包含的小数位数可能是不确定的
print('0.1 + 0.2 = ', 0.1 + 0.2)
a = 1.1
b = 1.2
print('a=0.1 + b=0.2 = ', a + b)

age1 = 23
# message = "Happy " + age1 + "rd Birthday!"
# 这个变量表示的可能是数值23，也可能是字符2和3。像上面这样在字符串中使用整数时，需要显式地指出你希望Python将这个整数用作字符串,
# 为此，可调用函数str()，它让Python将非字符串值表示为字符串
message = "Happy " + str(age1) + "rd Birthday!"
print(message)

print("=====================\n")

"""
 python2 与 python3 将两个整数相除得到的结果稍有不同：
 
 python2 ，整数除法的结果只包含整数部分，小数部分被删除。请注意，计算整数结果时，采取的方式不是四舍五入，而是将小数部分直接删除
"""
print('3 / 2 = ', 3 / 2)
print('python2中：3 / 2 = 1')
print('python2中：3 / 2.0 = 1.5')
print('python2中：3.0 / 2 = 1.5')
print('python2中：3.0 / 2.0 = 1.5')

print("================================================================")

"""
列表（List）
"""
list1 = [1, 2, 3, 8, 9, ]

print(list1)
print(list1[0])

# 定义大小一定的数组

list2 = [0 for i in range(5)]
list3 = [0] * 5

print("数组的长度：", list2.__len__())
print("数组的长度：", list3.__len__())

```
### 1.2 列表

```python
"""
列表：
    序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。
    Python有6个序列的内置类型，但最常见的是列表和元组。
    序列都可以进行的操作包括索引，切片，加，乘，检查成员。
    此外，Python已经内置确定序列的长度以及确定最大和最小的元素的方法。
    列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。
    列表的数据项不需要具有相同的类型
"""
list1 = ['Google', 'Runoob', 1997, 2000]
list2 = [1, 2, 3, 4, 5]
list3 = ["a", "b", "c", "d"]

print(type(list1))
print(list1)
print('数组的长度：', list1.__len__())

# 遍历
print("遍历列表：")
for item in list1:
    print(item)

# 遍历列表得到索引值和数据
"""
使用enumrate函数来获取列表中索引的位置
"""
print("遍历列表得到索引值和数据:")
for index, value in enumerate(list1):
    print(index, value)

print(enumerate(list1))
print(list(enumerate(list1)))

# 输出指定索引的数据
print('输出2位置的元素：', list1[2])
# 输出某段索引的数据
print('输出1-2位置的数据：', list1[1:2])

# 将列表转换成元祖
tup1 = ('Google', 'Runoob', 1997, 2000)
tup_list = list(tup1)
print(type(tup_list))
```
### 1.3 字典
```python
"""
字典：
    字典是另一种可变容器模型，且可存储任意类型对象。
    字典的每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中 ,格式如下所示：
    d = {key1 : value1, key2 : value2 }

    键必须是唯一的，但值则不必。
    值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组。
"""

dict1 = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
dict2 = {'abc': 456}
dict3 = {'abc': 123, 98.6: 37}

print(type(dict1))

# 遍历
print("遍历：")
print(dict1)
print("dict1['Name']: ", dict1['Name'])
print("dict1['Age']: ", dict1['Age'])
print("dict3[98.6]: ", dict3[98.6])

# 	radiansdict.items()   以列表返回可遍历的(键, 值) 元组数组
print('radiansdict.items()   以列表返回可遍历的(键, 值) 元组数组:')
dict__items = dict1.items()
for key, value in dict__items:
    print(key, value)

# 修改
print('修改：')
dict1['Class'] = 'Second'
print(dict1)

'''
字典值可以是任何的 python 对象，既可以是标准的对象，也可以是用户定义的，但键不行。
两个重要的点需要记住：
1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住
2）键必须不可变，所以可以用数字，字符串或元组充当，而用列表就不行(因为列表的值可以改变)
'''
# 当key一样时，后面的覆盖前面
dict3 = {'Name': 'Runoob', 'Age': 7, 'Name': '小菜鸟'}
print("dict['Name']: ", dict3['Name'])

# dict4 = {['Name']: 'Runoob', 'Age': 7}
# print("dict['Name']: ", dict4['Name'])
```

### 1.4 集合
```python
"""
@Time           : 2019-10-13 11:06
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Set.py
@Software       : PyCharm
"""

"""
集合：
    集合（set）是一个无序的不重复元素序列。
    可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典
"""
set1 = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
set2 = {'apple', 2, 'pear', 'orange', 'banana'}
set3 = set(('apple', 'pear', 'orange', 'banana'))

# 遍历
print(set1)

# 添加
set1.add('火龙果')
# 也可以添加元素，且参数可以是列表，元组，字典等
set1.update(['椰子', '石榴'])
set1.update(('木瓜', '杏子'))
set1.update({'核桃', '西瓜'})
print(set1)

# 移除，如果集合中没有该元素，会报错
set1.remove('西瓜')
# 还有一个方法也是移除集合中的元素，且如果元素不存在，不会发生错误
set1.discard('X')
set1.discard('核桃')
print(set1)
```

### 1.5 元祖
```python
"""
元祖：
    Python 的元组与列表类似，不同之处在于元组的元素不能修改。
    元组使用小括号，列表使用方括号。
    元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可
"""
tup1 = ('Google', 'Runoob', 1997, 2000)
tup2 = (1, 2, 3, 4, 5)
# 不需要括号也可以
tup3 = "a", "b", "c", "d"
print(type(tup3))

print("tup1[0]: ", tup1[0])
print("tup2[1:5]: ", tup2[1:5])

for index, value in enumerate(tup1):
    print(index, value)

# 将列表转换为元组
list1 = ["a", "b", "c", "d"]
list_tuple = tuple(list1)
print(type(list_tuple))
```
## 2 流程控制
### 2.1 循环
```python
"""
@Time           : 2019-10-13 11:57
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Cycle.py
@Software       : PyCharm
"""

'''
循环：在 Python 中没有 do..while 循环。

'''
# while循环
a = 3
while a <= 6:
    print(a)
    a += 1

# 计算从1到100的和
count = 0
counter = 1
while counter <= 100:
    count += counter
    counter += 1
print(count)

# while 循环使用 else 语句: 在 while … else 在条件语句为 false 时执行 else
print('while 循环使用 else 语句:')
b = 0
while b < 5:
    print(b, " 小于 5")
    b = b + 1
else:
    print(b, " 大于或等于 5")

# 类似if语句的语法，如果你的while循环体中只有一条语句，你可以将该语句与while写在同一行中
flag = 1
while flag == 2: print('类似if语句的语法，如果你的while循环体中只有一条语句，你可以将该语句与while写在同一行中!')

'''
for 语句
Python for循环可以遍历任何序列的项目，如一个列表或者一个字符串。
        for循环的一般格式如下：
        for <variable> in <sequence>:
            <statements>
        else:
            <statements>
'''
list1 = [1, 3, 5, 7, 8]

for val in list1:
    if val == 7:
        continue
    print(val)
```

### 2.2 选择判断
```python
"""
条件判断:

三目表达式：
java：判断条件 ? true : false
python: true if 判断条件 else false (为真时的结果 if 判断条件 else 为假时的结果)
"""

print("请求输入一个数字：")
b = int(input())

if b > 5:
    print(b + 1 if b + 2 == 1 else b)
elif b < 5:
    print(b % 2)
else:
    print(b)
```

## 3 运算符

```python
"""
@Time           : 2019-10-13 11:31
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Mathematical.py
@Software       : PyCharm
"""
"""
运算符：
只演示，与Java不一样的运算符：
"""

# 算数运算符

# ** 幂 - 返回x的y次幂
print(2 ** 3)
# // 取整除 - 向下取接近除数的整数
print(8 // 3)

# 赋值运算符

# **=	幂赋值运算符	c **= a 等效于 c = c ** a
# //=	取整除赋值运算符	c //= a 等效于 c = c // a
a = 5
c = 3
c **= a
print(c)

c //= a
print(a)

# 逻辑运算符

# and	x and y	布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。	(a and b) 返回 20。(java: &&)
# or	x or y	布尔"或" - 如果 x 是 True，它返回 x 的值，否则它返回 y 的计算值。	(a or b) 返回 10。(java:||)
# not	not x	布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。	not(a and b) 返回 False (java:!)
print('逻辑运算：')
d = True
e = False
print('and逻辑与: ', d and e)
print('or逻辑或: ', d or e)
print('not逻辑非: ', not e)

# 成员运算

# in	如果在指定的序列中找到值返回 True，否则返回 False。	x 在 y 序列中 , 如果 x 在 y 序列中返回 True。
# not in	如果在指定的序列中没有找到值返回 True，否则返回 False。	x 不在 y 序列中 , 如果 x 不在 y 序列中返回 True。

print('成员运算：')
list1 = [1, 2, 3, 4, 5]
f = 3
print(f in list1)
print(f not in list1)
```
## 4 函数
```python
"""
@Time           : 2019-10-14 22:21
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Function.py
@Software       : PyCharm
"""
"""
函数：
    定义一个函数
    你可以定义一个由自己想要功能的函数，以下是简单的规则：
    函数代码块以 def 关键词开头，后接函数标识符名称和圆括号 ()。
    任何传入参数和自变量必须放在圆括号中间，圆括号之间可以用于定义参数。
    函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
    函数内容以冒号起始，并且缩进。
    return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。
    
    Python 定义函数使用 def 关键字，一般格式如下：
    def 函数名（参数列表）:
        函数体
"""


# return [表达式] 语句用于退出函数，选择性地向调用方返回一个表达式。不带参数值的return语句返回None
def sum(a, b):
    return a + b


# 调用函数
print(sum(10, 20))
print("------------------------")

'''
在 python 中，类型属于对象，变量是没有类型的
    a=[1,2,3]
    a="Runoob"
    以上代码中，[1,2,3] 是 List 类型，"Runoob" 是 String 类型，而变量 a 是没有类型，她仅仅是一个对象的引用（一个指针），可以是指向 List 类型对象，也可以是指向 String 类型对象。
    
可更改(mutable)与不可更改(immutable)对象
    在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。
    不可变类型：
        变量赋值 a=5 后再赋值 a=10，这里实际是新生成一个 int 值对象 10，再让 a 指向它，而 5 被丢弃，不是改变a的值，相当于新生成了a。
    可变类型：
        变量赋值 la=[1,2,3,4] 后再赋值 la[2]=5 则是将 list la 的第三个元素值更改，本身la没有动，只是其内部的一部分值被修改了。
    
    python 函数的参数传递：
    不可变类型：
        类似 c++ 的值传递，如 整数、字符串、元组。如fun（a），传递的只是a的值，没有影响a对象本身。比如在 fun（a）内部修改 a 的值，只是修改另一个复制的对象，不会影响 a 本身。
    可变类型：
        类似 c++ 的引用传递，如 列表，字典。如 fun（la），则是将 la 真正的传过去，修改后fun外部的la也会受影响
python 中一切都是对象，严格意义我们不能说值传递还是引用传递，我们应该说传不可变对象和传可变对象    
        
'''


# python 传不可变对象实例

# 数字
def ChangeInt(a):
    a = 10


b = 2
ChangeInt(b)
# 实例中有 int 对象 2，指向它的变量是 b，在传递给 ChangeInt 函数时，按传值的方式复制了变量 b，a 和 b 都指向了同一个 Int 对象，在 a=10 时，则新生成一个 int 值对象 10，并让 a 指向它。
# 结果是 2
print(b)


# 字符串
def ChangeStr(str):
    str = 'str'


str1 = '12str'
ChangeStr(str1)
print(str1)


# 元祖
def ChangeTuple(tuple):
    tup1 = (11, 22, 2, 3)


tup1 = ('d', 4, 5, 6)
ChangeTuple(tup1)
print(tup1)
print("------------------------")


# 传可变对象实例
# 可变对象在函数里修改了参数，那么在调用这个函数的函数里，原始的参数也被改变了

def ChangeList(mylist):
    """修改传入的列表"""
    mylist.append([1, 2, 3, 4])
    print("函数内取值: ", mylist)
    return


# 调用ChangeList函数
mylist = [10, 20, 30]
ChangeList(mylist)
print("函数外取值: ", mylist)


# json
def ChangeDict(dict1):
    """修改传入的列表"""
    dict1.update({"isSuccess": "success"})
    print("函数内取值: ", dict1)
    return


# 调用ChangeDict函数
dict1 = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
ChangeDict(dict1)
print("函数外取值: ", dict1)
print("------------------------")

""""
参数：

1、关键字参数
    关键字参数和函数调用关系紧密，函数调用使用关键字参数来确定传入的参数值。
    使用关键字参数允许函数调用时参数的顺序与声明时不一致，因为 Python 解释器能够用参数名匹配参数值。
2、默认参数
    调用函数时，如果没有传递参数，则会使用默认参数    

3、不定长参数
    你可能需要一个函数能处理比当初声明时更多的参数。这些参数叫做不定长参数，和上述 2 种参数不同，声明时不会命名
"""


# 1、关键字参数
# 可写函数说明
def printme(str):
    """打印任何传入的字符串"""
    print(str)
    return


# 调用printme函数
printme(str="菜鸟教程")


# 可写函数说明
def printinfo(name, age):
    "打印任何传入的字符串"
    print("名字: ", name)
    print("年龄: ", age)
    return


# 调用printinfo函数
printinfo(age=50, name="runoob")
print("------------------------")


# 2、默认参数

def printinfo(name, age=35):
    "打印任何传入的字符串"
    print("名字: ", name)
    print("年龄: ", age)
    return


# 调用printinfo函数
printinfo(age=50, name="aaa")
printinfo(name="aaa")
print("------------------------")


# 3、不定长参数
# def functionname([formal_args, ] * var_args_tuple):
#     """函数_文档字符串"""
#     function_suite
#     return [expression]

def printinfo(arg1, *vartuple):
    """打印任何传入的参数"""
    print("输出: ")
    print(arg1)
    print(vartuple)


# 调用printinfo 函数
printinfo(70, 60, 50)
print("------------------------")


# 如果在函数调用时没有指定参数，它就是一个空元组。我们也可以不向函数传递未命名的变量
def printinfo(arg1, *vartuple):
    """打印任何传入的参数"""
    print("输出: ")
    print(arg1)
    for var in vartuple:
        print(var)
    return


# 调用printinfo 函数
printinfo(10)
printinfo(70, 60, 50)
print("------------------------")


# 加了两个星号 ** 的参数会以字典的形式导入
def printinfo(arg1, **vardict):
    """打印任何传入的参数"""
    print("输出: ")
    print(arg1)
    print(vardict)


# 调用printinfo 函数
printinfo(1, a=2, b=3)
print("------------------------")


# 如果单独出现星号 * 后的参数必须用关键字传入
def printinfo(arg1, *, arg2, arg3):
    return arg1 * arg2 * arg3


# 调用printinfo 函数
print(printinfo(1, arg2=3, arg3=4))
print("------------------------")

"""
匿名函数
python 使用 lambda 来创建匿名函数。
所谓匿名，意即不再使用 def 语句这样标准的形式定义一个函数。

    lambda 只是一个表达式，函数体比 def 简单很多。
    lambda的主体是一个表达式，而不是一个代码块。仅仅能在lambda表达式中封装有限的逻辑进去。
    lambda 函数拥有自己的命名空间，且不能访问自己参数列表之外或全局命名空间里的参数。
    虽然lambda函数看起来只能写一行，却不等同于C或C++的内联函数，后者的目的是调用小函数时不占用栈内存从而增加运行效率。
语法:
    lambda 函数的语法只包含一个语句，如下：
    lambda [arg1 [,arg2,.....argn]]:expression
"""

sum = lambda arg1, arg2: arg1 + arg2

# 调用sum函数
print("相加后的值为 : ", sum(10, 20))
print("相加后的值为 : ", sum(20, 20))
```

## 5 模块
```python
"""
@Time           : 2019-10-16 21:34
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Model.py
@Software       : PyCharm
"""
"""
模块：
    从 Python 解释器退出再进入，那么你定义的所有的方法和变量就都消失了。
    为此 Python 提供了一个办法，把这些定义存放在文件中，为一些脚本或者交互式的解释器实例使用，这个文件被称为模块。
    模块是一个包含所有你定义的函数和变量的文件，其后缀名是.py。模块可以被别的程序引入，以使用该模块中的函数等功能。这也是使用 python 标准库的方法。
"""

# Python标准库的例子：
import sys

# 将模块所在报加载成顶级目录
# import Support as sp
from day01.com.azbz.cl.model import Support as sp
import day01.com.azbz.cl.model.Fobble as f
from day01.com.azbz.cl.model.Fobble import fib, fib2
from day01.com.azbz.cl.model.color import Red

print('命令行参数如下:')
for i in sys.argv:
    print(i)

print('Python 路径为：', sys.path, '\n')
'''
1、import sys 引入 python 标准库中的 sys.py 模块；这是引入某一模块的方法。
2、sys.argv 是一个包含命令行参数的列表。
3、sys.path 包含了一个 Python 解释器自动查找所需模块的路径的列表。
'''

# import 语句
# 想使用 Python 源文件，只需在另一个源文件里执行 import 语句，语法如下：
# import module1[, module2[,... moduleN]
# 当解释器遇到 import 语句，如果模块在当前的搜索路径就会被导入。

sp.print_func("gggggg")

f.fib(200)
print(f.fib2(200))

"""
from … import 语句
    Python 的 from 语句让你从模块中导入一个指定的部分到当前命名空间中，语法如下：
    from modname import name1[, name2[, ... nameN]]
    例如，要导入模块 fibo 的 fib 函数，使用如下语句：
    
    from fibo import fib, fib2
    fib(500)
    1 1 2 3 5 8 13 21 34 55 89 144 233 377
    这个声明不会把整个fibo模块导入到当前的命名空间中，它只会将fibo里的fib函数引入进来。
"""
fib(300)
print(fib2(500))

"""
from … import * 语句
把一个模块的所有内容全都导入到当前的命名空间也是可行的，只需使用如下声明：

from modname import *
这提供了一个简单的方法来导入一个模块中的所有项目。然而这种声明不该被过多地使用

将把所有的名字都导入进来，但是那些由单一下划线（_）开头的名字不在此例。大多数情况， Python程序员不使用这种方法，因为引入的其它来源的命名，很可能覆盖了已有的定义。
"""

# 说明： 每个模块都有一个__name__属性，当其值是'__main__'时，表明该模块自身在运行，否则是被引入。
if __name__ == '__main__':
    print('程序自身在运行')
else:
    print('我来自另一模块')

# dir() 函数
# 内置的函数 dir() 可以找到模块内定义的所有名称。以一个字符串列表的形式返回

print(dir(f))
print(dir(sp))
print(dir())

"""
这里给出了一种可能的包结构（在分层的文件系统中）:

sound/                          顶层包
      __init__.py               初始化 sound 包
      formats/                  文件格式转换子包
              __init__.py
              wavread.py
              wavwrite.py
              aiffread.py
              aiffwrite.py
              auread.py
              auwrite.py
              ...
      effects/                  声音效果子包
              __init__.py
              echo.py
              surround.py
              reverse.py
              ...
      filters/                  filters 子包
              __init__.py
              equalizer.py
              vocoder.py
              karaoke.py
              ...

使用时：导包： from sound.effects import echo
"""
Red.pri_red()
```

## 6 读写文件

```python
"""
读和写文件
    open() 将会返回一个 file 对象，基本语法格式如下:
    open(filename, mode)
    filename：包含了你要访问的文件名称的字符串值。
    mode：决定了打开文件的模式：只读，写入，追加等。所有可取值见如下的完全列表。这个参数是非强制的，默认文件访问模式为只读(r)。
"""
```
不同模式打开文件的完全列表:

| 模式 | 说明 |
| ---- | ---- |
|r	    |以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。|
|rb	    |以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。|
|r+	    |打开一个文件用于读写。文件指针将会放在文件的开头。|
|rb+	|以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。|
|w	    |打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|wb	    |以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|w+	    |打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|wb+	|以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。|
|a	    |打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。|
|ab	    |以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。|
|a+	    |打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。|
|ab+	|以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。|

![](./images/文件打开模式.png)

```python
"""
@Time           : 2019-10-18 20:32
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : File.py
@Software       : PyCharm
"""

"""
读和写文件
    open() 将会返回一个 file 对象，基本语法格式如下:
        open(filename, mode)
        filename：包含了你要访问的文件名称的字符串值。
        mode：决定了打开文件的模式：只读，写入，追加等。所有可取值见如下的完全列表。这个参数是非强制的，默认文件访问模式为只读(r)。
"""
# 打开一个文件
f = open("E:/project-group/python-project/foo1.txt", "w+")
write = f.write("Python 是一个非常好的语言。\n是的，的确非常好!!\n")
print('将下列内容写入文件的字符数：', write)
# 关闭打开的文件
f.close()
print('-----------------------------------------------------------------')

# 写入一些不是字符串的东西, 那么将需要先进行转换:
print('写入一些不是字符串的东西, 那么将需要先进行转换')
f = open("E:/project-group/python-project/foo3.txt", "w")
value = ('www.runoob.com', 14)
s = str(value)
f.write(s)
# 关闭打开的文件
f.close()
print('-----------------------------------------------------------------')

# f.tell() 返回文件对象当前所处的位置, 它是从文件开头开始算起的字节数
f = open("E:/project-group/python-project/foo3.txt", "r")
print(f.tell())
f.close()
print('-----------------------------------------------------------------')

# f.seek()
# 如果要改变文件当前的位置, 可以使用 f.seek(offset, from_what) 函数。
#   from_what 的值, 如果是 0 表示开头, 如果是 1 表示当前位置, 2 表示文件的结尾，例如：
#   seek(x,0) ： 从起始位置即文件首行首字符开始移动 x 个字符
#   seek(x,1) ： 表示从当前位置往后移动x个字符
#   seek(-x,2)：表示从文件的结尾往前移动x个字符
f = open("E:/project-group/python-project/foo3.txt", "rb+")
print(f.seek(0))
print(f.seek(1))
print(f.seek(2))
print('-----------------------------------------------------------------')

# 处理一个文件对象时, 使用 with 关键字是非常好的方式。在结束后, 它会帮你正确的关闭文件。 而且写起来也比 try - finally 语句块要简短
with open('E:/project-group/python-project/foo3.txt', 'r') as f:
    read_data = f.read()
    print(read_data)
f.close()
print('-----------------------------------------------------------------')

"""
 读取文件
"""
# 为了读取一个文件的内容，调用 f.read(size), 这将读取一定数目的数据, 然后作为字符串或字节对象返回。
# size 是一个可选的数字类型的参数。 当 size 被忽略了或者为负, 那么该文件的所有内容都将被读取并且返回。
file = open("E:/project-group/python-project/foo1.txt", 'r')
print(file.read())
file.close()
print('-----------------------------------------------------------------')

# f.readlines()
# f.readlines() 将返回该文件中包含的所有行。
# 如果设置可选参数 sizehint, 则读取指定长度的字节, 并且将这些字节按行分割。
file1 = open("E:/project-group/python-project/foo1.txt", 'r')
print(file1.readline())
file1.close()
file2 = open("E:/project-group/python-project/foo1.txt", 'r')
print(file2.readlines())
file2.close()
print('-----------------------------------------------------------------')

# 迭代读取文件
file3 = open("E:/project-group/python-project/foo1.txt", 'r')
for line in file3:
    print(line, end='')
# 关闭打开的文件
file3.close()
print('-----------------------------------------------------------------')

"""
pickle 模块
    python的pickle模块实现了基本的数据序列和反序列化。
    通过pickle模块的序列化操作我们能够将程序中运行的对象信息保存到文件中去，永久存储。
    通过pickle模块的反序列化操作，我们能够从文件中创建上一次程序保存的对象。
    
基本接口：
    pickle.dump(obj, file, [,protocol])
    有了 pickle 这个对象, 就能对 file 以读取的形式打开:
    
    x = pickle.load(file)
    注解：从 file 中读取一个字符串，并将它重构为原来的python对象。
    file: 类文件对象，有read()和readline()接口。
"""
import pickle
import pprint

# 使用pickle模块将数据对象保存到文件
data1 = {'a': [1, 2.0, 3, 4 + 6j],
         'b': ('string', 'Unicode string'),
         'c': None}

output = open('E:/project-group/python-project/data.pkl', 'wb')
# Pickle dictionary using protocol 0.
pickle.dump(data1, output)

selfref_list = [1, 2, 3]
selfref_list.append(selfref_list)
# Pickle the list using the highest protocol available.
pickle.dump(selfref_list, output, -1)
output.close()
print('-----------------------------------------------------------------')

# 使用pickle模块从文件中重构python对象
pkl_file = open('E:/project-group/python-project/data.pkl', 'rb')
data1 = pickle.load(pkl_file)
pprint.pprint(data1)

data2 = pickle.load(pkl_file)
pprint.pprint(data2)

pkl_file.close()
```

## 7 文件

|	序号|	方法及描述|
| ---- | ---- |
|1	|file.close()关闭文件。关闭后文件不能再进行读写操作。|
|2	|file.flush()刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。|
|3	|file.fileno()返回一个整型的文件描述符(file descriptor FD 整型), 可以用在如os模块的read方法等一些底层操作上。|
|4	|file.isatty()如果文件连接到一个终端设备返回 True，否则返回 False。|
|5	|<font color='red'> file.next()Python 3 中的 File 对象不支持 next() 方法。返回文件下一行。</font>|
|6	|file.read([size])从文件读取指定的字节数，如果未给定或为负则读取所有。|
|7	|file.readline([size])读取整行，包括 "\n" 字符。|
|8	|file.readlines([sizeint])读取所有行并返回列表，若给定sizeint>0，返回总和大约为sizeint字节的行, 实际读取值可能比 sizeint 较大, 因为需要填充缓冲区。|
|9	|file.seek(offset[, whence])移动文件读取指针到指定位置|
|10	|file.tell()返回文件当前位置。|
|11	|file.truncate([size])从文件的首行首字符开始截断，截断文件为 size 个字符，无 size 表示从当前位置截断；截断之后后面的所有字符被删除，其中 Widnows 系统下的换行代表2个字符大小。|
|12	|file.write(str)将字符串写入文件，返回的是写入的字符长度。|
|13	|file.writelines(sequence)向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。|


## 8 异常

### 8.1 异常处理
```python
"""
异常处理:
    try语句按照如下方式工作；
        首先，执行try子句（在关键字try和关键字except之间的语句）
        如果没有异常发生，忽略except子句，try子句执行后结束。
        如果在执行try子句的过程中发生了异常，那么try子句余下的部分将被忽略。如果异常的类型和 except 之后的名称相符，那么对应的except子句将被执行。最后执行 try 语句之后的代码。
        如果一个异常没有与任何的except匹配，那么这个异常将会传递给上层的try中。
    
    一个 try 语句可能包含多个except子句，分别来处理不同的特定的异常。最多只有一个分支会被执行。
    处理程序将只针对对应的try子句中的异常进行处理，而不是其他的 try 的处理程序中的异常。
    一个except子句可以同时处理多个异常，这些异常将被放在一个括号里成为一个元组
    
    语法：
        except (RuntimeError, TypeError, NameError):
            pass
"""
print('------------------------------异常语法---------------------------------')
try:
    f = open('myfile.txt')
    s = f.readline()
    i = int(s.strip())
except OSError as err:
    print('OS error:{0}'.format(err))
except ValueError:
    print("Could not convert data to an integer")
except:
    print("Unexpected error:", sys.exc_info()[0])

# try except 语句还有一个可选的else子句，如果使用这个子句，那么必须放在所有的except子句之后。这个子句将在try子句没有发生任何异常的时候执行。
# 使用 else 子句比把所有的语句都放在 try 子句里面要好，这样可以避免一些意想不到的、而except又没有捕获的异常。
print('-------------------使用 try ... except ... else ... -----------------')
for arg in sys.argv[1:]:
    try:
        f = open(arg, 'r')
    except IOError:
        print('cannot open', arg)
    else:
        print(arg, 'has', len(f.readlines()), 'lines')
        f.close()

# 异常处理并不仅仅处理那些直接发生在try子句中的异常，而且还能处理子句中调用的函数（甚至间接调用的函数）里抛出的异常
print('----------------------------处理函数的异常-----------------------------')


def this_fails():
    x = 1 / 0


try:
    this_fails()
except ZeroDivisionError as err:
    print('Handling run-time error:', err)

"""
try 语句还有另外一个可选的子句，它定义了无论在任何情况下都会执行的清理行为

    不管 try 子句里面有没有发生异常，finally 子句都会执行。
    如果一个异常在 try 子句里（或者在 except 和 else 子句里）被抛出，而又没有任何的 except 把它截住，那么这个异常会在 finally 子句执行后被抛出。
"""

print('----------------------------try 子句里面有没有发生异常，finally 子句都会执行-----------------------------')


def divide(x, y):
    try:
        result = x / y
    except ZeroDivisionError:
        print("division by zero!")
    else:
        print("result is", result)
    finally:
        print("executing finally clause")


divide(2, 1)
divide(2, 0)
# divide("2", "1")

"""
预定义的清理行为
    一些对象定义了标准的清理行为，无论系统是否成功的使用了它，一旦不需要它了，那么这个标准的清理行为就会执行。
    这面这个例子展示了尝试打开一个文件，然后把内容打印到屏幕上:
    for line in open("myfile.txt"):
        print(line, end="")
    以上这段代码的问题是，当执行完毕后，文件会保持打开状态，并没有被关闭
    
    关键词 with 语句就可以保证诸如文件之类的对象在使用完之后一定会正确的执行他的清理方法
"""
with open("myfile.txt") as f:
    for line in f:
        print(line, end="")
```
### 8.2 抛出异常
```python
"""
抛出异常：  
    Python 使用 raise 语句抛出一个指定的异常

    raise 唯一的一个参数指定了要被抛出的异常。它必须是一个异常的实例或者是异常的类（也就是 Exception 的子类）。
    如果你只想知道这是否抛出了一个异常，并不想去处理它，那么一个简单的 raise 语句就可以再次把它抛出。
"""

# raise NameError('HiThere')

print('---------------------------抛出异常----------------------------------')
try:
    raise NameError('HiThere')
except NameError:
    print('An exception flew by!')
    raise
```

### 8.3 自定义异常
````python
"""
自定义异常：
    通过创建一个新的异常类来拥有自己的异常。异常类继承自 Exception 类，可以直接继承，或者间接继承
"""


class MyError(Exception):
    def __init__(self, value):
        self.value = value

    def __str__(self):
        return repr(self.value)


try:
    raise MyError(2 * 2)
except MyError as e:
    print('My exception occurred, value:', e.value)

# 类 Exception 默认的 __init__() 被覆盖


"""
当创建一个模块有可能抛出多种不同的异常时，一种通常的做法是为这个包建立一个基础异常类，然后基于这个基础类为不同的错误情况创建不同的子类:
"""

"""
定义基础异常 继承Exception
"""


class Error(Exception):
    """Base class for exceptions in this module."""
    pass


class InputError(Error):
    """
    Exception raised for errors in the input.

      ​Attributes:
          ​expression -- input expression in which the error occurred
          ​message -- explanation of the error
    """


def __init__(self, expression, message):
    self.message = message
    self.expression = expression


class TransitionError(Error):
    """
    Raised when an operation attempts a state transition that's not ​allowed.

     ​Attributes:
         ​previous -- state at beginning of transition
         ​next -- attempted new state
         ​message -- explanation of why the specific transition is not allowed
    """


def __init__(self, previous, next, message):
    self.previous = previous
    self.message = message
    self.next = next
````

## 8 类
> Python从设计之初就已经是一门面向对象的语言，正因为如此，在Python中创建一个类和对象是很容易的。本章节我们将详细介绍Python的面向对象编程
>     类(Class): 用来描述具有相同的属性和方法的对象的集合。它定义了该集合中每个对象所共有的属性和方法。对象是类的实例。
>     方法：     类中定义的函数。
>     类变量：   类变量在整个实例化的对象中是公用的。类变量定义在类中且在函数体之外。类变量通常不作为实例变量使用。
>     数据成员： 类变量或者实例变量用于处理类及其实例对象的相关的数据。
>     方法重写： 如果从父类继承的方法不能满足子类的需求，可以对其进行改写，这个过程叫方法的覆盖（override），也称为方法的重写。
>     局部变量： 定义在方法中的变量，只作用于当前实例的类。
>     实例变量： 在类的声明中，属性是用变量来表示的。这种变量就称为实例变量，是在类声明的内部但是在类的其他成员方法之外声明的。
>     继承：     即一个派生类（derived class）继承基类（base class）的字段和方法。继承也允许把一个派生类的对象作为一个基类对象对待。例如，有这样一个设计：一个Dog类型的对象派生自Animal类，这是模拟"是一个（is-a）"关系（例图，Dog是一个Animal）。
>     实例化：   创建一个类的实例，类的具体对象。
>     对象：     通过类定义的数据结构实例。对象包括两个数据成员（类变量和实例变量）和方法。    
>
> 其它编程语言相比，Python 在尽可能不增加新的语法和语义的情况下加入了类机制。
> Python中的类提供了面向对象编程的所有基本功能：
>     类的继承机制允许多个基类，派生类可以覆盖基类中的任何方法，方法中可以调用基类中的同名方法。
> 对象可以包含任意数量和类型的数据

### 8.1 定义类
```python
"""
类定义：
    类对象支持两种操作：属性引用和实例化。
    属性引用使用和 Python 中所有的属性引用一样的标准语法：obj.name。
    类对象创建后，类命名空间中所有的命名都是有效属性名

类有一个名为 
 __init__() 方法可以有参数，参数通过 __init__() 传递到类的实例化操作上
"""

print('----------------------------定义类-------------------------------')


class MyClass:
    """一个简单的类实例"""
    i = 12345

    b: int = 0
    name: str = ''

    def f(self):
        return 'hello world'

    # __init__() 的特殊方法（构造方法），该方法在类实例化时会自动调用
    def __init__(self, b, name):
        self.b = b
        self.name = name


x = MyClass(28, '赵丽颖')
print('b=', x.b, 'name=', x.name)

# 访问类的属性
print(x.i)
# 访问类的方法
print(x.f())

"""
self代表类的实例，而非类
    类的方法与普通的函数只有一个特别的区别————》它们必须有一个额外的第一个参数名称, 按照惯例它的名称是 self。
    
    self 不是 python 关键字，我们把他换成 runoob 也是可以正常执行
"""
print(x)
print(x.__class__)
```

### 8.2 类中的方法
```python
"""
类的方法
    在类的内部，使用 def 关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数 self, 且为第一个参数，self 代表的是类的实例
"""


class People:
    # 定义基本属性
    name = ''
    age = 0
    # 定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0

    # 定义构造方法
    def __init__(self, n, a, w):
        self.name = n
        self.age = a
        self.__weight = w

    def speak(self):
        print("%s 说: 我 %d 岁。" % (self.name, self.age))


p = People(a=28, n='刘亦菲', w=98.56)
p.speak()
```

### 8.3 继承
#### 8.3.1 单继承
```python
print('----------------------------单继承--------------------------------')

"""
继承：
    Python 同样支持类的继承，如果一种语言不支持继承，类就没有什么意义。派生类的定义如下所示:
    class DerivedClassName(BaseClassName1):
        <statement-1>
        .
        .
        .
        <statement-N>
        
    需要注意圆括号中基类的顺序，若是基类中有相同的方法名，而在子类使用时未指定，python从左至右搜索 即方法在子类中未找到时，从左到右查找基类中是否包含方法。
    BaseClassName（示例中的基类名）必须与派生类定义在一个作用域内。除了类，还可以用表达式，基类定义在另一个模块中时这一点非常有用:
"""


# 单继承

# 类定义
class People1:
    # 定义基本属性
    name = ''
    age = 0
    # 定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0

    # 定义构造方法
    def __init__(self, n, a, w):
        self.name = n
        self.age = a
        self.__weight = w

    def speak(self):
        print("%s 说: 我 %d 岁。" % (self.name, self.age))


# 单继承示例
class Student(People1):
    grade = ''

    def __init__(self, n, a, w, g):
        # 调用父类的构函
        People1.__init__(self, n, a, w)
        self.grade = g

    # 覆写父类的方法
    def speak(self):
        print("%s 说: 我 %d 岁了，我在读 %d 年级" % (self.name, self.age, self.grade))


s = Student('ken', 10, 60, 3)
s.speak()
```

#### 8.3.2 多继承
```python
print('----------------------------多继承--------------------------------')

"""
多继承
    Python同样有限的支持多继承形式。多继承的类定义形如下例:
    
    class DerivedClassName(Base1, Base2, Base3):
        <statement-1>
        .
        .
        .
        <statement-N>
    需要注意圆括号中父类的顺序，若是父类中有相同的方法名，而在子类使用时未指定，python从左至右搜索 即方法在子类中未找到时，从左到右查找父类中是否包含方法。
"""


# 另一个类，多重继承之前的准备
class Speaker:
    topic = ''
    name = ''

    def __init__(self, n, t):
        self.name = n
        self.topic = t

    def speak(self):
        print("我叫 %s，我是一个演说家，我演讲的主题是 %s" % (self.name, self.topic))


# 多重继承
class Sample(Speaker, Student):
    a = ''

    def __init__(self, n, a, w, g, t):
        Student.__init__(self, n, a, w, g)
        Speaker.__init__(self, n, t)


test = Sample("Tim", 25, 80, 4, "Python")
# 方法名同，默认调用的是在括号中排前地父类的方法
test.speak()
```
### 8.4 方法重写
```python
print('----------------------------方法重写--------------------------------')
"""
方法重写：
    如果你的父类方法的功能不能满足你的需求，你可以在子类重写你父类的方法
"""


class Parent:  # 定义父类
    def myMethod(self):
        print('调用父类方法')


class Child(Parent):  # 定义子类
    def myMethod(self):
        print('调用子类方法')


# 子类实例
c = Child()
# 子类调用重写方法
c.myMethod()
# 用子类对象调用父类已被覆盖的方法
# super() 函数是用于调用父类(超类)的一个方法
super(Child, c).myMethod()
```
### 8.5 子类继承父类的构造函数说明
```python
print('----------------------------子类继承父类构造函数说明--------------------------------')

'''
Python 子类继承父类构造函数说明：
    （1）如果在子类中需要父类的构造方法就需要显式地调用父类的构造方法，或者不重写父类的构造方法。 子类不重写 __init__，实例化子类时，会自动调用父类定义的 __init__。
    （2）如果重写了__init__ 时，实例化子类，就不会调用父类已经定义的 __init__
    （3）如果重写了__init__ 时，要继承父类的构造方法，可以使用 super 关键字
'''


# （1）（2）
class Father(object):
    def __init__(self, name):
        self.name = name
        print("name: %s" % (self.name))

    def getName(self):
        return 'Father ' + self.name


class Son(Father):
    # def __init__(self, name):
    #     print("hi")
    #     self.name = name

    def getName(self):
        return 'Son ' + self.name


if __name__ == '__main__':
    son = Son('runoob')
    print(son.getName())


# （3）
class Father(object):
    def __init__(self, name):
        self.name = name
        print("name: %s" % (self.name))

    def getName(self):
        return 'Father ' + self.name


class Son(Father):
    def __init__(self, name):
        super(Son, self).__init__(name)
        print("hi")
        self.name = name

    def getName(self):
        return 'Son ' + self.name


if __name__ == '__main__':
    son = Son('runoob')
    print(son.getName())

"""
情况一：子类需要自动调用父类的方法：子类不重写__init__()方法，实例化子类后，会自动调用父类的__init__()的方法。
情况二：子类不需要自动调用父类的方法：子类重写__init__()方法，实例化子类后，将不会自动调用父类的__init__()的方法。
情况三：子类重写__init__()方法又需要调用父类的方法：使用super关键词：
    super(子类，self).__init__(参数1，参数2，....)
    class Son(Father):
      def __init__(self, name):   
        super(Son, self).__init__(name)
"""
```
### 8.6 类属性和方法
```python
print('----------------------------类属性与方法--------------------------------')
"""
类属性与方法:
    类的私有属性
        __private_attrs：两个下划线开头，声明该属性为私有，不能在类的外部被使用或直接访问。在类内部的方法中使用时 self.__private_attrs。
    类的方法
        在类的内部，使用 def 关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数 self，且为第一个参数，self 代表的是类的实例。
        self 的名字并不是规定死的，也可以使用 this，但是最好还是按照约定是用 self。
    类的私有方法
        __private_method：两个下划线开头，声明该方法为私有方法，只能在类的内部调用 ，不能在类的外部调用。self.__private_methods。
        
类的专有方法：
    __init__ : 构造函数，在生成对象时调用
    __del__ : 析构函数，释放对象时使用
    __repr__ : 打印，转换
    __setitem__ : 按照索引赋值
    __getitem__: 按照索引获取值
    __len__: 获得长度
    __cmp__: 比较运算
    __call__: 函数调用
    __add__: 加运算
    __sub__: 减运算
    __mul__: 乘运算
    __truediv__: 除运算
    __mod__: 求余运算
    __pow__: 乘方
"""
```
### 8.7 运算符重载
```python
print('----------------------------运算符重载--------------------------------')
"""
运算符重载
    Python同样支持运算符重载，我们可以对类的专有方法进行重载
"""


class Vector:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    def __str__(self):
        return 'Vector (%d, %d)' % (self.a, self.b)

    def __add__(self, other):
        return Vector(self.a + other.a, self.b + other.b)


v1 = Vector(2, 10)
v2 = Vector(5, -2)
print(v1 + v2)
```

## 9 命名空间和作用域

### 9.1 命名空间
```python
"""
@Time           : 2019-10-20 12:56
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : NameSpace.py
@Software       : PyCharm
"""
"""
命名空间：
    命名空间(Namespace)是从名称到对象的映射，大部分的命名空间都是通过 Python 字典来实现的。
    命名空间提供了在项目中避免名字冲突的一种方法。各个命名空间是独立的，没有任何关系的，所以一个命名空间中不能有重名，但不同的命名空间是可以重名而没有任何影响。
    
    一般有三种命名空间：
        内置名称（built-in names）， Python 语言内置的名称，比如函数名 abs、char 和异常名称 BaseException、Exception 等等。
        全局名称（global names），模块中定义的名称，记录了模块的变量，包括函数、类、其它导入的模块、模块级的变量和常量。
        局部名称（local names），函数中定义的名称，记录了函数的变量，包括函数的参数和局部定义的变量。（类中定义的也是）
        
    命名空间查找顺序:
        假设我们要使用变量 runoob，则 Python 的查找顺序为：局部的命名空间去 -> 全局命名空间 -> 内置命名空间。
        如果找不到变量 runoob，它将放弃查找并引发一个 NameError 异常: NameError: name 'runoob' is not defined。
        
        
    命名空间的生命周期：
        命名空间的生命周期取决于对象的作用域，如果对象执行完成，则该命名空间的生命周期就结束。
        因此，我们无法从外部命名空间访问内部命名空间的对象。
"""
print('--------------------------------命名空间----------------------------------')
# var1 是全局名称
var1 = 5


def some_func():
    # var2 是局部名称
    var2 = 6

    def some_inner_func():
        # var3 是内嵌的局部名称
        var3 = 7
```
![](./images/命名空间的查找顺序.png)

![](./images/相同对象可存在不同的命名空间.png)

### 9.2 作用域

```python
print('--------------------------------作用域----------------------------------')

"""
作用域：
    作用域就是一个 Python 程序可以直接访问命名空间的正文区域。
    在一个 python 程序中，直接访问一个变量，会从内到外依次访问所有的作用域直到找到，否则会报未定义的错误。
    Python 中，程序的变量并不是在哪个位置都可以访问的，访问权限决定于这个变量是在哪里赋值的。
    变量的作用域决定了在哪一部分程序可以访问哪个特定的变量名称。Python的作用域一共有4种，分别是：

    有四种作用域：
        L（Local）：最内层，包含局部变量，比如一个函数/方法内部。
        E（Enclosing）：包含了非局部(non-local)也非全局(non-global)的变量。比如两个嵌套函数，一个函数（或类） A 里面又包含了一个函数 B ，那么对于 B 中的名称来说 A 中的作用域就为 nonlocal。
        G（Global）：当前脚本的最外层，比如当前模块的全局变量。
        B（Built-in）： 包含了内建的变量/关键字等。，最后被搜索
    规则顺序： L –> E –> G –>gt; B。
    在局部找不到，便会去局部外的局部找（例如闭包），再找不到就会去全局找，再者去内置中找
"""
g_count = 0  # 全局作用域


def outer():
    o_count = 1  # 闭包函数外的函数中

    def inner():
        i_count = 2  # 局部作用域


print('------------------------Python 中只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域--------------------------')
"""
Python 中只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域，
其它的代码块（如 if/elif/else/、try/except、for/while等）是不会引入新的作用域的，也就是说这些语句内定义的变量，外部也可以访问，
"""
if True:
    a: int = 2

print(a)


def getA():
    b: int = 2


# 会报错
# print(b)

print('--------------------------------全局变量和局部变量----------------------------------')

"""
全局变量和局部变量
    定义在函数内部的变量拥有一个局部作用域，定义在函数外的拥有全局作用域。
    局部变量只能在其被声明的函数内部访问，而全局变量可以在整个程序范围内访问。调用函数时，所有在函数内声明的变量名称都将被加入到作用域中
"""
# 这是一个全局变量
total = 0


def sum(arg1, arg2):
    # 返回2个参数的和
    # total在这里是局部变量.
    total = arg1 + arg2
    print("函数内是局部变量 : ", total)
    return total


# 调用sum函数
sum(10, 20)
print("函数外是全局变量 : ", total)

print('--------------------------------global 和 nonlocal关键字----------------------------------')

"""
global 和 nonlocal关键字
    当内部作用域想修改外部作用域的变量时，就要用到global和nonlocal关键字了。
"""
print('-------------------------------------')
# 修改全局变量
num = 1


def fun1():
    # 需要使用 global 关键字声明
    global num
    print(num)
    num = 123
    print(num)


fun1()
print(num)
print('-------------------------------------')


# 如果要修改嵌套作用域（enclosing 作用域，外层非全局作用域）中的变量则需要 nonlocal 关键字了
def outer():
    age = 10

    def inner():
        # nonlocal关键字声明
        nonlocal age
        age = 100
        print(age)

    inner()
    print(age)


outer()

print('-------------------------------------')

# a1 = 10
# def test():
# UnboundLocalError: local variable 'a1' referenced before assignment
# 错误信息为局部作用域引用错误，因为 test 函数中的 a 使用的是局部，未定义，无法修改
# a1 = a1 + 1
# print(a1)

# test()

# 修改1
a1 = 10


def test(a1):
    a1 = a1 + 1
    print(a1)


test(a1)

# 修改2
b1 = 10


def test():
    global b1
    b1 = b1 + 1
    print(b1)


test()
```

