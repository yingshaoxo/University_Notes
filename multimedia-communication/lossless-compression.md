# Lossless Compression

### 1. 行程编码\(Run Length Encoding，RLE\)

压缩原始数据中相同、重复的部分

### 2. 霍夫曼编码\(Huffman Coding\)

`出现概率大的`分配`短码`， `出现概率小的`分配`长码`

步骤:

1. 按概率递减排列
2. 把两个最小的`概率值`合并，作为新符号概率
3. 重复 step1 和 step2 ，直到概率和 = 1
4. ...

![](../.gitbook/assets/huffman_coding_example1%20%281%29.jpg)

注意:

* 允许交叉
* `概率大的分支`写`1`，`概率小的分支`写`0`，如果概率相等就 左`1`右`0`
* 写`对应编码`时，从根出发，走最短路径

### 3. 算术编码

每次编码会得到一个`[0,1)`的小数。\(无限细分概率区间\)

> 实际是: 多重概率合并计算 \(那个小数 = 连续输这一串数据的概率\)

例如:

![](../.gitbook/assets/suanshubianma%20%281%29.png)

小数变二进制: **乘2取整**

![](../.gitbook/assets/chengerquzheng%20%281%29.png)

### 4. 字典编码\(Dictionary Coding\)

* 方式一，用`内存指针`指向重复字符\(方式二 dict 方法的本质\)
* 方式二，自动创建 dict，输出 index，而不是原数据

## Questions

**我这里第一题的答案是错的，你可以按照你自己的想法自己再做一遍**

![](../.gitbook/assets/huffman_coding_example2%20%281%29.jpg)

![](../.gitbook/assets/suansu_bianma%20%281%29.jpg)

注意 `1 - 0`，`0.5 - 0`, `0.375 - 0.25` 只是一个区间，它们的值还是取决于符号的概率

比如:

$$0.5 = (1-0) \times 0.5$$

$$0.375 = (0.5-0) \times (0.5 + 0.25)$$

$$0.25 = (0.5-0) \times (0.5)$$

$$0.359375 = (0.5 + 0.25 + 0.125) \times (0.375 - 0.25) + 0.25$$

$$0.34375 = (0.5+0.25) \times (0.375 - 0.25) + 0.25$$

$$0.357421875 = 0.359375 - ((0.359375 - 0.34375) \times 0.125)$$

