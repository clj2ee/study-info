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
### 1.6 字符串

* Python字符串运算符

| 操作符 | 描述                                                         | 实例                             |
| ------ | ------------------------------------------------------------ | -------------------------------- |
| +      | 字符串连接                                                   | a + b 输出结果： HelloPython     |
| *      | 重复输出字符串                                               | a*2 输出结果：HelloHello         |
| []     | 通过索引获取字符串中字符                                     | a[1] 输出结果 **e**              |
| [ : ]  | 截取字符串中的一部分，遵循**左闭右开**原则，str[0,2] 是不包含第 3 个字符的。 | a[1:4] 输出结果 **ell**          |
| in     | 成员运算符 - 如果字符串中包含给定的字符返回 True             | **'H' in a** 输出结果 True       |
| not in | 成员运算符 - 如果字符串中不包含给定的字符返回 True           | **'M' not in a** 输出结果 True   |
| r/R    | 原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母 **r**（可以大小写）以外，与普通字符串有着几乎完全相同的语法。 | `print( r'\n' ) print( R'\n' ) ` |
| %      | 格式字符串                                                   | 请看下一节内容。                 |

* python字符串格式化符号

| 符   号 | 描述                                 |
| ------- | ------------------------------------ |
| %c      | 格式化字符及其ASCII码                |
| %s      | 格式化字符串                         |
| %d      | 格式化整数                           |
| %u      | 格式化无符号整型                     |
| %o      | 格式化无符号八进制数                 |
| %x      | 格式化无符号十六进制数               |
| %X      | 格式化无符号十六进制数（大写）       |
| %f      | 格式化浮点数字，可指定小数点后的精度 |
| %e      | 用科学计数法格式化浮点数             |
| %E      | 作用同%e，用科学计数法格式化浮点数   |
| %g      | %f和%e的简写                         |
| %G      | %f 和 %E 的简写                      |
| %p      | 用十六进制数格式化变量的地址         |

* Python 的字符串常用内建函数如下

| 序号 | 方法及描述                                                   |
| ---- | ------------------------------------------------------------ |
| 1    | [capitalize()](https://www.runoob.com/python3/python3-string-capitalize.html) 将字符串的第一个字符转换为大写 |
| 2    | [center(width, fillchar)](https://www.runoob.com/python3/python3-string-center.html) 返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。 |
| 3    | [count(str, beg= 0,end=len(string))](https://www.runoob.com/python3/python3-string-count.html) 返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数 |
| 4    | [bytes.decode(encoding="utf-8", errors="strict")](https://www.runoob.com/python3/python3-string-decode.html) Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。 |
| 5    | [encode(encoding='UTF-8',errors='strict')](https://www.runoob.com/python3/python3-string-encode.html) 以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace' |
| 6    | [endswith(suffix, beg=0, end=len(string))](https://www.runoob.com/python3/python3-string-endswith.html) 检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False. |
| 7    | [expandtabs(tabsize=8)](https://www.runoob.com/python3/python3-string-expandtabs.html) 把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。 |
| 8    | [find(str, beg=0, end=len(string))](https://www.runoob.com/python3/python3-string-find.html) 检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1 |
| 9    | [index(str, beg=0, end=len(string))](https://www.runoob.com/python3/python3-string-index.html) 跟find()方法一样，只不过如果str不在字符串中会报一个异常. |
| 10   | [isalnum()](https://www.runoob.com/python3/python3-string-isalnum.html) 如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True,否则返回 False |
| 11   | [isalpha()](https://www.runoob.com/python3/python3-string-isalpha.html) 如果字符串至少有一个字符并且所有字符都是字母则返回 True, 否则返回 False |
| 12   | [isdigit()](https://www.runoob.com/python3/python3-string-isdigit.html) 如果字符串只包含数字则返回 True 否则返回 False.. |
| 13   | [islower()](https://www.runoob.com/python3/python3-string-islower.html) 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False |
| 14   | [isnumeric()](https://www.runoob.com/python3/python3-string-isnumeric.html) 如果字符串中只包含数字字符，则返回 True，否则返回 False |
| 15   | [isspace()](https://www.runoob.com/python3/python3-string-isspace.html) 如果字符串中只包含空白，则返回 True，否则返回 False. |
| 16   | [istitle()](https://www.runoob.com/python3/python3-string-istitle.html) 如果字符串是标题化的(见 title())则返回 True，否则返回 False |
| 17   | [isupper()](https://www.runoob.com/python3/python3-string-isupper.html) 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False |
| 18   | [join(seq)](https://www.runoob.com/python3/python3-string-join.html) 以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串 |
| 19   | [len(string)](https://www.runoob.com/python3/python3-string-len.html) 返回字符串长度 |
| 20   | [ljust(width[, fillchar\])](https://www.runoob.com/python3/python3-string-ljust.html) 返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。 |
| 21   | [lower()](https://www.runoob.com/python3/python3-string-lower.html) 转换字符串中所有大写字符为小写. |
| 22   | [lstrip()](https://www.runoob.com/python3/python3-string-lstrip.html) 截掉字符串左边的空格或指定字符。 |
| 23   | [maketrans()](https://www.runoob.com/python3/python3-string-maketrans.html) 创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。 |
| 24   | [max(str)](https://www.runoob.com/python3/python3-string-max.html) 返回字符串 str 中最大的字母。 |
| 25   | [min(str)](https://www.runoob.com/python3/python3-string-min.html) 返回字符串 str 中最小的字母。 |
| 26   | [replace(old, new [, max\])](https://www.runoob.com/python3/python3-string-replace.html) 把 将字符串中的 str1 替换成 str2,如果 max 指定，则替换不超过 max 次。 |
| 27   | [rfind(str, beg=0,end=len(string))](https://www.runoob.com/python3/python3-string-rfind.html) 类似于 find()函数，不过是从右边开始查找. |
| 28   | [rindex( str, beg=0, end=len(string))](https://www.runoob.com/python3/python3-string-rindex.html) 类似于 index()，不过是从右边开始. |
| 29   | [rjust(width,[, fillchar\])](https://www.runoob.com/python3/python3-string-rjust.html) 返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串 |
| 30   | [rstrip()](https://www.runoob.com/python3/python3-string-rstrip.html) 删除字符串字符串末尾的空格. |
| 31   | [split(str="", num=string.count(str))](https://www.runoob.com/python3/python3-string-split.html) num=string.count(str)) 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串 |
| 32   | [splitlines([keepends\])](https://www.runoob.com/python3/python3-string-splitlines.html) 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。 |
| 33   | [startswith(substr, beg=0,end=len(string))](https://www.runoob.com/python3/python3-string-startswith.html) 检查字符串是否是以指定子字符串 substr 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。 |
| 34   | [strip([chars\])](https://www.runoob.com/python3/python3-string-strip.html) 在字符串上执行 lstrip()和 rstrip() |
| 35   | [swapcase()](https://www.runoob.com/python3/python3-string-swapcase.html) 将字符串中大写转换为小写，小写转换为大写 |
| 36   | [title()](https://www.runoob.com/python3/python3-string-title.html) 返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle()) |
| 37   | [translate(table, deletechars="")](https://www.runoob.com/python3/python3-string-translate.html) 根据 str 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中 |
| 38   | [upper()](https://www.runoob.com/python3/python3-string-upper.html) 转换字符串中的小写字母为大写 |
| 39   | [zfill (width)](https://www.runoob.com/python3/python3-string-zfill.html) 返回长度为 width 的字符串，原字符串右对齐，前面填充0 |
| 40   | [isdecimal()](https://www.runoob.com/python3/python3-string-isdecimal.html) 检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。 |

```python
"""
@Time           : 2019-11-01 23:10
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : String.py
@Software       : PyCharm
"""

"""
字符串：
    字符串是 Python 中最常用的数据类型。我们可以使用引号( ' 或 " )来创建字符串。
    
    Python 访问字符串中的值
        Python 不支持单字符类型，单字符在 Python 中也是作为一个字符串使用。
        Python 访问子字符串，可以使用方括号来截取字符串
"""
var1 = 'Hello World!'
var2 = "Runoob"

print("var1[0]: ", var1[0])
print("var2[1:5]: ", var2[1:5])

# Python 字符串更新
# 你可以截取字符串的一部分并与其他字段拼接
var1 = 'Hello World!'
print("已更新字符串 : ", var1[:6] + 'Runoob!')
print('--------------------------------------------------')

# Python转义字符
# 在需要在字符中使用特殊字符时，python用反斜杠(\)转义字符
print('\\')
print('--------------------------------------------------')

# Python字符串运算符
a = "Hello"
b = "Python"

print("a + b 输出结果：", a + b)
print("a * 2 输出结果：", a * 2)
# 通过索引获取字符串中字符
print("a[1] 输出结果：", a[1])
# 截取字符串中的一部分，遵循左闭右开原则，str[0,2] 是不包含第 3 个字符的
print("a[1:4] 输出结果：", a[1:4])

if "H" in a:
    print("H 在变量 a 中")
else:
    print("H 不在变量 a 中")

if "M" not in a:
    print("M 不在变量 a 中")
else:
    print("M 在变量 a 中")

print('\r')
print(r'\r')
print(R'\n')
print('--------------------------------------------------')

# Python字符串格式化
# Python 支持格式化字符串的输出 。尽管这样可能会用到非常复杂的表达式，但最基本的用法是将一个值插入到一个有字符串格式符 %s 的字符串中。
# 在 Python 中，字符串格式化使用与 C 中 sprintf 函数一样的语法

print("我叫 %s 今年 %d 岁!" % ('小明', 10))
print('--------------------------------------------------')

# Python三引号
# python三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符
para_str = """这是一个多行字符串的实例
多行字符串可以使用制表符
TAB ( \t )。
也可以使用换行符 [ \n ]。
"""
print(para_str)

# 三引号让程序员从引号和特殊字符串的泥潭里面解脱出来，自始至终保持一小块字符串的格式是所谓的WYSIWYG（所见即所得）格式的。
# 一个典型的用例是，当你需要一块HTML或者SQL时，这时用字符串组合，特殊字符串转义将会非常的繁琐
errHTML = '''
<HTML><HEAD><TITLE>
Friends CGI Demo</TITLE></HEAD>
<BODY><H3>ERROR</H3>
<B>%s</B><P>
<FORM><INPUT TYPE=button VALUE=Back
ONCLICK="window.history.back()"></FORM>
</BODY></HTML>
'''
# cursor.execute('''
# CREATE TABLE users (
# login VARCHAR(8),
# uid INTEGER,
# prid INTEGER)
# ''')

# Unicode 字符串
# 在Python2中，普通字符串是以8位ASCII码进行存储的，而Unicode字符串则存储为16位unicode字符串，这样能够表示更多的字符集。使用的语法是在字符串前面加上前缀 u。
# 在Python3中，所有的字符串都是Unicode字符串。
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
    print(datetime, err)

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

## 10 常用的python库
```python
"""
@Time           : 2019-10-24 21:54
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : os.py
@Software       : PyCharm
"""
"""
操作系统标准接口：
    os模块提供了过多与操作系统相关联的函数
"""

import os
import shutil
import glob
import sys
import math
import random
from urllib.request import urlopen
import smtplib
import datetime
import time
import zlib
from timeit import Timer

print('当前工作目录：', os.getcwd())

# 修改当前的工作目录
# os.chdir('/ server / accesslogs')

# 执行操作系统命令
os.system('dir')

# 导入关闭
shutil.copy('./os.py', './os1.py')
shutil.move('./os1.py', '../os1.py')

"""
文件通配符
"""
# glob模块提供了一个函数用于从目录通配符搜索中生成文件列表：
print(glob.glob('*.py'))

"""
命令行参数
"""
print(sys.argv)

# 错误输出重置和程序终止
# sys还有stdin，stdout和stderr属性，甚至在stdout被重定向时，另外也可以用于显示警告和错误信息。
# sys.stderr.write("警告，未找到开始新文件的日志文件")
# sys.stdin.write("警告，未找到开始新文件的日志文件")
# sys.stdout.write("警告，未找到开始新文件的日志文件")

# 大部分脚本的定向终止都使用“ sys.exit（）”。

"""
数学
    math模块为浮点运算提供了对扩展C函数库的访问
"""
print(math.cos(math.pi / 4))
print(math.log(1024, 2))

# random提供了生成随机数的工具。
print(random.choice(['dell', 'lenovo', 'hp', 'mac']))

# 采样而不替换
print(random.sample(range(100), 10))
# 随机浮点数
print(random.random())
# randrange(x)从x随机整数
print(random.randrange(39))

"""
访问互联网
"""
# 其中一些最简单的两个是用于处理从url的接收的数据的urllib.request以及用于发送电子邮件的smtplib：
print(urlopen('https://www.baidu.com'))

# 注意需要本地有一个在运行的邮件服务器。
# smtp = smtplib.SMTP("localhost")
# smtp.sendmail('clj2ee@163.com', 'l058805540@qq.com', 'Python学习')
# smtp.quit()

"""
日期和时间
    datetime模块为日期和时间处理同时提供了简单和复杂的方法。
    支持日期和时间算法的同时，实现的重点放在更有效的处理和格式化输出。
    该模块还支持时区处理：
"""
print(datetime.date.today())
print(datetime.date(2019, 10, 24))

t = "2017-11-24 17:30:00"
# 将其转换为时间数组
timeStruct = time.strptime(t, "%Y-%m-%d %H:%M:%S")
# 转换为时间戳:
timeStamp = int(time.mktime(timeStruct))
print(timeStamp)

timeStamp = 1511515800
localTime = time.localtime(timeStamp)
strTime = time.strftime("%Y-%m-%d %H:%M:%S", localTime)
print(strTime)

"""
数据压缩
    以下模块直接支持通用的数据打包和压缩格式：zlib，gzip，bz2，zipfile和tarfile
"""

"""
性能指标
    有些用户对了解解决同一问题的不同方法之间的性能差异很感兴趣。Python提供了一个刻度工具，为这些问题提供了直接答案。
例如，使用元组封装和拆封来交换元素看起来要比使用传统的方法要诱人的多，timeit证明了现代的方法重启一些
"""
print(Timer('t = a; a = b; b = t', 'a = 1; b = 2').timeit())

"""
测试模块
    开发出色软件的方法之一是为每一个函数开发测试代码，并且在开发过程中经常进行测试
    doctest模块提供了一个工具，扫描模块并根据程序中内嵌的文档字符串执行测试。
    测试构造经典简单的将它的输出结果剪切并粘贴到文档字符串中。
    通过用户提供的示例，它强化了文档，允许doctest模块确认代码的结果是否与文档一致
"""

# 其它模块见文档
```

## 11 正则表达式
### 11.1 正则表达式修饰符——可选标志
> 正则表达式可以包含一些可选标志修饰符来控制匹配的模式。修饰符被指定为一个可选的标志。多个标志可以通过按位 OR(|) 它们来指定。如 re.I | re.M 被设置成 I 和 M 标志：

|修饰符|描述|
|----|----|
|re.I	|使匹配对大小写不敏感|
|re.L	|做本地化识别（locale-aware）匹配|
|re.M	|多行匹配，影响 ^ 和 $|
|re.S	|使 . 匹配包括换行在内的所有字符|
|re.U	|根据Unicode字符集解析字符。这个标志影响 \w, \W, \b, \B.|
|re.X	|该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。|

```python
"""
@Time           : 2019-10-26 09:15
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : RegularExpression.py
@Software       : PyCharm
"""
"""
正则表达式：
    ? 和 * 通配符来查找硬盘上的文件。? 通配符匹配文件名中的 0 个或 1 个字符，而 * 通配符匹配零个或多个字符
    用 * 字符代替 ? 字符扩大了找到匹配的数量
"""

'''
    ^[0-9] + abc$
        ^ 为匹配输入字符串的开始位置。
        [0-9]+匹配多个数字， [0-9] 匹配单个数字，+ 匹配一个或者多个。
        abc$匹配字母 abc 并以 abc 结尾，$ 为匹配输入字符串的结束位置。
        
        
只允许用户名包含字符、数字、下划线和连接字符(-)，并设置用户名的长度
    ^[a-z0-9_-]{3,5}$
'''
import re

# re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match()就返回none。
ma = '^[a-z0-9_-]{3,5}$'
print(re.match(ma, 'sss').span())
print('---------------------------------------------------------------')

# re.search 扫描整个字符串并返回第一个成功的匹配。

# group(num=0)	匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。
# groups()	返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。
line = "Cats are smarter than dogs"
searchObj = re.search(r'(.*) are (.*?) .*', line, re.M | re.I)

if searchObj:
    print("searchObj.group() : ", searchObj.group())
    print("searchObj.group(1) : ", searchObj.group(1))
    print("searchObj.group(2) : ", searchObj.group(2))
    print("searchObj.groups() : ", searchObj.groups())
else:
    print("Nothing found!!")

print('---------------------------------------------------------------')

# re.match与re.search的区别
# re.match只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回None；而re.search匹配整个字符串，直到找到一个匹配。

line = "Cats are smarter than dogs";

matchObj = re.match(r'dogs', line, re.M | re.I)
if matchObj:
    print("match --> matchObj.group() : ", matchObj.group())
else:
    print("No match!!")

matchObj = re.search(r'dogs', line, re.M | re.I)
if matchObj:
    print("search --> matchObj.group() : ", matchObj.group())
else:
    print("No match!!")
print('---------------------------------------------------------------')

'''
检索和替换
    Python 的re模块提供了re.sub用于替换字符串中的匹配项。
    re.sub(pattern, repl, string, count=0, flags=0)
    参数：
    pattern : 正则中的模式字符串。
    repl : 替换的字符串，也可为一个函数。
    string : 要被查找替换的原始字符串。
    count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。
    flags : 编译时用的匹配模式，数字形式。
    前三个为必选参数，后两个为可选参数。
'''
phone = "2004-959-559 # 这是一个电话号码"

# 删除注释
num = re.sub(r'#.*$', "", phone)
print("电话号码 : ", num)

# 移除非数字的内容
num = re.sub(r'\D', "", phone)
print("电话号码 : ", num)


# 将匹配的数字乘于 2
def double(matched):
    """
    :param matched:
    :return:
    """
    value = int(matched.group('value'))
    return str(value * 2)


s = 'A23G4HFD567'
print(re.sub('(?P<value>\d+)', double, s))
print('---------------------------------------------------------------')

"""
compile 函数
compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。

语法格式为：
    re.compile(pattern[, flags])
    参数：
        pattern : 一个字符串形式的正则表达式
        flags 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：
        re.I 忽略大小写
        re.L 表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境
        re.M 多行模式
        re.S 即为' . '并且包括换行符在内的任意字符（' . '不包括换行符）
        re.U 表示特殊字符集 \w, \W, \b, \B, \d, \D, \s, \S 依赖于 Unicode 字符属性数据库
        re.X 为了增加可读性，忽略空格和' # '后面的注释
"""
pattern = re.compile(r'\d+')
m = pattern.match('one12twothree34four')
print(m)
print(pattern.match('one12twothree34four', 3, 10))
print(pattern.search('one12twothree34four').group())

# 忽略大小写
pattern = re.compile(r'([a-z]+) ([a-z]+)', re.I)
m = pattern.match('Hello World Wide Web')
print(m)
# 返回匹配成功的整个子串
print(m.group())
# m.groups()等价于 (m.group(1), m.group(2), ...)
print(m.groups())
print('---------------------------------------------------------------')

"""
findall
在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果没有找到匹配的，则返回空列表。
注意： match 和 search 是匹配一次 findall 匹配所有。
    语法格式为：
        re.findall(string[, pos[, endpos]])
    参数：
        string 待匹配的字符串。
        pos 可选参数，指定字符串的起始位置，默认为 0。
        endpos 可选参数，指定字符串的结束位置，默认为字符串的长度。
"""
# 查找数字
pattern = re.compile(r'\d+')
result1 = pattern.findall('runoob 123 google 456')
result2 = pattern.findall('run88oob123google456', 0, 10)

print(result1)
print(result2)

# re.finditer
# 和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。

finditer = pattern.finditer('run88oob123google456', 0, 10)
for iterm in finditer:
    print(iterm)
    print(iterm.group())

print('---------------------------------------------------------------')

"""
re.split
split 方法按照能够匹配的子串将字符串分割后返回列表，它的使用形式如下：
    re.split(pattern, string[, maxsplit=0, flags=0])
    参数：
        参数	描述
        pattern	匹配的正则表达式
        string	要匹配的字符串。
        maxsplit	分隔次数，maxsplit=1 分隔一次，默认为 0，不限制次数。
        flags	标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：正则表达式修饰符 - 可选标志
"""
print(re.split('\W+', 'runoob, runoob, runoob.'))
```

## 12 mysql
### 12.1 安装mysql connector
    需要更换镜像源:
        C:\Users\程林\AppData\Roaming\pip\pip.ini
        如果没有改文件夹和文件，就新建
        pip.ini的内容设置为：
            [global] 
            index-url = http://mirrors.aliyun.com/pypi/simple/ 
            [install] 
            trusted-host=mirrors.aliyun.com
        可以使用其他镜像源
 python -m pip install mysql-connector

### 12.2 Python使用mysql
```python
"""
@Time           : 2019-10-26 22:54
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Mysql.py
@Software       : PyCharm
"""
"""
    Python MySQL - mysql-connector 驱动
    使用 mysql-connector 来连接使用 MySQL， mysql-connector 是 MySQL 官方提供的驱动器。
    命令：python -m pip install mysql-connector
"""
import mysql.connector

mydb = mysql.connector.connect(
    host="xxx.xxx.xxx.xxx",  # 数据库主机地址
    user="admin",  # 数据库用户名
    passwd="admin"  # 数据库密码
)

print(mydb)
cursor = mydb.cursor()

# 执行sql语句
print('----------------------------------------------')
cursor.execute('show databases')
for c in cursor:
    print(c)

print('----------------------------------------------')

# 指定数据库
test_db = mysql.connector.connect(
    host="xxx.xxx.xxx.xxx",  # 数据库主机地址
    user="admin",  # 数据库用户名
    passwd="admin",  # 数据库密码
    database="test_db"
)
test_cursor = test_db.cursor()

# 查询所有的表
blog_cursor.execute("SHOW TABLES")

for x in blog_cursor:
    print(x)

print('-------------------查询表结构---------------------------')
# 查询表结构
blog_cursor.execute("desc t_blogtype")
for y in blog_cursor:
    print(y)

print('-----------------------创建表--------------------')

# 创建表
# blog_cursor.execute("CREATE TABLE `sites` (name VARCHAR(255), url VARCHAR(255))")

# 插入数据
print('---------------------插入数据---------------------')
sql = "INSERT INTO t_blogtype (typeName, orderNum) VALUES (%s, %s)"
val = ("RUNOOB", 30)
blog_cursor.execute(sql, val)
# 数据表内容有更新，必须使用到该语句
db_blog.commit()
print("1 条记录已插入, ID:", blog_cursor.lastrowid)

# 批量插入
# 批量插入使用 executemany() 方法，该方法的第二个参数是一个元组列表，包含了我们要插入的数据：
batchSql = "INSERT INTO t_blogtype (typeName, orderNum) VALUES (%s, %s)"
val = [
    ('Google', 4),
    ('Github', 6),
    ('Taobao', 8),
    ('stackoverflow', 9)
]
blog_cursor.executemany(batchSql, val)
mydb.commit()

print('--------------------查询--------------------------')
# 查询
sql = 'SELECT * FROM `t_blogtype`'
blog_cursor.execute(sql)
# fetchall() 获取所有记录
fetchall = blog_cursor.fetchall()

for x in fetchall:
    print(x)

# where 条件查询

# order by

# group by

# limit




```


## 13 PyMysql
```python
"""
@Time           : 2019-11-01 22:50
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : PyMysql.py
@Software       : PyCharm
"""
"""
什么是 PyMySQL？
    PyMySQL 是在 Python3.x 版本中用于连接 MySQL 服务器的一个库，Python2中则使用mysqldb。
    PyMySQL 遵循 Python 数据库 API v2.0 规范，并包含了 pure-Python MySQL 客户端库。
"""
import pymysql

# 打开数据库连接
db = pymysql.connect("106.14.112.147", "root", "toor", "db_blog")

# 使用 cursor() 方法创建一个游标对象 cursor
cursor = db.cursor()

# 使用 execute()  方法执行 SQL 查询
cursor.execute("SELECT VERSION()")

# 使用 fetchone() 方法获取单条数据.
data = cursor.fetchone()

print("Database version : %s " % data)

"""
插入:

"""

# SQL 插入语句
sql = "INSERT INTO t_blogtype (typeName, orderNum) VALUES  ('Google', 4)"
# SQL 插入语句
# sql = "INSERT INTO t_blogtype (typeName, orderNum) VALUES (%s, %d)" % ('Github', 6)
try:
    # 执行sql语句
    cursor.execute(sql)
    # 提交到数据库执行
    db.commit()
except:
    # 如果发生错误则回滚
    db.rollback()

# 关闭数据库连接
db.close()

```

## 14  网络编程

### 14.1 Socket 对象(内建)方法

| 函数                                 | 描述                                                         |
| ------------------------------------ | ------------------------------------------------------------ |
| 服务器端套接字                       |                                                              |
| s.bind()                             | 绑定地址（host,port）到套接字， 在AF_INET下,以元组（host,port）的形式表示地址。 |
| s.listen()                           | 开始TCP监听。backlog指定在拒绝连接之前，操作系统可以挂起的最大连接数量。该值至少为1，大部分应用程序设为5就可以了。 |
| s.accept()                           | 被动接受TCP客户端连接,(阻塞式)等待连接的到来                 |
| 客户端套接字                         |                                                              |
| s.connect()                          | 主动初始化TCP服务器连接，。一般address的格式为元组（hostname,port），如果连接出错，返回socket.error错误。 |
| s.connect_ex()                       | connect()函数的扩展版本,出错时返回出错码,而不是抛出异常      |
| 公共用途的套接字函数                 |                                                              |
| s.recv()                             | 接收TCP数据，数据以字符串形式返回，bufsize指定要接收的最大数据量。flag提供有关消息的其他信息，通常可以忽略。 |
| s.send()                             | 发送TCP数据，将string中的数据发送到连接的套接字。返回值是要发送的字节数量，该数量可能小于string的字节大小。 |
| s.sendall()                          | 完整发送TCP数据，完整发送TCP数据。将string中的数据发送到连接的套接字，但在返回之前会尝试发送所有数据。成功返回None，失败则抛出异常。 |
| s.recvfrom()                         | 接收UDP数据，与recv()类似，但返回值是（data,address）。其中data是包含接收数据的字符串，address是发送数据的套接字地址。 |
| s.sendto()                           | 发送UDP数据，将数据发送到套接字，address是形式为（ipaddr，port）的元组，指定远程地址。返回值是发送的字节数。 |
| s.close()                            | 关闭套接字                                                   |
| s.getpeername()                      | 返回连接套接字的远程地址。返回值通常是元组（ipaddr,port）。  |
| s.getsockname()                      | 返回套接字自己的地址。通常是一个元组(ipaddr,port)            |
| s.setsockopt(level,optname,value)    | 设置给定套接字选项的值。                                     |
| s.getsockopt(level,optname[.buflen]) | 返回套接字选项的值。                                         |
| s.settimeout(timeout)                | 设置套接字操作的超时期，timeout是一个浮点数，单位是秒。值为None表示没有超时期。一般，超时期应该在刚创建套接字时设置，因为它们可能用于连接的操作（如connect()） |
| s.gettimeout()                       | 返回当前超时期的值，单位是秒，如果没有设置超时期，则返回None。 |
| s.fileno()                           | 返回套接字的文件描述符。                                     |
| s.setblocking(flag)                  | 如果flag为0，则将套接字设为非阻塞模式，否则将套接字设为阻塞模式（默认值）。非阻塞模式下，如果调用recv()没有发现任何数据，或send()调用无法立即发送数据，那么将引起socket.error异常。 |
| s.makefile()                         | 创建一个与该套接字相关连的文件                               |

```python
"""
@Time           : 2019-11-02 00:14
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Network.py
@Software       : PyCharm
"""
"""
网络编程：
    Python 提供了两个级别访问的网络服务。：
        低级别的网络服务支持基本的 Socket，它提供了标准的 BSD Sockets API，可以访问底层操作系统Socket接口的全部方法。
        高级别的网络服务模块 SocketServer， 它提供了服务器中心类，可以简化网络服务器的开发
        
    什么是 Socket?
        Socket又称"套接字"，应用程序通常通过"套接字"向网络发出请求或者应答网络请求，使主机间或者一台计算机上的进程间可以通讯。
    
    socket()函数
    Python 中，我们用 socket（）函数来创建套接字，语法格式如下：
        socket.socket([family[, type[, proto]]])
        参数
        family: 套接字家族可以使AF_UNIX或者AF_INET
        type: 套接字类型可以根据是面向连接的还是非连接分为SOCK_STREAM或SOCK_DGRAM
        protocol: 一般不填默认为0.
"""

"""
服务端
    我们使用 socket 模块的 socket 函数来创建一个 socket 对象。socket 对象可以通过调用其他函数来设置一个 socket 服务。
    现在我们可以通过调用 bind(hostname, port) 函数来指定服务的 port(端口)。
    接着，我们调用 socket 对象的 accept 方法。该方法等待客户端的连接，并返回 connection 对象，表示已连接到客户端。
"""
import socket
import sys

# 1 创建socket对象
serverSocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# 2 绑定端口号
# 绑定地址（host,port）到套接字， 在AF_INET下,以元组（host,port）的形式表示地址。
serverSocket.bind((socket.gethostname(), 9999))

# 3 设置最大连接数，超过后排队
# 开始TCP监听。backlog指定在拒绝连接之前，操作系统可以挂起的最大连接数量。该值至少为1，大部分应用程序设为5就可以了。
serverSocket.listen(5)

while True:
    # 建立客户端连接,被动接受TCP客户端连接,(阻塞式)等待连接的到来
    clientSocket, addr = serverSocket.accept()

    print("连接地址: %s" % str(addr))

    msg = '欢迎访问菜鸟教程'
    clientSocket.send(msg.encode('utf-8'))
    clientSocket.close()

"""
客户端
    接下来我们写一个简单的客户端实例连接到以上创建的服务。端口号为 9999。
    socket.connect(hosname, port ) 方法打开一个 TCP 连接到主机为 hostname 端口为 port 的服务商。连接后我们就可以从服务端获取数据，记住，操作完成后需要关闭连接。
"""
import socket
import sys

# 1 创建socket对象
clientSocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# 2 连接服务，指定主机和端口
# 主动初始化TCP服务器连接，。一般address的格式为元组（hostname,port），如果连接出错，返回socket.error错误。
clientSocket.connect((socket.gethostname(), 9999))

# 3 接收小于 1024 字节的数据
# 接收TCP数据，数据以字符串形式返回，bufsize指定要接收的最大数据量。flag提供有关消息的其他信息，通常可以忽略。
msg = clientSocket.recv(1024)

# 4 关闭连接,关闭套接字
clientSocket.close()

print(msg.decode('utf-8'))

```

### 14.2 Python Internet 模块

以下列出了 Python 网络编程的一些重要模块：

| 协议   | 功能用处                         | 端口号 | Python 模块                |
| ------ | -------------------------------- | ------ | -------------------------- |
| HTTP   | 网页访问                         | 80     | httplib, urllib, xmlrpclib |
| NNTP   | 阅读和张贴新闻文章，俗称为"帖子" | 119    | nntplib                    |
| FTP    | 文件传输                         | 20     | ftplib, urllib             |
| SMTP   | 发送邮件                         | 25     | smtplib                    |
| POP3   | 接收邮件                         | 110    | poplib                     |
| IMAP4  | 获取邮件                         | 143    | imaplib                    |
| Telnet | 命令行                           | 23     | telnetlib                  |
| Gopher | 信息查找                         | 70     | gopherlib, urllib          |

## 15 STMP发送邮件
```python
"""
@Time           : 2019-11-03 14:53
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Smtp.py
@Software       : PyCharm
"""
"""
Python3 SMTP发送邮件
    SMTP（Simple Mail Transfer Protocol）即简单邮件传输协议,它是一组用于由源地址到目的地址传送邮件的规则，由它来控制信件的中转方式。
    python的smtplib提供了一种很方便的途径发送电子邮件。它对smtp协议进行了简单的封装。

    Python创建 SMTP 对象语法如下：
    import smtplib
    smtpObj = smtplib.SMTP( [host [, port [, local_hostname]]] )
    参数说明：
        host: SMTP 服务器主机。 你可以指定主机的ip地址或者域名如:runoob.com，这个是可选参数。
        port: 如果你提供了 host 参数, 你需要指定 SMTP 服务使用的端口号，一般情况下SMTP端口号为25。
        local_hostname: 如果SMTP在你的本机上，你只需要指定服务器地址为 localhost 即可。
    
    Python SMTP对象使用sendmail方法发送邮件，语法如下：
    SMTP.sendmail(from_addr, to_addrs, msg[, mail_options, rcpt_options]
    参数说明：
        from_addr: 邮件发送者地址。
        to_addrs: 字符串列表，邮件发送地址。
        msg: 发送消息
    这里要注意一下第三个参数，msg是字符串，表示邮件。我们知道邮件一般由标题，发信人，收件人，邮件内容，附件等构成，发送邮件的时候，要注意msg的格式。这个格式就是smtp协议中定义的格式。
"""

# 如果我们本机没有 sendmail 访问，也可以使用其他服务商的 SMTP 访问（QQ、网易、Google等）。

import smtplib
from email.mime.text import MIMEText
from email.header import Header
from email.mime.multipart import MIMEMultipart
from email.mime.image import MIMEImage

print('1 简单邮件发送，2 发送html邮件，3 发送带附件的邮件，4 在 HTML 文本中添加图片')
data = input('please input:\n>>>')

# 第三方 SMTP 服务
mail_host = "smtp.qq.com"  # 设置服务器
mail_user = "xxxx@qq.com"  # 用户名
mail_pass = "ccccc"  # 口令

sender = 'xxxx@qq.com'
# 接收邮件，可设置为你的QQ邮箱或者其他邮箱
receivers = ('xxx@163.com')

if data == '1':

    content = 'Python 邮件发送测试...'

    # 标准邮件需要三个头部信息： From, To, 和 Subject ，每个信息直接使用空行分割。
    subject = 'Python SMTP 邮件测试'
    message = MIMEText(content, 'plain', 'utf-8')
    message['Subject'] = Header(subject, 'utf-8')
    # message['From'] = Header("cl", 'utf-8')
    # message['To'] = Header("clj2ee", 'utf-8')
    message['From'] = sender
    message['To'] = receivers

    try:
        smtpObj = smtplib.SMTP()
        smtpObj.connect(mail_host, 25)  # 25 为 SMTP 端口号
        smtpObj.login(mail_user, mail_pass)
        smtpObj.sendmail(sender, receivers, message.as_string())
        print("邮件发送成功")
    except smtplib.SMTPException:
        print("Error: 无法发送邮件")
elif data == '2':

    # 读取html文件内容
    f = open('index.html', 'rb')  # HTML文件默认和当前文件在同一路径下，若不在同一路径下，需要指定要发送的HTML文件的路径
    mail_body = f.read()
    f.close()

    message = MIMEText(mail_body, 'html', 'utf-8')
    subject = 'Python SMTP html邮件测试'
    message['Subject'] = Header(subject, 'utf-8')
    message['From'] = sender
    message['To'] = receivers

    try:
        smtpObj = smtplib.SMTP()
        smtpObj.set_debuglevel(1)
        smtpObj.connect(mail_host, 25)
        smtpObj.login(mail_user, mail_pass)
        smtpObj.sendmail(sender, receivers, message.as_string())
        print("邮件发送成功")
    except smtplib.SMTPException:
        print("Error: 无法发送邮件")
elif data == '3':
    # 创建一个带附件的实例
    message = MIMEMultipart()
    subject = 'Python SMTP 附件邮件测试'
    message['Subject'] = Header(subject, 'utf-8')
    message['From'] = sender
    message['To'] = receivers

    # 邮件正文内容
    message.attach(MIMEText('这是菜鸟教程Python 邮件发送测试……', 'plain', 'utf-8'))

    # 构造附件1，传送当前目录下的 test.txt 文件
    att1 = MIMEText(open('E:/project-group/python-project/foo1.txt', 'rb').read(), 'base64', 'utf-8')
    att1["Content-Type"] = 'application/octet-stream'
    # 这里的filename可以任意写，写什么名字，邮件中显示什么名字
    att1["Content-Disposition"] = 'attachment; filename="foo1.txt"'
    message.attach(att1)

    # 构造附件2，传送当前目录下的 foo3.txt 文件
    att2 = MIMEText(open('E:/project-group/python-project/foo3.txt', 'rb').read(), 'base64', 'utf-8')
    att2["Content-Type"] = 'application/octet-stream'
    att2["Content-Disposition"] = 'attachment; filename="foo3.txt"'
    message.attach(att2)

    try:
        smtpObj = smtplib.SMTP()
        smtpObj.connect(mail_host, 25)
        smtpObj.login(mail_user, mail_pass)
        smtpObj.sendmail(sender, receivers, message.as_string())
        print("邮件发送成功")
    except smtplib.SMTPException:
        print("Error: 无法发送邮件")
elif data == '4':
    msgRoot = MIMEMultipart('related')
    msgRoot['From'] = sender
    msgRoot['To'] = receivers
    subject = 'Python SMTP html中图片邮件测试'
    msgRoot['Subject'] = Header(subject, 'utf-8')

    msgAlternative = MIMEMultipart('alternative')
    msgRoot.attach(msgAlternative)

    mail_msg = """
    <p>Python 邮件发送测试...</p>
    <p color='red'><a href="http://www.baidu.com">百度</a></p>
    <p>图片演示：</p>
    <p><img src="cid:image1"></p>
    """
    msgAlternative.attach(MIMEText(mail_msg, 'html', 'utf-8'))

    # 指定图片为当前目录
    fp = open('C:/Users/程林/Pictures/Saved Pictures/0007.jpg', 'rb')
    msgImage = MIMEImage(fp.read())
    fp.close()

    # 定义图片 ID，在 HTML 文本中引用2
    msgImage.add_header('Content-ID', '<image1>')
    msgRoot.attach(msgImage)

    try:
        smtpObj = smtplib.SMTP()
        smtpObj.connect(mail_host, 25)
        smtpObj.login(mail_user, mail_pass)
        smtpObj.sendmail(sender, receivers, msgRoot.as_string())
        print("邮件发送成功")
    except smtplib.SMTPException:
        print("Error: 无法发送邮件")
else:
    print('没有该类型的邮件')

```


## 16 Python3多线程
### 16.1 多线程定义
```python
"""
@Time           : 2019-11-03 19:52
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Thread.py
@Software       : PyCharm
"""
"""
多线程：
  多线程类似于同时执行多个不同程序，多线程运行有如下优点：
        使用线程可以把占据长时间的程序中的任务放到后台去处理。
        用户界面可以更加吸引人，比如用户点击了一个按钮去触发某些事件的处理，可以弹出一个进度条来显示处理的进度。
        程序的运行速度可能加快。
        在一些等待的任务实现上如用户输入、文件读写和网络收发数据等，线程就比较有用了。在这种情况下我们可以释放一些珍贵的资源如内存占用等等。
        每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。

  每个线程都有他自己的一组CPU寄存器，称为线程的上下文，该上下文反映了线程上次运行该线程的CPU寄存器的状态。
  指令指针和堆栈指针寄存器是线程上下文中两个最重要的寄存器，线程总是在进程得到上下文中运行的，这些地址都用于标志拥有线程的进程地址空间中的内存。
        线程可以被抢占（中断）。
        在其他线程正在运行时，线程可以暂时搁置（也称为睡眠） -- 这就是线程的退让。

  线程可以分为:
        内核线程：由操作系统内核创建和撤销。
        用户线程：不需要内核支持而在用户程序中实现的线程。

  Python3 线程中常用的两个模块为：
    _thread
    threading(推荐使用)
    
    thread 模块已被废弃。用户可以使用 threading 模块代替。所以，在 Python3 中不能再使用"thread" 模块。为了兼容性，Python3 将 thread 重命名为 "_thread"。  
"""

"""
Python中使用线程有两种方式：函数或者用类来包装线程对象。

    函数式：调用 _thread 模块中的start_new_thread()函数来产生新线程。语法如下:
        _thread.start_new_thread ( function, args[, kwargs] )
        参数说明:
            function - 线程函数。
            args - 传递给线程函数的参数,他必须是个tuple类型。
            kwargs - 可选参数。
"""
import _thread
import time


# 为线程定义一个函数
def print_time(threadName, delay):
    """
    :param threadName:
    :param delay:
    """
    count = 0
    while count < 5:
        time.sleep(delay)
        count += 1
        print("%s: %s" % (threadName, time.ctime(time.time())))


# 创建两个线程
try:
    _thread.start_new_thread(print_time, ("Thread-1", 2,))
    _thread.start_new_thread(print_time, ("Thread-2", 4,))
except:
    print("Error: 无法启动线程")

while True:
    pass

```
### 16.2 Python3中的线程模块
```python
"""
@Time           : 2019-11-06 21:43
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : Threading.py
@Software       : PyCharm
"""

"""
线程模块
 Python3 通过两个标准库 _thread 和 threading 提供对线程的支持。
 _thread 提供了低级别的、原始的线程以及一个简单的锁，它相比于 threading 模块的功能还是比较有限的。
 threading 模块除了包含 _thread 模块中的所有方法外，还提供的其他方法：
      threading.currentThread(): 返回当前的线程变量。
      threading.enumerate(): 返回一个包含正在运行的线程的list。正在运行指线程启动后、结束前，不包括启动前和终止后的线程。
      threading.activeCount(): 返回正在运行的线程数量，与len(threading.enumerate())有相同的结果。
 除了使用方法外，线程模块同样提供了Thread类来处理线程，Thread类提供了以下方法:
      run(): 用以表示线程活动的方法。
      start():启动线程活动。
      join([time]): 等待至线程中止。这阻塞调用线程直至线程的join() 方法被调用中止-正常退出或者抛出未处理的异常-或者是可选的超时发生。
      isAlive(): 返回线程是否活动的。
      getName(): 返回线程名。
      setName(): 设置线程名。

使用 threading 模块创建线程
    我们可以通过直接从 threading.Thread 继承创建一个新的子类，并实例化后调用 start() 方法启动新线程，即它调用了线程的 run() 方法
"""
import threading
import time

exitFlag = 0


# 继承 threading.Thread
class myThread(threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter

    def run(self):
        print("开始线程：" + self.name)
        print_time(self.name, self.counter, 5)
        print("退出线程：" + self.name)


def print_time(threadName, delay, counter):
    """
    :param threadName:
    :param delay:
    :param counter:
    """
    while counter:
        if exitFlag:
            threadName.exit()
        time.sleep(delay)
        print("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1


# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()
thread1.join()
thread2.join()
print("退出主线程")

```
### 16.3 线程同步
```python
"""
@Time           : 2019-11-06 21:51
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : ThreadSynchronize.py
@Software       : PyCharm
"""
"""
线程同步：
    如果多个线程共同对某个数据修改，则可能出现不可预料的结果，为了保证数据的正确性，需要对多个线程进行同步。
    使用 Thread 对象的 Lock 和 Rlock 可以实现简单的线程同步，这两个对象都有 acquire 方法和 release 方法，
    对于那些需要每次只允许一个线程操作的数据，可以将其操作放到 acquire 和 release 方法之间。如下：

    多线程的优势在于可以同时运行多个任务（至少感觉起来是这样）。但是当线程需要共享数据时，可能存在数据不同步的问题。考虑这样一种情况：
    一个列表里所有元素都是0，线程"set"从后向前把所有元素改成1，而线程"print"负责从前往后读取列表并打印。
    那么，可能线程"set"开始改的时候，线程"print"便来打印列表了，输出就成了一半0一半1，这就是数据的不同步。为了避免这种情况，引入了锁的概念。
    锁有两种状态——锁定和未锁定。每当一个线程比如"set"要访问共享数据时，必须先获得锁定；如果已经有别的线程比如"print"获得锁定了，那么就让线程"set"暂停，也就是同步阻塞；等到线程"print"访问完毕，释放锁以后，再让线程"set"继续。
    经过这样的处理，打印列表时要么全部输出0，要么全部输出1，不会再出现一半0一半1的尴尬场面。
"""
import threading
import time


class myThread(threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter

    def run(self):
        print("开启线程： " + self.name)
        # 获取锁，用于线程同步
        threadLock.acquire()
        print_time(self.name, self.counter, 3)
        # 释放锁，开启下一个线程
        threadLock.release()


def print_time(threadName, delay, counter):
    """
    :param threadName:
    :param delay:
    :param counter:
    """
    while counter:
        time.sleep(delay)
        print("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1


threadLock = threading.Lock()
threads = []

# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()

# 添加线程到线程列表
threads.append(thread1)
threads.append(thread2)

# 等待所有线程完成
for t in threads:
    t.join()
print("退出主线程")

```
### 16.4 线程优先级队列
```python
"""
@Time           : 2019-11-06 21:59
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : ThreadQueue.py
@Software       : PyCharm
"""
"""
线程优先级队列（ Queue）
    Python 的 Queue 模块中提供了同步的、线程安全的队列类，包括FIFO（先入先出)队列Queue，LIFO（后入先出）队列LifoQueue，和优先级队列 PriorityQueue。
    这些队列都实现了锁原语，能够在多线程中直接使用，可以使用队列来实现线程间的同步。
    
    Queue 模块中的常用方法:
        Queue.qsize() 返回队列的大小
        Queue.empty() 如果队列为空，返回True,反之False
        Queue.full() 如果队列满了，返回True,反之False
        Queue.full 与 maxsize 大小对应
        Queue.get([block[, timeout]])获取队列，timeout等待时间
        Queue.get_nowait() 相当Queue.get(False)
        Queue.put(item) 写入队列，timeout等待时间
        Queue.put_nowait(item) 相当Queue.put(item, False)
        Queue.task_done() 在完成一项工作之后，Queue.task_done()函数向任务已经完成的队列发送一个信号
        Queue.join() 实际上意味着等到队列为空，再执行别的操作
"""
import queue
import threading
import time

exitFlag = 0


class myThread(threading.Thread):
    def __init__(self, threadID, name, q):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.q = q

    def run(self):
        """
            重写父类的run方法
        """
        print("开启线程：" + self.name)
        process_data(self.name, self.q)
        print("退出线程：" + self.name)


def process_data(threadName, q):
    """
    :param threadName:
    :param q:
    """
    while not exitFlag:
        queueLock.acquire()
        if not workQueue.empty():
            data = q.get()
            queueLock.release()
            print("%s processing %s " % (threadName, data))
        else:
            queueLock.release()
        time.sleep(1)


threadList = ["Thread-1", "Thread-2", "Thread-3"]
nameList = ["One", "Two", "Three", "Four", "Five"]
queueLock = threading.Lock()
workQueue = queue.Queue(10)
threads = []
threadID = 1

# 填充队列
queueLock.acquire()
for word in nameList:
    workQueue.put(word)
queueLock.release()

# 创建新线程
for tName in threadList:
    thread = myThread(threadID, tName, workQueue)
    thread.start()
    threads.append(thread)
    threadID += 1

# 等待队列清空
while not workQueue.empty():
    pass

# 通知线程是时候退出
exitFlag = 1

# 等待所有线程完成
for t in threads:
    t.join()
print("退出主线程")

```

## 17 Python3 XML解析
### 17.1 sax解析
```python
"""
@Time           : 2019-11-07 21:41
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : XmlParse.py
@Software       : PyCharm
"""
"""
xml解析：
    常见的XML编程接口有DOM和SAX，这两种接口处理XML文件的方式不同，当然使用场合也不同。
    Python有三种方法解析XML，SAX，DOM和ElementTree：
    
    1.SAX（XML的简单API）
    Python标准库包含SAX解析器，SAX用事件驱动模型，通过在解析XML的过程中触发一个个事件并调用用户定义的变量函数来处理XML文件。
    
    2.DOM（文档对象模型）
    将XML数据在内存中解析成一个树，通过对树的操作来操作XML。
    
    
    Python使用SAX解析xml
        SAX是一种基于事件驱动的API。
        利用SAX解析XML文档牵涉到两个部分：解析器和事件处理器。
        解析器负责读取XML文档，并向事件处理器发送事件，如元素开始跟元素结束事件。
        而事件处理器则负责对事件做出响应，对传递的XML数据进行处理。
        1，对大型文件进行处理；
        2，只需要文件的部分内容，或者只是从文件中得到特定信息。
        3，想建立自己的对象模型的时候。
        在 Python 中使用 sax 方式处理 xml 要先引入 xml.sax 中的 parse 函数，还有 xml.sax.handler 中的 ContentHandler。
        
        ContentHandler 类方法介绍
            characters(content) 方法
            调用时机：
                从行开始，遇到标签之前，存在字符，content 的值为这些字符串。
                从一个标签，遇到下一个标签之前， 存在字符，content 的值为这些字符串。
                从一个标签，遇到行结束符之前，存在字符，content 的值为这些字符串。
                标签可以是开始标签，也可以是结束标签。
            startDocument() 方法:文档启动的时候调用。
            endDocument() 方法:解析器到达文档结尾时调用。
            startElement(name, attrs) 方法:遇到XML开始标签时调用，name 是标签的名字，attrs 是标签的属性值字典。
            endElement(name) 方法:遇到XML结束标签时调用。   
            
            
    make_parser 方法:以下方法创建一个新的解析器对象并返回。
    xml.sax.make_parser( [parser_list] )
        参数说明:
        parser_list - 可选参数，解析器列表
        
    parser 方法:以下方法创建一个 SAX 解析器并解析xml文档：
    xml.sax.parse( xmlfile, contenthandler[, errorhandler])
        参数说明:
        xmlfile - xml文件名
        contenthandler - 必须是一个 ContentHandler 的对象
        errorhandler - 如果指定该参数，errorhandler 必须是一个 SAX ErrorHandler 对象
        
    parseString 方法: parseString 方法创建一个 XML 解析器并解析 xml 字符串：
    xml.sax.parseString(xmlstring, contenthandler[, errorhandler])
        参数说明:
        xmlstring - xml字符串
        contenthandler - 必须是一个 ContentHandler 的对象
        errorhandler - 如果指定该参数，errorhandler 必须是一个 SAX ErrorHandler对象
"""
import xml.sax


class MovieHandler(xml.sax.ContentHandler):
    def __init__(self):
        self.CurrentData = ""
        self.type = ""
        self.format = ""
        self.year = ""
        self.rating = ""
        self.stars = ""
        self.description = ""

    # 元素开始事件处理
    def startElement(self, tag, attributes):
        """
        :param tag:
        :param attributes:
        """
        self.CurrentData = tag
        if tag == "movie":
            print("*****Movie*****")
            title = attributes["title"]
            print("Title:", title)

    # 元素结束事件处理
    def endElement(self, tag):
        """
        :param tag:
        """
        if self.CurrentData == "type":
            print("Type:", self.type)
        elif self.CurrentData == "format":
            print("Format:", self.format)
        elif self.CurrentData == "year":
            print("Year:", self.year)
        elif self.CurrentData == "rating":
            print("Rating:", self.rating)
        elif self.CurrentData == "stars":
            print("Stars:", self.stars)
        elif self.CurrentData == "description":
            print("Description:", self.description)
        self.CurrentData = ""

    # 内容事件处理
    def characters(self, content):
        """
        :param content:
        """
        if self.CurrentData == "type":
            self.type = content
        elif self.CurrentData == "format":
            self.format = content
        elif self.CurrentData == "year":
            self.year = content
        elif self.CurrentData == "rating":
            self.rating = content
        elif self.CurrentData == "stars":
            self.stars = content
        elif self.CurrentData == "description":
            self.description = content


if __name__ == "__main__":
    # 创建一个 XMLReader
    parser = xml.sax.make_parser()
    # turn off namepsaces
    parser.setFeature(xml.sax.handler.feature_namespaces, 0)

    # 重写 ContextHandler
    Handler = MovieHandler()
    parser.setContentHandler(Handler)

    # 以下方法创建一个 SAX 解析器并解析xml文档
    parser.parse("movies.xml")


```
### 17.2 DOM 解析
```python
"""
@Time           : 2019-11-07 22:12
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : XmlDomParse.py
@Software       : PyCharm
"""
"""
使用xml.dom解析xml
    文件对象模型（Document Object Model，简称DOM），是W3C组织推荐的处理可扩展置标语言的标准编程接口。
    一个 DOM 的解析器在解析一个 XML 文档时，一次性读取整个文档，把文档中所有元素保存在内存中的一个树结构里，
    之后你可以利用DOM 提供的不同的函数来读取或修改文档的内容和结构，也可以把修改过的内容写入xml文件。
"""

from xml.dom.minidom import parse
import xml.dom.minidom

# 使用minidom解析器打开 XML 文档，得到DOM树
DOMTree = xml.dom.minidom.parse("movies.xml")

# 文档对象
collection = DOMTree.documentElement

if collection.hasAttribute("rack"):
    # etAttribute(AttributeName)：获取XML节点属性值
    print("Root element : %s" % collection.getAttribute("rack"))

# 在集合中获取所有电影
# getElementsByTagName(TagName)：获取XML节点对象集合
movies = collection.getElementsByTagName("movie")

# 打印每部电影的详细信息
for movie in movies:
    print("*****Movie*****")
    if movie.hasAttribute("title"):
        print("Title: %s" % movie.getAttribute("title"))

    type = movie.getElementsByTagName('type')[0]
    print("Type: %s" % type.childNodes[0].data)
    format = movie.getElementsByTagName('format')[0]
    print("Format: %s" % format.childNodes[0].data)
    rating = movie.getElementsByTagName('rating')[0]
    print("Rating: %s" % rating.childNodes[0].data)
    description = movie.getElementsByTagName('description')[0]
    print("Description: %s" % description.childNodes[0].data)

```
### 17.3 DOM创建xml
```python
"""
@Time           : 2019-11-07 22:31
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : CreateXml.py
@Software       : PyCharm
"""
import xml.dom


def create_element(doc, tag, attr):
    # 创建一个元素节点
    elementNode = doc.createElement(tag)
    # 创建一个文本节点
    textNode = doc.createTextNode(attr)
    # 将文本节点作为元素节点的子节点
    elementNode.appendChild(textNode)
    return elementNode


dom1 = xml.dom.getDOMImplementation()  # 创建文档对象，文档对象用于创建各种节点。
doc = dom1.createDocument(None, "info", None)
top_element = doc.documentElement  # 得到根节点
books = [{'head': u'bookone', 'page': u'200', 'number': u'001', 'id': u'001', 'name': u'python check'},
         {'head': u'booktwo', 'page': u'300', 'number': u'002', 'id': u'002', 'name': u'python learn'}]
for book in books:
    sNode = doc.createElement('list')
    sNode.setAttribute('id', str(book['id']))
    headNode = create_element(doc, 'head', book['head'])
    nameNode = create_element(doc, 'name', book['name'])
    numberNode = create_element(doc, 'number', book['number'])
    pageNode = create_element(doc, 'page', book['page'])
    sNode.appendChild(headNode)
    sNode.appendChild(nameNode)
    sNode.appendChild(pageNode)
    top_element.appendChild(sNode)  # 将遍历的节点添加到根节点下
xmlfile = open('bookdate.xml', 'w')
doc.writexml(xmlfile, addindent=' ' * 4, newl='\n', encoding='utf-8')
xmlfile.close()

```

## 18 Python3 JSON 数据解析

* Python 编码为 JSON 类型转换对应表：

| Python                                 | JSON   |
| -------------------------------------- | ------ |
| dict                                   | object |
| list, tuple                            | array  |
| str                                    | string |
| int, float, int- & float-derived Enums | number |
| True                                   | true   |
| False                                  | false  |
| None                                   | null   |

* JSON 解码为 Python 类型转换对应表：

| JSON          | Python |
| ------------- | ------ |
| object        | dict   |
| array         | list   |
| string        | str    |
| number (int)  | int    |
| number (real) | float  |
| true          | True   |
| false         | False  |
| null          | None   |
```python
"""
@Time           : 2019-11-07 22:40
@Author         : clj2ee@163.com
@ProjectName    : python-project
@File           : JsonParse.py
@Software       : PyCharm
"""
"""
Python3 JSON 数据解析
    JSON (JavaScript Object Notation) 是一种轻量级的数据交换格式。它基于ECMAScript的一个子集。
    Python3 中可以使用 json 模块来对 JSON 数据进行编解码，它包含了两个函数：

    json.dumps(): 对数据进行编码。
    json.loads(): 对数据进行解码。
"""
import json

# Python 字典类型转换为 JSON 对象
data = {
    'no': 1,
    'name': 'Runoob',
    'url': 'http://www.runoob.com'
}

json_str = json.dumps(data)
print("Python 原始数据：", repr(data))
print("JSON 对象：", json_str)

print('---------------------------------------------')

data1 = {
    'no': 1,
    'name': 'Runoob',
    'url': 'http://www.runoob.com'
}

json_str = json.dumps(data1)
print("Python 原始数据：", repr(data1))
print("JSON 对象：", json_str)

# 将 JSON 对象转换为 Python 字典
data2 = json.loads(json_str)
print("data2['name']: ", data2['name'])
print("data2['url']: ", data2['url'])

print('---------------------------------------------')

# 写入 JSON 数据写入一个文件中
with open('names.json', 'w') as f:
    json.dump(data, f)

# 读取数据
with open('names.json', 'r') as f:
    data = json.load(f)
    print('读取json文件内容：', data)

```

## 19 Python3 日期和时间

## 20 Python3内置函数

## 21 Python MongoDB



> 本文中有些例子：来源 [菜鸟教程](https://www.runoob.com/python3/python3-tutorial.html),非常感谢‘菜鸟教程’的帮助，如有侵权请联系:clj2ee@163.com ，本文未经许可严禁商用


