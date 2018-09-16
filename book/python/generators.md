# 生成器 generators

在讨论生成器之前先讲讲以下三个东西

- 可迭代对象 Iterable
- 迭代器 Iterator
- 迭代 Iteration

## 可迭代对象

> 返回一个迭代器的`__iter__`方法 或 支持下标索引的 `__getitem__` 方法的对象

```python
class Iterable:

    def __iter__(self):
        return iter('Iterable')

iters = Iterable()
```

## 迭代器

> 定义了`__next__`方法(在python2中是 next)的对象

## 迭代

> 循环遍历一个东西的过程

## 生成器

> 生成器也是一种迭代器，但只能迭代一次
> 它并不会将所有的值都存在内存中，而是实际运行才生成

```python
def gen_func():
    for i in range(10):
        yield i

# 生成器既可以被for循环调用 也可以用next函数调用
# for循环自己捕获了StopIteration
for i in gen_func():
    print(i)


gen = gen_func()

while True:
    try:
         print(next(gen))
    except StopIteration:
        break
```


---

- https://stackoverflow.com/questions/9884132/what-exactly-are-iterator-iterable-and-iteration
- https://docs.python.org/3/tutorial/classes.html#iterators
- https://docs.python.org/dev/library/stdtypes.html#iterator-types
- https://docs.python.org/dev/howto/functional.html#iterators
- https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/00143178254193589df9c612d2449618ea460e7a672a366000
- https://eastlakeside.gitbooks.io/interpy-zh/content/Generators/

