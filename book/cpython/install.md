# python编译安装

`代码clone`

```shell
# 如果未安装git
yum install git

git clone https://github.com/python/cpython.git
cd cpython
git checkout v3.7.0
```

`编译前系统库安装`

```shell
# gcc make
yum install gcc make

# zlib
yum install zlib-devel

# 3.7版本需要一个新的包libffi-devel
yum install libffi-devel

# sqlite安装
yum install sqlite-devel

# readline安装
yum install readline-devel

# openssl安装
yum install openssl-devel

# tk安装
yum install tk-devel
```

`编译安装`

```shell
# 查看configure可选项
./configure --help

./configure
make
make install
```
