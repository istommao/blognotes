# RSA加密算法

`加密`

```
密文 = 明文^E  mode N

# 公钥
公钥(E, N)
```

`解密`

```
明文 ＝ 密文^D mode N

# 私钥
私钥 (D, N)
```

## 生成密钥对


- 求 N
- 求 L 仅在生成密钥对过程中使用
- 求 E
- 求 D

### 求N

> 首先准备两个大质数 p 和 q

```shell
N = p x q
```

### 求L

```shell
# L是p - 1 和 q - 1 的最小公倍数
L = lcm(p - 1, q - 1)
```

### 求E

> E是一个比 1 < E < L

```shell
# E 和 L 的最大公约数为1 (E和L互斥)
gcd(E, L) = 1
```

### 求D

`D由E计算得到`
- 1 < D < L
- E x D mod L = 1

