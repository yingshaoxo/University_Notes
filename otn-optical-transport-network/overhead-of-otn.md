### What is OH
OH stands for Overhead.

> My point of view: Overhead is additional data transmitted for better communication.

### OverHead of OTN

![](/assets/Overhead of OTN.png)

### OTU OH and Frame Alignment

**OTU = Optical Transport Unit**

OTU OH = Optical Transport Unit OverHead

> The OTU is used in the OTN to support transport via one or more optical channel connections.

![](/assets/OTU OH structure.png)

#### FAS (frame alignment signal, 帧定位)

The `frame alignment OH`, which is part of the `OTU OH`, is situated in row 1, columns 1 to 6 of the OTU in which a FAS is defined, as Figure 7 shows. As the OTU and ODU frames could span multiple OTU frames, a multiframed, structured overhead signal is defined. The `multiframe alignment signal (MFAS)` is defined in row 1, column 7 of the OTU/ODU overhead. The value of the `MFAS byte` increments with each OTU/ODU frame.

#### SM (Section Monitoring, 段监控)

![](/assets/Section monitoring OH.png)

