### 1. 用户身份加密

用 TMSI 代替 IMSI 识别不同用户，并在空中传输信息。

> TMSI: Temporary Mobile Subscriber Identity

> IMSI: International Mobile Subscriber Identity

___

### 2. 用户身份鉴权(authentication)

![](/assets/GSM用户鉴权.png)

> A3, A5, A8 指的各种算法。Algorithm -> Ａ.

* A3 用于鉴权，产生`Sres`
* A5 用于加密，产生`114 bit的加密序列`. It's probably binary numbers
* A8 用于产生密钥，即`Kc`

#### step 1

`AuC`生成`RAND`。

`AuC`通过`A3(RAND, Ki)`得到`SRES`

于是有了`三参数组(RAND, SRES, Kc)`。

> SRES = Series

> RAND = Random Numbers

> Ki = individual subscriber authentication key

> Kc = ciphering key

#### step 2

`MSC`发送`RAND`给`MS`。

`MS`通过`A3(RAND, Ki)`得到`SRES`。

`MS`将生成的`SRES`回传给`MSC`。

`MSC`对比之前它自己生成的`SRES`，如果相同，那么匹配成功(鉴定完毕是那个用户)

> `SIM`, `Auc` 有共同的 `Ki`。`Ki`与`IMSI`在注册`SIM卡`时就产生了。

___

### 3. 用户(语音)数据加密

![](/assets/GSM数据加密.png)

`AuC`通过`A8(RAND, Ki)`得到`Kc`

`MSC`通过`A5(Kc, TDMA序列号)`得到`114 bit的序列`

`MSC`将`用户数据`与`114 bit的序列`做`异或运算`，再将`运算结果`发送给手机

`MS`自己也像`MSC`那样产生`114 bit的序列`，将`接收到的数据`与`114 bit的序列`做`异或运算`，最终得到`原始数据`

> 异或: Binary XOR

```
a = 60            # 60 = 0011 1100 
b = 13            # 13 = 0000 1101
 
c = a ^ b;        # 49 = 0011 0001
```

___

References:

http://www.jiamisoft.com/blog/22123-gsma.html