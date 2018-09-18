# 二叉搜索树

```python
class Node(object):

    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None


class BSTree(object):

    def __init__(self):
        self.root = None

    def add(self, value):
        if not self.root:
            self.root = Node(value)
        else:
            self._insert(value, self.root)

    def _insert(self, value, node):
        if value < node.value:
            if node.left:
                self._insert(value, node.left)
            else:
                node.left = Node(value)
        elif value > node.value:
            if node.right:
                self._insert(value, node.right)
            else:
                node.right = Node(value)
        else:
            print('Value alread in tree!')

    def print(self):
        if self.root:
            self._print(self.root)

    def _print(self, node):
        if node:
            self._print(node.left)
            print('\t', node.value)
            self._print(node.right)

    @property
    def height(self):
        if self.root:
            return self._height(self.root, 0)
        else:
            return 0

    def _height(self, node, height):
        if not node:
            return height

        left_height = self._height(node.left, height + 1)
        right_height = self._height(node.right, height + 1)

        return max(left_height, right_height)

    def search(self, value):
        if self.root:
            return self._search(value, self.root)
        else:
            return False

    def _search(self, value, node):
        if value == node.value:
            return True
        elif value < node.value and node.left:
            return self._search(value, node.left)
        elif value > node.value and node.right:
            return self._search(value, node.right)

        return False


def main(count):
    bst = BSTree()
    from random import randint
    for _ in range(count):
        value = randint(0, count)
        bst.add(value)

    bst.print()
    print('Tree height', bst.height)
    print('Tree find 5', bst.search(5))

main(15)
```
