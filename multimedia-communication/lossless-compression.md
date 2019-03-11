# 无损压缩

___

#### 1. 行程编码(Run Length Encoding，RLE)

压缩原始数据中相同、重复的部分

___


#### 2. 霍夫曼编码(Huffman Coding)

`出现概率大的`分配`短码`， `出现概率小的`分配`长码`

步骤: 

1. 按概率递减排列
2. 把两个最小的`概率值`合并，作为新符号概率
3. 重复 step1 和 step2 ，直到概率和 = 1
4. ...

![](/assets/huffman_coding_example1.jpg)


注意: 

* 允许交叉
* `概率大的分支`写`1`，`概率小的分支`写`0`，如果概率相等就 左`0`右`1`
* 写`对应编码`时，从根出发，走最短路径

___

#### 3. 算术编码

每次编码会得到一个`[0,1)`的小数。(无限细分概率区间)

> 实际是: 多重概率合并计算 (那个小数 = 连续输这一串数据的概率)

例如: 

![](/assets/suanshubianma.png)

小数变二进制: **乘2取整**

![](/assets/chengerquzheng.png)

___

#### 4. 字典编码(Dictionary Coding)

* 方式一，用`内存指针`指向重复字符(方式二 dict 方法的本质)
* 方式二，自动创建 dict，输出 index，而不是原数据

___

## Questions

![](/assets/huffman_coding_example2.jpg)