# Python魔术方法

## __call__

```python
class Person(object):

    def __init__(self, name, age):
        self._age = age
        self._name = name

    def __call__(self):
        print('name:{} age:{}'.format(self._name, self._age))

cat = Person('codingcat', 27)
cat()
```

## __bool__

```python
class Coin(object):

    def __init__(self, val):
        self._val = val

    def __bool__(self):
        return True if self._val == '正面' else False

coin = Coin('正面')
bool(coin)
```


## __setitem__ __getitem__ __len___

```python
class Zoo(object):

    def __init__(self):
        self._dict = {}

    def __setitem__(self, key, value):
        self._dict[key] = value

    def __getitem__(self, key):
        return self._dict[key]

    def __len__(self):
        return len(self._dict)

zoo = Zoo()

zoo['tom'] = 'cat'
zoo['tony'] = 'dog'

print('zoo have {} animals'.format(len(zoo)))
print('tom is a {}'.format(zoo['tom']))
```
