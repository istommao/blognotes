# python编译安装

`代码clone`

```shell
yum install wget

# yum太慢的话可以换国内yum源
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
cd /etc/yum.repos.d/
wget http://mirrors.163.com/.help/CentOS7-Base-163.repo
```

```shell
# 如果未安装git
yum install git

git clone https://github.com/python/cpython.git
cd cpython
git checkout v3.7.0

# 或wget获取源码
wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tar.xz

xz -d Python-3.7.0.tar.xz
tar xvf Python-3.7.0.tar
```

`编译前系统库安装`

```shell
# gcc make
yum install gcc

# zlib
yum install zlib zlib-devel

# 3.7版本需要一个新的包libffi-devel
yum install libffi-devel

# sqlite安装
yum install sqlite-devel

# 解决 readline 缺失提醒及方向键行为非预期的问题
yum install readline-devel

# openssl安装
yum install openssl openssl-devel

# 解决 import bz2 报错
yum install bzip2 bzip2-devel

# uuid
yum install libuuid-devel

# 解决 import curses 报错
# 安装 readline 会附带这个库
yum install ncurses-devel

# 解决 _dbm _gdbm 缺失提醒
yum install gdbm-devel

# 解决 _lzma 缺失提醒
yum install xz-devel

# 解决 _tkinter 缺失提醒
yum install tk-devel
```

```shell
sudo apt-get install uuid-dev

# 测试 uuid
cat /proc/sys/kernel/random/uuid
```

`编译安装`

```shell
# 查看configure可选项
./configure --help

./configure
make
make install

# 重新编译前
make clean
```
