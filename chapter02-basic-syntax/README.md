# Chapter 02 - Python Basic Syntax

## 项目初始化

```bash
uv init chapter02-basic-syntax -p 3.10 --vcs none --description "Chapter 02 - Python Basic Syntax"
```

运行 Jupyter Notebook

```bash
./notebooks/.venv/Scripts/jupyter lab
```

## 2.1 输入与输出 [Input and Output]

### 输入的分类

- 物理设备：键盘、鼠标、传感器、雷达、摄像头
- 逻辑概念：终端、文件、程序的可视化窗口

基于 Python 的不同运行方式，有交互模式和非交互模式输入

- 交互模式：直接在终端中运行 Python 解释器，例如 `python` 或 `python3`。
- 非交互模式：`input()` 函数从终端读取用户输入。

### 如何进行输出

使用 Python 内置函数 `print()` 等函数进行输出。

> Python 解释器内置了很多函数和类型，任何时候都能使用 
> 完整内置函数参考：https://docs.python.org/zh-cn/3.10/library/functions.html

## 2.2 变量 [Variables]

变量是用于存储数据的内存位置。在 Python 中，变量不需要提前声明，直接赋值即可。

添加变量，用于程序过程中临时保存数据。

```python
text = input("请输入一个字符串：")
x = 10  # 变量 x 赋值为 10
y = "hello"  # 变量 y 赋值为字符串 "hello"
```
为变量赋值的不同写法

```python
a, b = 1, 2
x = y = z = 3
```

## 2.3 字符串 [Strings]

### 字符串的定义

字符串是 Python 中常用的数据类型，用于表示文本。字符串可以用单引号 `'`、双引号 `"` 或三引号 `'''` 或 `"""` 来定义。

```python
s1 = 'hello'  # 单引号定义字符串
s2 = "world"  # 双引号定义字符串
s3 = '''hello world'''  # 三引号定义字符串
s4 = """hello world"""  # 三引号定义字符串
```

### 字符串中使用变量

需要在字符串中插入变量的值的时候，可以使用 f-strings

> * f-strings 需要 Python 3.6 以上版本

```python
name = "张三"
age = 18
print(f"我是{name}，我今年{age}岁")
```

### 字符串的基本用法

成员运算

```python
x in s
x not in s
```

连接运算

```python
s1 = "hello"
s2 = "world"
s3 = s1 + s2  # 连接字符串
print(s3)  # 输出：helloworld

s4 = s3 * 3  # 重复字符串
print(s4)  # 输出：helloworldhelloworldhelloworld
```

### 字符串的索引和切片

字符串的索引和切片用于获取字符串中的指定字符或子字符串。

```python
s = "hello world"
print(s[0])  # 输出：h 输出索引为 0 的字符
print(s[1:5])  # 输出：ello 输出索引为 1, 2, 3, 4 的字符
print(s[1:5:2])  # 输出：el 输出索引为 1, 3 的字符
print(s[-1])  # 输出：d 输出最后一个字符
print(s[::-1])  # 输出：dlrow olleh 输出字符串的反转
```

### 字符串的方法 [String Methods]

- `str.count(sub[, start[, end]])`
  - 返回子字符串 `sub` 在字符串 `str` 中出现的次数。
- `str.find(sub[, start[, end]])`
  - 返回子字符串 `sub` 在字符串 `str` 中第一次出现的索引。
  - 如果 `sub` 没有找到，返回 -1。
- `str.isalnum()`
  - 判断字符串是否由字母和数字组成。
- `str.isalpha()`
  - 判断字符串是否由字母组成。
- `str.isdigit()`
  - 判断字符串是否由数字组成。
- `str.isspace()`
  - 判断字符串是否由空格组成。
- `str.islower()`
  - 判断字符串是否由小写字母组成。
- `str.isupper()`
  - 判断字符串是否由大写字母组成。
- `str.index(sub[, start[, end]])`
  - 返回子字符串 `sub` 在字符串 `str` 中第一次出现的索引。
  - 如果 `sub` 没有找到，会抛出 `ValueError` 异常。
  - 如果 `start` 或 `end` 被指定，则只在 `start` 或 `end` 之间查找。
- `str.join(iterable)`
  - 将字符串 `str` 作为分隔符，将可迭代对象 `iterable` 中的元素连接成一个字符串。
  - 可迭代对象 `iterable` 可以是列表、元组、集合、字典等。
  - 如果 `iterable` 中包含非字符串类型的元素，会抛出 `TypeError` 异常。
- `str.split(sep=None, maxsplit=-1)`
  - 将字符串 `str` 按照指定的分隔符 `sep` 进行分割，返回一个列表。
  - 如果 `sep` 没有指定，则默认以空格为分隔符。
- `str.strip([chars])`
  - 移除字符串 `str` 开头和结尾的指定字符 `chars`。
  - 如果 `chars` 没有指定，则默认移除空格。
- `str.startswith(prefix[, start[, end]])`
  - 判断字符串 `str` 是否以指定的前缀 `prefix` 开头。
  - 如果 `prefix` 没有指定，则默认判断字符串是否以空格开头。
  - 如果 `start` 或 `end` 被指定，则只在 `start` 或 `end` 之间判断。
- `str.replace(old, new[, count])`
  - 将字符串 `str` 中的子字符串 `old` 替换为 `new`。
  - 如果 `count` 没有指定，则默认替换所有的子字符串。
  - 如果 `count` 为 0，则不替换任何子字符串。
  - 如果 `count` 为 1，则只替换第一个子字符串。
  - 如果 `count` 为 2，则只替换前两个子字符串。
  - 其他情况，根据 `count` 的值进行替换。

```python
s = "hello world"
print(s.upper())  # 输出：HELLO WORLD 输出字符串的大写
print(s.lower())  # 输出：hello world 输出字符串的小写
print(s.title())  # 输出：Hello World 输出字符串的标题
print(s.capitalize())  # 输出：Hello world 输出字符串的首字母大写
print(s.count("l"))  # 输出：3 输出字符串中字符 "l" 的个数
print(s.find("l"))  # 输出：2 输出字符串中字符 "l" 的索引
print(s.replace("l", "L"))  # 输出：heLLo world 输出字符串中字符 "l" 替换为 "L"
```

## 2.4 数字类型 [Numbers]

Python 的数字类型经常用于数学计算和统计

### 数字类型的常见运算

- x + y ：加法运算
- x - y ：减法运算
- x * y ：乘法运算
- x / y ：除法运算
- x // y ：整除运算
- x % y ：取余运算
- x ** y ：乘方运算
- -x ：取负运算
- +x ：取正运算
- abs(x) ：取绝对值
- int(x) ：取整数
- float(x) ：取浮点数
- complex(re, im) ：一个带有实部 `re` 和虚部 `im` 的复数
- c.real ：复数 `c` 的实部
- c.imag ：复数 `c` 的虚部
- c.conjugate() ：复数 `c` 的共轭复数
- divmod(a, b) ：返回商和余数
- pow(x, y[, z]) ：返回 `x` 的 `y` 次幂，可选参数 `z` 表示对结果取模

### 数字类型的强制转换

- Python 是强类型的编程语言
- 通过 `type()` 函数可以查看变量的类型
- 通过 `int()`, `float()`, `complex()` 函数可以进行强制类型转换

### 数字与字符串的转换

- `str(x)` ：将数字 `x` 转换为字符串
- `int(x)` ：将只含有整数的字符串 `x` 转换为整数，否则报错
- `float(x)` ：将字符串 `x` 转换为浮点数
- `complex(x)` ：将字符串 `x` 转换为复数

## 2.5 Python 之禅

Python 之禅是 Tim Peters 于 1999 年编写的一段关于 Python 编程的指导原则。
它的目标是为 Python 编程提供一些指导原则，帮助开发者编写出更有质量的代码。

```bash
$ python
Python 3.10.18 (main, Jun 12 2025, 12:37:32) [MSC v.1943 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
>>>
```