# 生成器 generators

在讨论生成器之前先讲讲以下三个东西

- 可迭代对象 Iterable
- 迭代器 Iterator
- 迭代 Iteration

## 可迭代对象

> 定义了 __iter__方法或__getitem__方法的对象

## 迭代器

> 定义了__next__方法(在python2中是 next)的对象

## 迭代

> 循环遍历一个东西的过程

## 生成器

> 生成器也是一种迭代器，但只能迭代一次
> 它并不会将所有的值都存在内存中，而是实际运行才生成

```python
def gen_func():
    for i in range(10):
        yield i

for i in gen_func():
    print(i)
```
