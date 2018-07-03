# Python数据结构 字符串

## Python2与Python3的区别

`Python2`
- str: 已经编码后的字节序列
- unicode: 编码前的文本字符
- str与bytes都继承basestring

`Python3`
- str: 编码过的 unicode 文本字符
- bytes: 编码前的字节序列
- str与bytes类型独立区分

## 字符串的缓存机制 intern 池化

> 在进程中字符串可能是实例数量最多的类型之一，
> 因此CPython为字符串做了缓存机制
> 这样再次被使用时可以直接使用缓存中的对象
> 好处是节省了内存，且省去了创建新实例的开销

## 基本使用

```python
word = 'hello'

word += ' world'

```
