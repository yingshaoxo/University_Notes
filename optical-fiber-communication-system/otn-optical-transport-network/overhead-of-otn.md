# OverHead of OTN

## What is OH

OH stands for Overhead.

> My point of view: Overhead is additional data transmitted for better communication.

## OverHead of OTN

![](../../.gitbook/assets/Overhead%20of%20OTN.png)

## OTU OH and Frame Alignment

**OTU = Optical Transport Unit**

OTU OH = Optical Transport Unit OverHead

> The OTU is used in the OTN to support transport via one or more optical channel connections.

![](../../.gitbook/assets/OTU%20OH%20structure.png)

### FAS \(frame alignment signal, 帧定位\)

The `frame alignment OH`, which is part of the `OTU OH`, is situated in row 1, columns 1 to 6 of the OTU in which a FAS is defined, as Figure 7 shows. As the OTU and ODU frames could span multiple OTU frames, a multiframed, structured overhead signal is defined. The `multiframe alignment signal (MFAS)` is defined in row 1, column 7 of the OTU/ODU overhead. The value of the `MFAS byte` increments with each OTU/ODU frame.

### SM \(Section Monitoring, 段监控\)

![](../../.gitbook/assets/Section%20monitoring%20OH.png)

The `section monitoring (SM) OH` consists of the subfields as described for the `path monitoring OH`, with the exception of the `incoming alignment error (IAE)` bit. This bit allows the ingress point to inform the egress point that an alignment error in the incoming signal has been detected. IAE is set to “1” when an error occurs, otherwise it is set to “0”.

* TTI: Trail trace identifier

  > The TTI is similar to the J0 byte in SONET/SDH, which is used to identify the signal from the source to the destination within the network. The TTI contains the `access point identifiers (API)`, which are used to specify the `source (SAPI)` and `destination access point identifiers (DAPI)`. The APIs contain information regarding the country of origin, network operator, and administrative details.

* BIP-8: Bit interleaved parity

  > This byte, used for error detection, provides a BIP-8 code, computed over the whole OPU and inserted into the BIP-8 SM two frames later.

* BEI and BIAE: Backward Error Indication and Backward Incoming Alignment Error

  > The BEI and BIAE signals carry information upstream on interleaved bit blocks detected in error and are also used to convey incoming alignment errors \(IAE\) upstream.

* BDI: Backward defect indication

  > The single bit BDI conveys information upstream regarding signal failure.

* IAE: Incoming \(Frame\) Alignment Error
* RES: Reserved

![](../../.gitbook/assets/Section%20monitoring%20开销.png)

* 路径踪迹标识码: TTI
* 奇偶校验: BIP-8
* 后向输入帧定位错误: BEI/BIAE、BDI

### GCC \(General communication channel\)

GCC is used as a communication channel between OTU termination points.

> 网管通道

### RES \(Reserved\)

It has no definition yet. It's reserved.

> 保留字节

## ODU OH

**ODU = Optical Data Unit**

![](../../.gitbook/assets/Overhead%20structure%20of%20ODU.png)

### TCM \(Tandem Connection Monitoring, 串联连接监测\)

![](../../.gitbook/assets/TCM%20and%20PM%20Overhead%20structures.png)

### PM \(Path Monitoring, 用户通道监控\)

![](../../.gitbook/assets/TCM%20and%20PM%20Overhead%20structures%20%281%29.png)

### APS/PCC \(Automatic protection switching and protection communication channel\)

![](../../.gitbook/assets/APS%20字段格式.png)

![](../../.gitbook/assets/APS%20信道字段值与含义1.png)

![](../../.gitbook/assets/APS%20信道字段值与含义2.png)

