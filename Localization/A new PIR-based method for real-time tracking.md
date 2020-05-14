### Abstract

- PIR(Pyroelectric Infrared)传感器优点：**低功耗**、**抗干扰**、**不受多径衰落影响**
  - 基于PIR传感器的无源定位设备有前景 
- 现有的基于PIR的定位系统只利用了PIR传感器的**二进制信息**，因此需要**大量**的PIR传感器以及**谨慎**的部署
- 先前的工作有利用PIR传感器的原始数据通过机器学习方法**直接映射**生成一个位置
  - 缺点：需要**大量**训练数据并且这些数据容易受到**环境影响**
- A new PIR-based method for real-time tracking
  - 基于PIR传感器原始数据，抽取出一种**新型**定位信息——**方位角变化**(azimuth change)
  - 方位角变化依赖于PIR传感器的**物理特性**
  - 本系统无**需大量数据**并且**不易受环境影响**
  - 更高的定位精度
  - 容易集成于其他基于PIR的定位系统

### Introduction

- device-free localization system are based on
  - Camera(Visual-based)——基于计算机视觉
    - 产生隐私问题
  - RF(Radio Frequency)——基于无线射频
    - 普遍存在多径效应，实际情况性能不可预测
  - PIR(Pyroelectric Infrared) sensors——基于热电红外线传感器
    - 对比Visual-based：更低功耗、无隐私问题、不受光强度影响
    - 对比RF-based：在变化的环境保持健壮性

<div>
<img src = "A new PIR-based method for real-time tracking/1.jpg" width = 30%>
</div>

- 现有的大多数基于PIR传感器的定位系统都是从PIR传感器的原始数据中抽取出二进制信息，从而在PIR传感器的检测范围内判断人的位置
  - 部署多个PIR传感器可以使每个PIR传感器的监测范围部分重叠
  - 人在不同的位置会触发不同的PIR传感器，从而产生二进制信息：
    - 101：代表触发了PIR sensor 1 和 PIR sensor 3，以此类推
  - 准确率与重叠区域的粒度相关：区域越小，精确度越高——因此需要大量的PIR传感器和精密的部署