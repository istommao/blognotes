# Python编码规范


## 工具

- pep8检查工具
- pylint
- pre-commit

## import 顺序问题


`PEP8建议按如下三种方式分组导入包`

- 标准库导入
- 第三方相关包导入
- 本地应用或库导入

```python
#标准库
from math import sqrt
from os.path import abspath

#Django导入
from django.db import models
from django.utils.translation import ugettext_lazy as _

#第三方应用导入
from rest_framework.response import Response

#导入自己的应用
from user.models import User
```

- 尽量不要使用 `id` `type` 等Python关键字给变量命名


## 代码的坏味道

- 神奇的数字 使用常量代替
- 确定不再使用的代码，别注释掉，直接删除
- 重复的代码 DRY
- 不必要的复杂
- 不知所云的变量名
- 冗长的类
- 过长的函数

## 防御性编程

- 检查前端传来的参数，考虑边界值
- 最小权限原则


## 编写函数的几个原则
- 1：函数设计要尽量短小，嵌套层次不宜过深。最好能控制在 3 层以内。
- 2：函数申明应该做到合理、简单、易于使用。参数个数不宜太多。
- 3：函数参数设计应该考虑向下兼容。比如相同功能的函数不同版本的实现，唯一不同的是在更高级的版本中添加了参数导致程序中函数调用的接口发生了改变。这并不是最佳设计，更好的方法是通过加入默认参数来避免这种退化，做到向下兼容。
- 4：一个函数只做一件事，尽量保证函数语句粒度的一致性。
- 5：不要在函数参数中定义可变对象作为默认值
- 6：使用异常替换返回错误
- 7：保证通过单元测试

---

- PEP8  https://www.python.org/dev/peps/pep-0008/
- Python风格规范  http://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_style_rules/
- Python语言规范  http://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_language_rules/
- Python Code Style http://www.wklken.me/posts/2016/11/03/python-code-style.html
- https://pythonguidecn.readthedocs.io/zh/latest/writing/style.html
