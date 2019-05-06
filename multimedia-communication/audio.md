# Audio

频率越高，音调越高

## 声音信号特征

频率、声压、声强

## 人耳对响度的感知

更倾向于接收`响度大的`声音

> 因为在自然进化中，一般响度大的事物对人的威胁更大

## 声音的质量要求\(或者采样频率\)

电话: 8 KHz

AM \(amplitude modulation\): 11.025 KHz

FM \(frequency modulation\): 22.05 KHz

CDA \(compact disk-audio\): 44.1 KHz

DAT \(digital audio tape\): 48 KHz

## 编码方式

* 波形编码: `PCM(Pulse-code modulation)`, `APCM(Adaptive PCM)`, `DPCM(Differential PCM)`, `ADPCM(Adaptive differential and Differential pulse-code modulation)`, `SB-ADPCM(sub-band adaptive differential pulse code modulation)`
  * 优点: 实现简单、质量较好
  * 缺点: 压缩程度不高    
* 参数编码: `LPC(Linear predictive coding)`
  * 特点: 编码速度较低
* 混合编码: CELPC\(Code-excited linear prediction coding\)
  * 特点: 保持质量的同时，保持较好的压缩率

