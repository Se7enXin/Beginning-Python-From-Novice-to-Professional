# 条件、循环及其他语句

## 5.1 再谈print和import

## 5.2 赋值魔法

## 5.3 代码块：缩进的乐趣

## 5.4 条件和条件语句

    if xxx:
        do something
    elif xxx:
        do something
    else:
        do something


    条件表达式:
        a = b if c else d
        如果c为True，a = b；否则，a = d

断言:

```python
age = -1
assert 0 < age < 100, 'the age must between (0,100)'
```

## 5.5 循环

* while
* for
* 迭代字典

    字典是无序的，每次遍历所得的输出随机

    字典元素的排列顺序是不确定的。
    换而言之，迭代字典的键或值时，一定会处理所有的键或值，但不知道处理的顺序。
    如果顺序很重要，可将键或值存储在一个列表中并对列表排序，再进行迭代。
    要让映射记住其项的插入顺序，可使用模块collections中的OrderedDict类

*

## 5.6 简单推导



## 5.7 三人行




