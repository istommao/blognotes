# Python魔术方法

## __call__

> 可调用

```python
class Person(object):

    def __init__(self, name, age):
        self._age = age
        self._name = name

    def __call__(self):
        print('name:{} age:{}'.format(self._name, self._age))

cat = Person('codingcat', 27)

callable(cat) == True
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


## 映射

- __hash__
- __setitem__
- __getitem__
- __delitem__
- __len___
- __contains__

```python
class Zoo(object):

    def __init__(self):
        self._dict = {}

    def __setitem__(self, key, value):
        self._dict[key] = value

    def __getitem__(self, key):
        return self._dict[key]

    def __delitem__(self, key):
        del self._dict[key]

    def __len__(self):
        return len(self._dict)

    def __contains__(self, value):
        return value in self._dict

zoo = Zoo()

zoo['tom'] = 'cat'
zoo['tony'] = 'dog'
'tom' in zoo

print('zoo have {} animals'.format(len(zoo)))
print('tom is a {}'.format(zoo['tom']))
```

## 比较方法

- __lt__
- __le__
- __gt__
- __ge__
- __eq__
- __ne__

```python
class Poker(object):

    CARDS = {
        'A': 1,
        '2': 2,
        '3': 3,
        '4': 4,
        '5': 5,
        '6': 6,
        '7': 7,
        '8': 8,
        '9': 9,
        '10': 10,
        'J': 11,
        'Q': 12,
        'K': 13
    }

    def __init__(self, card):
        self.card = str(card.upper())

    def __lt__(self, obj):
        return Poker.CARDS.get(self.card) < Poker.CARDS.get(obj.card)

    def __le__(self, obj):
        return Poker.CARDS.get(self.card) <= Poker.CARDS.get(obj.card)

    def __gt__(self, obj):
        return Poker.CARDS.get(self.card) > Poker.CARDS.get(obj.card)

    def __ge__(self, obj):
        return Poker.CARDS.get(self.card) >= Poker.CARDS.get(obj.card)

    def __eq__(self, obj):
        return Poker.CARDS.get(self.card) == Poker.CARDS.get(obj.card)

    def __ne__(self, obj):
        return Poker.CARDS.get(self.card) != Poker.CARDS.get(obj.card)

    def __repr__(self):
        return '<Pocker {}>'.format(self.card)

    def __str__(self):
        return '<Pocker {}>'.format(self.card)

j = Poker('J')
k = Poker('K')
j > k
```


---

- http://www.wklken.me/posts/2012/10/29/python-base-magic.html
