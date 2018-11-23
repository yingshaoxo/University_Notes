### 感慨
我本来是对这个学科有好感的，但直到我发现中国在教这个学科时的 SB 之处，我突然很厌恶这个学科。

举个例子，为什么 `ip地址` 转 `2进制` 要用人脑算？ 你是傻逼吗？

```python
>>> IP = "192.168.75.158"
>>> MASK = "255.255.255.240"
>>> 
>>> 
>>> def decimal_to_binary(num):
...     if isinstance(num, str):
...         return [bin(int(x)+256)[3:] for x in num.split('.')]
...     elif isinstance(num, list):
...         result = []
...         for i in num:
...             result.append(bin(i+256)[3:])
...         return result
... 
>>> 
>>> Binary_IP_list = decimal_to_binary(IP)
>>> Binary_MASK_list = decimal_to_binary(MASK)
>>> 
>>> print(IP, ':', Binary_IP_list)
192.168.75.158 : ['11000000', '10101000', '01001011', '10011110']
>>> print(MASK, ':', Binary_MASK_list)
255.255.255.240 : ['11111111', '11111111', '11111111', '11110000']
```
___

另外，还有很多底层的早已被内嵌到硬件算法的计算过程，他妈的还是叫你用人脑算，比如`子网划分`（http://tool.chinaz.com/Tools/subnetmask）

就拿`子网划分(Subnetting)` 这个技术来讲，它是为了解决ip地址不足而研发的，如果我们切换到 `ipv6` 为主导的网络世界，这项技术就完全没意义了
___

说白了，你国 `计算机网络` 这门学科就是抄袭照搬全翻译的 `Data Communications and Networking - Behrouz A. Forouzan`

结果国内老师讲得一塌糊涂，着实让我兴趣全无，十分心寒。