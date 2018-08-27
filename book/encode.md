# 编码问题

- ASCII码 美国信息交换标准码
- Unicode
- utf-8
- utf-16
- utf-32
- gbk
- gb2312

## ASCII码

> ASCII第一次以规范标准的型态发表是在1967年，最后一次更新则是在1986年，至今为止共定义了128个字元；
> 其中33个字元无法显示（一些终端提供了扩展，使得这些字符可显示为诸如笑脸、扑克牌花式等8-bit符号），
> 且这33个字元多数都已是陈废的控制字元。控制字元的用途主要是用来操控已经处理过的文字。
> 在33个字元之外的是95个可显示的字元。用键盘敲下空白键所产生的空白字元也算1个可显示字元（显示为空白）。 -- wiki

```
ASCII值  控制字符    ASCII值  控制字符    ASCII值  控制字符    ASCII值  控制字符
0        NUT        32      (space)    64       @           96      、
1        SOH        33      !          65       A           97      a
2        STX        34      "          66       B           98      b
3        ETX        35      #          67       C           99      c
4        EOT        36      $          68       D           100     d
5        ENQ        37      %          69       E           101     e
6        ACK        38      &          70       F           102     f
7        BEL        39      ,          71       G           103     g
8        BS         40      (          72       H           104     h
9        HT         41      )          73       I           105     i
10       LF         42      *          74       J           106     j
11       VT         43      +          75       K           107     k
12       FF         44      ,          76       L           108     l
13       CR         45      -          77       M           109     m
14       SO         46      .          78       N           110     n
15       SI         47      /          79       O           111     o
16       DLE        48      0          80       P           112     p
17       DCI        49      1          81       Q           113     q
18       DC2        50      2          82       R           114     r
19       DC3        51      3          83       S           115     s
20       DC4        52      4          84       T           116     t
21       NAK        53      5          85       U           117     u
22       SYN        54      6          86       V           118     v
23       TB         55      7          87       W           119     w
24       CAN        56      8          88       X           120     x
25       EM         57      9          89       Y           121     y
26       SUB        58      :          90       Z           122     z
27       ESC        59      ;          91       [           123     {
28       FS         60      <          92       /           124     |
29       GS         61      =          93       ]           125     }
30       RS         62      >          94       ^           126     `
31       US         63      ?          95       _           127     DEL
```


`ASCII控制字符`

```
二进制 十进制 十六进制    缩写  可以显示的表示法    名称/意义
0000  0000   0   00  NUL ␀   空字符（Null）
0000  0001   1   01  SOH ␁   标题开始
0000  0010   2   02  STX ␂   本文开始
0000  0011   3   03  ETX ␃   本文结束
0000  0100   4   04  EOT ␄   传输结束
0000  0101   5   05  ENQ ␅   请求
0000  0110   6   06  ACK ␆   确认回应
0000  0111   7   07  BEL ␇   响铃
0000  1000   8   08  BS  ␈   退格
0000  1001   9   09  HT  ␉   水平定位符号
0000  1010   10  0A  LF  ␊   换行键
0000  1011   11  0B  VT  ␋   垂直定位符号
0000  1100   12  0C  FF  ␌   换页键
0000  1101   13  0D  CR  ␍   归位键
0000  1110   14  0E  SO  ␎   取消变换（Shift out）
0000  1111   15  0F  SI  ␏   启用变换（Shift in）
0001  0000   16  10  DLE ␐   跳出数据通讯
0001  0001   17  11  DC1 ␑   设备控制一（XON 启用软件速度控制）
0001  0010   18  12  DC2 ␒   设备控制二
0001  0011   19  13  DC3 ␓   设备控制三（XOFF 停用软件速度控制）
0001  0100   20  14  DC4 ␔   设备控制四
0001  0101   21  15  NAK ␕   确认失败回应
0001  0110   22  16  SYN ␖   同步用暂停
0001  0111   23  17  ETB ␗   区块传输结束
0001  1000   24  18  CAN ␘   取消
0001  1001   25  19  EM  ␙   连接介质中断
0001  1010   26  1A  SUB ␚   替换
0001  1011   27  1B  ESC ␛   跳出
0001  1100   28  1C  FS  ␜   文件分割符
0001  1101   29  1D  GS  ␝   组群分隔符
0001  1110   30  1E  RS  ␞   记录分隔符
0001  1111   31  1F  US  ␟   单元分隔符
0111  1111   127 7F  DEL ␡   删除
```

`Python中ASCII的操作`

```python
# ASCII值 ＝> 字符
chr(65) == 'A'

# 字符 => ASCII值
ord('A') == 65
```

## Unicode 统一码

> 由于 ASCII只支持 英文字符数字等，为了解决这个问题
> 20世纪80年代末 一些美国公司组成Unicode组织的商业机构,
> 和国际合作的国际标准化组织因为电脑普及和资讯国际化的前提下，
> 分别各自成立了Unicode组织[3]和ISO-10646工作小组

`Python2中使用在字符串前加上u前缀表示unicode编码`
```python
s = u'Hello world'
```

`Python3中字符串默认是unicode编码`
```python
s = 'Hello world'
```

## utf-8

> utf-8 是Unicode编码的一种具体实现

```python
s = 'Hello world'
# utf-8编码
bytedata = s.encode('utf-8')

# utf-8解码
bytedata.decode('utf-8')
```

`乱码问题 编码解码方式不一致时, 也可能抛出UnicodeDecodeError`

```python
s = '你好'
bytedata = s.encode('utf-8')

bytedata.decode('gbk')
```



---

- https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/001431664106267f12e9bef7ee14cf6a8776a479bdec9b9000
- https://bindog.github.io/blog/2014/12/16/python-coding/