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