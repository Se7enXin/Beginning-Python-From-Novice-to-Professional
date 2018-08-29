# 11 文件

## 11.1 打开文件

```python
open('file_name', mode)
```

返回文件对象
mode可选，mode的取值可以有多个
open('file_name')与open('file_name', 'rt')相同

|值|描述||
|--|----|-|
|'r'|读取模式（默认值）||
|'w'|写入模式|文件不存在时创建，既有内容将被删除（截断），并从文件开头处开始写入|
|'x'|独占写入模式|文件已存在时引发FileExistsError异常|
|'a'|附加模式||
|'b'|二进制模式（与其他模式结合使用）||
|'t'|文本模式（默认值，与其他模式结合使用）|把文件视为经过编码的Unicode文本，将自动执行解码和编码，且默认使用UTF-8编码|
|'+'|读写模式（与其他模式结合使用）||

换行（'\n','\r','\r\n'）
open(name, newline='')

如果要指定只将'\r'或'\r\n'视为合法的行尾字符，可将参数newline设置为相应的行尾字符。这样，读取时不会对行尾字符进行转换，但写入时将把'\n'替换为指定的行尾字符

如果文件包含非文本的二进制数据，如声音剪辑片段或图像，你肯定不希望执行上述自动转换。为此，只需使用二进制模式（如'rb'）来禁用与文本相关的功能

## 11.2 文件的基本方法

### 读取和写入

### 使用管道重定向输出

随机存取：seek tell

seek(offset, whence)

方法tell()返回当前位于文件的什么位置

### 读取和写入行

readline()
readlines()
writelines()

没有writeline()

### 关闭文件

with open('somefile.txt') as somefile:
    do_something(somefile)

do_something执行完后，将自动关闭文件

### 使用文件的基本方法

## 11.3 迭代文件内容

### 每次一个字符

```python
with open(filename) as f:
    while True:
        char = f.read(1)
        if not char: break
        print(char)
```

### 每次一行

```python
with open(filename) as f:
    while True:
        line = f.readline()
        if not line: break
        print(line)
```

### 读取所有内容

```python
with open(filename) as f:
    for char in f.read():
        print(char)
```

```python
with open(filename) as f:
    for line in f.readlines():
        print(line)
```

### 使用fileinput实现延迟行迭代

```python
import fileinput
for line in fileinput.input(filename):
    print(line)
```

### 文件迭代器

```python
with open(filename) as f:
    for line in f:
        print(line)
```

不使用上下文管理器(with ... as ...:)，不显式关闭文件对象：

```python
for line in open(filename):
    print(line)
```

迭代标准输入中的所有行：

```python
import sys
for line in sys.stdin:
    print(line)
```











