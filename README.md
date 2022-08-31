#### 安装

```
npm install @imchen/rsa
```
----------
###### 支持任意长度字符, 密钥加解密
```
  import RSAEncrypt from '@imchen/rsa'

  // 加密
  function encodeRSA (data, key) {
    const encrypt = new RSAEncrypt()
    encrypt.setPublicKey(key)
    return encrypt.encryptLong(data)
  }

  // 解密
  function decodeRSA (data, key) {
    const encrypt = new RSAEncrypt()
    encrypt.setPrivateKey(key)
    return encrypt.decryptLong(data)
  }
```
-----------------
###### 只支持本地工具库任意长度字符及密钥加解密, 可用于公钥生成加密数据, 替代敏感信息, 在本地使用工具库私钥解密, 外部无解
```
  import RSASpecialEncrypt from '@imchen/rsa/special'

  // 加密
  function specialEncodeRSA (data, key) {
    const encrypt = new RSASpecialEncrypt()
    encrypt.setPublicKey(key)
    return encrypt.encryptUnicodeLong(data)
  }

  // 只能解 上面加密的数据
  function specialDecodeRSA (data, key) {
    const encrypt = new RSASpecialEncrypt()
    encrypt.setPrivateKey(key)
    // or return encrypt.decryptLong(data)
    return encrypt.decryptUnicodeLong(data)
  }
```

