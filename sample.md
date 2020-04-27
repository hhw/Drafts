# Notes

[TOC]



## The Art of Computer Programming

###  1 基本概念

#### 1.1 算法（Apr 27 2020）

#### 欧几里得算法

> 给定两个正整数m和n，求它们的*最大公因子*：
>
> * 求余：m/n, r为余数
> * r = 0?： if r = 0， 算法结束；n即为答案
> * 减少：置m←n, n←r, 并返回第一步

对应Python代码：

```python
def func(m,n):
    '''欧几里得算法'''
    m1, n1 = m, n
    r = m1 % n1
    if r == 0:
        return n
    else:
        m1 = n1
        n1 = r
        return func(m1,n1)
```

优化：显然，如果原来m<n，第一步当中的商将总为0，因此算法在这种相当讨厌的情况下总是进行m和n的交换。我们可以增加一个新的步骤：

> * 确保m>=n： if m < n, m↔n

优化后对应的Python代码：

```python
def func(m,n):
    '''欧几里得算法'''
    m1, n1 = m, n
    if m1 < n1:
        m1, n1 = n1, m1
    r = m1 % n1
    if r == 0:
        return n
    else:
        m1 = n1
        n1 = r
        return func(m1,n1)
```

#### 算法的定义

一个算法不过是一组有穷的规则，这些规则给出求解特定问题的运算序列。

算法的五个重要特征：

* 有限性

* 确定性
* 输入
* 输出
* 能行性

Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)


> For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
