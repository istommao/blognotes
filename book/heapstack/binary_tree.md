# 二叉树python实现


```python
class Node(object):

    def __init__(self, val=None, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

class BinaryTree(object):

    def __init__(self):
        self.root = Node()
        self._queue = []

    def add(self, val):
        node = Node(val)
        if self.root.val is None:
            self.root = node
            self._queue.append(self.root)
        else:
            tree_node = self._queue[0]
            if not tree_node.left:
                tree_node.left = node
            else:
                tree_node.right = node
                self._queue.append(tree_node.right)
                self._queue.pop(0)

    def level_queue(self, root):
        if not root:
            return

        queue = []
        node = root
        queue.append(node)

        _lst = []
        while queue:
            node = queue.pop(0)

            _lst.append(node.val)

            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)

        print(_lst)

def main():
    tree = BinaryTree()
    for val in range(10):
        tree.add(val)

    print('队列实现 层阶遍历')
    tree.level_queue(tree.root)

main()
```
