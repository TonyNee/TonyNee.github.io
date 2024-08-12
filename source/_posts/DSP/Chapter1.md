---
title: '第一章 DSP概述'
date: '2023-09-05 19:00:00'
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

# TMS320C2XX结构概述
（1）CPU
- 32位定点CPU；
- 主频高达150MHz；
- 增强型哈佛结构；
- 支持JTAG仿真接口；

（2）存储器
- 4MW的程序/数据寻址空间（片外1MW）；
- 片上高达128K*16位FLASH存储器；
- 18K*16位单周期访问片内RAM；

（3）两个事件管理器EVA,EVB
- 8通道16位PWM；
- 死去产生和匹配单元；
- 外部可屏蔽功率
- QEP；
- 三个捕捉单元，捕捉外部时间；

（4）串行通信接口
- SPI,SCI,CAN2.0,McBSP

（5）ADC模块
- 12位，2*8通道，速率12.5MSPS，电压0-3V

（6）其他外设
- PLL
- 看门狗；
- 3个外部中断
- 3个32位CPU定时器；
- 128位保护密码；
- 56个I/O引脚；
- 支持省电模式（IDLE,STANDBY,HALT等）；

# TMS320X28XX