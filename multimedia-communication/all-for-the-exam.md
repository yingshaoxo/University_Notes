# All for the exam

> 这让我不禁怀疑：中文教育的主要目的是让你的大脑充满垃圾。

## 第1、2章

* 根据CCITT的定义，媒体可划分为五大类：感觉媒体、表示媒体、显示媒体、存储媒体、传输媒体。
* 多媒体通常是指感觉媒体的组合，即语言、文字、语音、数据等多种媒体的组合。
* 多媒体具有三个主要特点：信息量巨大、数据类型的多样性与复合性、数据类型间的区别大。
* 多媒体通信系统的四个特性：集成性、交互性、同步性、实时性。
* 一幅1024\*768的彩色图像，每像素用24bits编码，其数据量为18432Mbit。
* 多媒体数据中存在信息冗余，冗余的类型主要有六种：空间冗余、时间冗余、结构冗余、知识冗余、视听冗余。
* 在视频的相邻帧间，往往包含相同的背景和移动物体，因此，后一帧数据与前一帧数据有许多共同的地方，这是时间冗余。
* 信息熵是表示信息中各个元素比特数的统计平均值。
* 按信息压缩前后是否有损失，数据压缩可以分为有损压缩和无损压缩。
* 无损压缩编码主要有：霍夫曼编码、行程编码、算数编码和词典编码。
* 评价一种数据压缩技术的性能的三个关键指标为数据压缩比、重现质量、压缩与解压缩的速度。
* 霍夫曼编码结果是唯一的。
* 行程编码的工作原理是将连续相同的数据序列用一个重复次数和单个数值来表示。
* 算术编码对整个消息只产生一个码字，这个码字是在区间\[0,1\)之间的一个实数。
* 算术编码是一种对错误极敏感的编码方法。
* 一个原始数据字符串为HKKKKKKKKKAMP，采用行程编码后的字符串为H\#9KAMP。

## 第3、4章

* 人类听觉器官能感知的声音频率范围为20Hz~20kHz。
* 电话系统中话音的频率范围为300~3400Hz。
* 人对声音的主管感觉是用响度、音调和音色三个参数来描述的。
* 一个声音的闻阈值由于另一个声音的出现而提高的效应称为掩蔽效应。
* 声音质量的主管评价的通用标准对质量级别分5级。
* 根据编码方式的不同，音频编码分为三种:波形编码、参数编码、和混合编码，PCM编码属于波形编码，线性预测编码属于参数编码，G.711标准属于波形编码，G.728标准属于混合编码。
* G.711就是PCM语音压缩标准，采样频率为8kHz，码速率为64kb/s。
* 音频压缩编码标准G.7xx由国际组织ITU-T发布。
* MPEGAudioLayer3 简称为MP3，是我们常用的一种音乐文件格式。
* 比较波形编码与参数编码的优缺点。
* 人类获取的信息中约有16%来自听觉系统，约有70%来自视觉系统。
* 图像按亮度等级不同，可分为二值图像和灰度图像。
* 图像按空间维数的不同，可分为二维图像和三维图像。
* 人眼适应暗环境的能力称为视觉适应性，通常这种适应过程约需30秒。
* 人眼的亮度感觉不仅由景物自身的亮度决定，还与其所处周围环境亮度有关。
* 当人眼所看到的影像消失后，人眼仍能继续保留其影像0.1-0.4秒左右的图像，这种现象被称为视觉残留。
* 彩色表示需要考虑三个属性：亮度、色调和饱和度。
* 三基色是指红、绿、蓝三色。
* 计算机显示设备使用RGB颜色空间，PAL电视采用YUV颜色空间，NTSC电视采用YIQ颜色空间。
* 图像质量的主观评价采用国际通用的5级评分标准。
* 图像的数字化是指将一幅图像从模拟的形式转化为数字的形式，包括对图像进行采样、量化和编码等过程。
* 没有彩色信息每个像素由一个量化的灰度来描述的图像称为灰度图。
* 如果图像的灰度级只有两级，这样的图像称为二值图。
* 帧内预测编码是利用图像信号的空间相关性，用已传输的像素对当前像素进行预测。
* 帧间预测就是为了去除运动图像在时间上的相关性。
* 对于画面中运动部分占较小区域的图像，采用运动补偿技术的压缩数据效果特别好。
* 将图像分割成静止和运动的两部分是运动补偿预测的基础。
* 在发送端每隔一段时间丢掉几帧图像，在接收端利用帧间相关性将丢掉的帧恢复出来，这种运动图像压缩编码方法称为帧间内插。

## 第4、5章

* 由联合图像专家组制定的静止图像压缩编码标准为JPEG，JBIG是二值图像编码标准。
* H．261标准将CIF和QCIF格式的数据结构划分4个层次，分别为：picture、group\_of\_block、和macro-block、block。
* MPEG标准主要由MPEG-1\_audio、MPEG-1\_video和MPEG-13部分组成，是一个完整的多媒体压缩编码方案。
* MPEG-1video标准中将图像帧分为三类：内帧、预测帧和双向预测帧。 
* MPEG-2标准支持NTSC、PAL、SECAM和HDTV格式的视频。
* MPEG-4是基于对象的视频编码系统。
* 由ITU-T和ISO联合制定的视频压缩编码标准是MPEG-2。
* H.264标准分为"基本档次、主要档次和扩展档次"，以适用于不同的应用。
* VCD所使用的视频压缩标准是MPEG-1， DVD所使用的视频压缩标准是MPEG-2。 
* 基于TCP/IP的多媒体通信模型中通信控制层分为三个子层：数据获取子层、媒体同步子层、和通信子层。
* 多媒体系统提供三种不用的QoS服务：Best-Effort、Integrated和Differentiated。
* 典型的QoS参数集：QoS={吞吐量、容错率、传输时延、延时抖动}
* QoS提供机制包括：Qos映射、Qos协商、接纳控制和资源预留与分配。
* QoS控制机制包括：流调度、流成型、流监管、流量控制和媒体流同步。
* 多媒体通信网络要求语言和图像的传输时延须小于0.25s，静止图像的传输时延须小于1s。
* 多媒体数据内部所固有的约束关系为时域约束关系、空域约束关系和基于内容的约束关系。
* 多媒体通信系统中通常将音频作为主媒体流，其他媒体流作为从媒体流。
* 多播通信中，消息在每条链路上传递一次，在链路分叉时，消息会被复制。
* 多播通信可分为2类：网络层的多播、应用层的多播。
* 多媒体数据库系统由硬件和软件组成。
* 多媒体数据库系统可以抽象地表示为三层：物理层、概念层和表现层。
* 基于内容的检索直接对图像、视频、音频内容进行分析，从而抽取特征和语义进行检索。
* 流媒体技术能够在网络上实现传输和播放同时进行。
* 互联网对流媒体的影响主要体现在带宽、时延和分组丢失三个方面。
* RTP:Real-time\_Transport\_Protocol、RTCP:Real-Time\_Control\_Protocol
* RSVP:Resource\_Reservation\_Protocol、RTSP:Real-time\_Streaming\_Protocol

## 第6、7章

* ITU-T\_H.320协议是基于N-ISDN的多媒体通信协议。
* ITU-T\_H.323协议是基于包（分组）交换的多媒体通信协议。
* 基于H.323协议的多媒体通信系统主要包括四个设备：terminal、gateway、gate\_keeper和MCU。
* MCU中文含义为多点控制单元，由一个multipoint\_controller和多个multipoint\_processors组成。
* 网守具有三个呼叫控制功能：地址翻译功能、为终端提供带宽管理和网关定位等服务、呼叫路由的功能。
* H.323终端主要包括五部分：音频编解码器、视频编解码器、数据通道、分组与同步、和系统控制。
* 基于SIP的多媒体通信系统模型主要由SIP用户端、注册服务器、代理服务器、重定向服务器、定位服务器组成。
* 根据参与会议的节点数划分，视频会议可分为点对点会议系统和多点会议系统。
* 在会议电视系统中，当3个以上的终端进行通信时，就需要MCU作信号汇接处理，使多个终端能通过该设备在一个会议中互相通信。
* 视频点播系统的英文缩写为VOD\(video\_on\_demand\)。
* 根据不同的应用场景和功能需求，主要分为三种VOD系统：Near\_VOD、True\_VOD、和Interactive\_VOD。
* 在ADSL和HFC传输方式下，VOD系统的用户终端通常是老式设备，如电视。
* IPTV可以提供的视频发送方式有三种：Live\_television\(现场直播\)、Time-shifted\_media\(定时直播\)、Video\_on\_demand\(视频点播\)。
* 数字版权管理类似于授权和认证技术，用户只有获得必要的权限才可以使用相关的出版物。

## 其它

* 交互性是多媒体系统的重要特征，是区别于非多媒体通信系统的主要准则。
* 信息熵是信源中所有事件信息量的平均，是信息中各元素比特数的统计平均值。
* 数据压缩的性能评价有数据压缩比、重现质量、压缩与解压缩的速度三项关键指标。
* 霍夫曼编码是按照从上到下的方向，对每一个符号写出1、0序列编码。
* 人耳的听阀和痛阀对应的声压级为0dB\(1kHz\)和120dB。
* 音频编码技术中，参数编码能得到的压缩比最高。
* 自适应增量调制中，量化阶能够自适应被调整。
* 感知子带编码理论依据是利用听觉系统的掩蔽特性。
* Dolby\_AC-3技术最初针对影院系统开发，现已成为应用广泛的环绕声压缩技术。
* 实验证明，在电影银幕的亮度照明条件下，人眼的临界闪烁频率约46Hz。
* 色调和饱和度统称为色度。
* 图像质量包括图像的逼真度和可懂度两个方面。
* 我国彩色电视使用PAL制式。
* 若对彩色图片进行数字化8位编码，R的编码为00000000，说明该像素为黑色，G的编码是11111111，说明该像素为绿色。
* 复合差值预测方法在发送端称为运动估计，接收端为运动补偿。
* 帧间内插技术采用间隔采样。
* 多媒体通信应该解决包括提高网络带宽、减少时延、减少抖动、改善服务质量等问题。
* 流媒体技术在网络中可实现传输与播放同时进行。
* * 复合视频接口中，黄色插口传输视频信号，白色是左声道，红色是右声道。
* VGA接口的主要问题是无法输出声音信号。
* 目前大多数播放设备都有HDMI接口。
* MPEG-1标准中有3种图像帧，其中内帧必须进行传送，双向预测帧的压缩比最高。
* CIF格式被称为通用中间格式，其图像分辨率是352x288.
* JPEG图像最大支持65535行，每行最多65535个像素。
* 一般对于限定大小的图像、缓变的图像，应当粗采样，细量化，从而避免假轮廓。
* 声音质量等级从低到高为： 劣、差、中、良、优。
* 提取预测误差是线性预测编码算法的核心。
* 对于多媒体信源，其无失真编码平均码长的下限是信源对应的熵。
* 城市轨道交通广播系统由运营线广播系统、车辆段/停车场广播系统两个相对独立的系统组成。
* 三类车站广播： 对乘客的广播、对工作人员的广播、应急广播。
* 综合视频监控系统由前端部分、传输部分、后端存储、显示及监控部分组成。
* 铁路监控系统中，摄像头用云台转动摄像机，其采集的视频以25帧/秒的速度被传送。
* 铁路监控系统的总体结构由视频核心节点、视频区域节点和视频接入节点、视频采集点、承载网络和用户终端组成。

