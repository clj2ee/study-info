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

