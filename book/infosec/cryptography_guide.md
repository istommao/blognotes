# 密码学入门与实践

## 密码技术

`机密性`

- 对称加密
- 公钥加密/非对称加密

`完整性`

- 单向散列函数

`认证`

- 消息验证码 MAC

`防治否认`

- 数字签名

- 伪随机数生成器


## 历史上的密码

`凯撒密码`

```python
text = 'aefqwerqvstreqwr'

# 加密
cipher = ''.join([chr(ord(i)  + 3) for i in text]).upper()

# 解密
text = ''.join([chr(ord(i)  - 3) for i in cipher]).lower()
```

## 流加密

## 分组加密

- 对称加密
    - DES
    - 3DES
    - AES Rijndael算法
        - ECB
        - CBC
        - CFB
        - OFB
        - CTR

- 公钥加密
    - RSA
    - EIGamal
    - Rabin
    - 椭圆曲线

## Hash函数

- MD4
- MD5
- SHA-1
- SHA-2
- SHA-3 Keccak算法
- RIPEMD-160 比特币

## 消息认证码 MAC

`应用`
- SSL/TLS
- IPsec

## 认证加密

- GCM
- GMAC
- CCM
- HMAC

## 数字签名

- RSA RSA-PSS
- EIGamal
- DSA
- ECDSA
- Rabin
