### 模糊仅是第一阶段

#### 题外话
爬楼梯原理：越往上爬人越少，因为楼层越高，人越不想频繁上下楼。

#### 没人能脱离基础
在讲这个之前，我想复习一下什么是电流
> Current is the flow of charge. (电流本质就是电荷的流动，只不过我们设置一个单位安培 代表 每秒流过一根导线的横截面的电荷数)
> ** 注意人类规定电流永远从+极流向-极 **

再复习一下什么是电压
> 电压等于某种神秘的力把单位正电荷从A点移动到B点所做的功。
> ** 注意人类规定电压方向永远从+极到-极（高压到低压），不然会出现无穷的困惑 **

#### Kirchhoff's Current Law(KCL)
由基础知，电流就是一堆可流动的电荷在电线类导体管道里流动，和水流一样。但不管它是什么，总归是物质，是物质就要遵守物质与能量守恒定律
> 能量与物质总在不断转换，不可能凭空消失，也不可能凭空产生。

** 所以在电路中的某一点，$$电路流进=电流流出$$。 **

#### Kirchhoff's Voltage Law(KVL)
在一个闭合电路(类似串联)，设电压源为`U`，各地点的电压绝对值为`i`，从电压正极+出发，初始电压变量为`x = 0`，遇到`同方向电流(箭头朝负极-走)产生的电压`或`+-电压`，就 `x = x + i` , 遇到`逆方向电流(箭头朝正极+走)产生的电压`或`-+电压`，就 `x = x - i`，最终 `U == x` 为真。

** 其实就是 **
> 电压值从+a到-a绕闭合线路一圈，合为a处提供的电压

___

### 拒绝萌逼
根据老师讲的，我再深入分析一下：

##### 电压有两种: 
+ 单点电压
> 该点到参考点（如大地）间的电压。
>> 最底层的电压概念，如上句的“电压”，指：某种神秘的力把单位正电荷从A点移动到B点所做的功。

+ 双点电压
> 两个单点之间的电压，如一个（电阻）元件的两端的电压差
>> 一个二端元件(如电阻)的两端`+` 与`-`之间的差别只在于$$`+`端的单点电压>`-`端的单点电压$$
>>> 通俗理解，`+`是高电压，`-`是低电压，不过都是相对而言

##### Example
###### `+a点` -> `+-电压(5V)` -> `+-电压(3V)` -> `-a点`
  - 我问你，从`+a点`到`-a点`，电压从`+`到`-`降了多少？ 答案明了，8V
  - ** 假设a为电压源，有+-两端，你就应该得出这个电压源提供了8V电压这个结论 **

######`+a点` -> `+-电压(5V)` -> `-+电压(3V)` -> `-a点`
  - ** $$U_a = 5 + (-3) = 2V$$ **

** 其实这就是串联电压的基本规律 **
>从+方向数电压；方向相同(+-)，电压相加; 方向相反(-+)，电压相减；最终等于这段`电压之和`
>> 那段`电压之和`可以当被当成`ab端口的电压`，即 $$U_{ab}$$
>>> ~~不知为何说是 Kirchhoff's voltage law~~

___

### 我要升华
Procedure of adding element voltages around a loop:
> Step 1: Pick a starting node.

> Step 2: Pick a direction to travel around the loop (clockwise or counterclockwise).

> Step 3: Walk around the loop. 
>> **Include element voltages in a growing sum according to these rules:**

>> 1. When you encounter a new element, look at the voltage sign as you enter the element.
>> 2. If the sign is +plus, then there will be a voltage drop going through the element. Subtract the element voltage.
>> 3. If the sign is -minus, then there will be a voltage rise going through the element. Add the element voltage.

> Step 4: Continue around the loop until you reach the starting point, including element voltages all the way around.


##### State Kirchhoff's Voltage Law in another way: The sum of voltage rises equals the sum of voltage drops around a loop.

俗称**电压升降平衡。**