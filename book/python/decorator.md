# Python闭包与装饰器

## 闭包

```python
def external(value):

    def inner():
        value += 1

    return inner
```
