# 描述符

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
