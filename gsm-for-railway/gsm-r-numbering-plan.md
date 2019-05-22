## 专用码

CT + UN

* **CT**(calling type): 呼叫类型

* **UN**(user number): UIN + FC

* **UIN**(user indentificate number): 用户标识号码

* **FC**(function code): 功能码

![](/assets/呼叫类型.jpg)

![](/assets/功能码.jpg)

## 短号码

* 1200: 连接最适合的`列车调度员` (一般指当前位置对应的`列车调度员`)
* 1300: 连接最适合的`车站值班员` (一般指当前位置对应的`车站值班员`)
* 1600: 连接最适合的`电力调度员` (一般指当前位置对应的`电力调度员`）

## 一般号码

### MSISDN (Mobile Station International Subscriber Directory Number)
CC + NDC + SN

* **CC**(country code): 中国是 86

* **NDC**(national destination code): 中国是 149

* **SN**(subscriber number): $$H_0 H_1 H_2 + XXXXX$$

$$H_0 = 8$$

$$H_1 H_2$$为铁路调度通信网络`长途区号`

### IMSI (International mobile subscriber identity)

> 共15位

MCC + MNC + MSIN

* **MCC**(mobile country code): 中国是 460

* **MNC**(mobile network code): 暂定为 20

* **MSIN**(mobile subscription identification number): $$H_0 H_1 H_2 + S + XXXXXX$$

$$H_0 = 8$$

$$H_1 H_2$$为铁路调度通信网络`长途区号`

### 固定电话 (经过 FAS 中转的电话)

CC + NDC + SN

* **CC**(country code): 中国是 86

* **NDC**(national destination code): 中国是 149

* **SN**(subscriber number): $$C_1 C_2 H_1 H_2 + XXXXX$$

$$C_1 C_2 = FAS的识别码 = 91$$

$$H_1 H_2$$为铁路调度通信网络`长途区号`

### 特别服务号码

* 112: 故障报告
* 114: 查号码
* 117: 事故后，请求救援
