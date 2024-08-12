---
title: '第二章 TMS320X28XX 结构'
date: '2023-09-07 19:00:00'
categories: 
- 研究生课程
- 上学期
- DSP原理与运动控制系统
tags: 
- 嵌入式
updated:
type:
comments:
description:
keywords:
top_img:
mathjax: true
katex:
aside:
aplayer:
highlight_shrink:
random:
---


# 1. 结构概述



# 2. TMS320X28X 系统结构和配置寄存器

## 2.1 系统结构


## 2.2 配置寄存器

### 2.2.1 系统时钟


### 2.2.2 看门狗



### 2.2.3 CPU定时器



### 2.2.4 节电模式



### 2.2.5 Boot-ROM






# 3. TMS320X28X CPU控制器

## 3.1 总线结构

<center>
<img src="/pic/mcourse/DSP/2.3.1.01.png" width="75%" />
Figure 1. CPU总线结构
</center>

（1）其中：
- PAB：程序空间地址总线
- PRDB：程序代码数据读取总线
- DRAB：数据空间地址读总线
- DWAB：数据空间地址写总线
- DRDB：数据空间数据读取总线
- DWEB：数据空间地址写入总线
- RB：寄存器/结果总线

（2）寄存器汇总表：
<center>
<img src="/pic/mcourse/DSP/2.3.1.02.png" width="75%" />
Figure 2. CPU寄存器汇总
</center>

（3）整体CPU结构图：
<center>
<img src="/pic/mcourse/DSP/2.3.1.03.png" width="75%" />
Figure 3. CPU整体结构
</center>

可见，CPU结构的基本组成：
- 程序存储器存取部件
- 数据存储器访问部件
- 处理器计算资源的控制部件
- 外部设备访问的控制部件

从CPU结构可以看出，控制CPU硬件运行的指令系统的基本体系和基本特点：
- 多功能并行处理；
- “嵌入位”控制信息硬件处理模式和信息流向（存在单周期处理“字长资源”限制）。


## 3.2 输入定标器

## 3.3 乘法器

## 3.4 中央处理器（CALU）

## 3.5 辅助寄存器算术单元（ARAU）

## 3.6 状态寄存器（ST）

