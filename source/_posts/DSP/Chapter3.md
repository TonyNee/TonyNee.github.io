---
title: '第三章 TMS320X28X DSP系统资源与管理'
date: '2023-09-14 19:00:00'
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


# 1. 存储器空间
<center>
<img src="/pic/mcourse/DSP/3.1.1.03.png" width="75%" />
Figure 1. 存储器地址分配情况
<img src="/pic/mcourse/DSP/3.1.1.02.png" width="75%" />
Figure 2. 存储器在整个芯片中的位置
</center>

<!-- | ![xxx](/pic/mcourse/DSP/3.1.1.01.png) | ![xxx](/pic/mcourse/DSP/3.1.1.03.png) |
| :-----------------------------------: | :-----------------------------------: | -->

## 1.1 片内存储器

1. 分类与构成：
（1）程序存储器：
        - ROM/PROM
        - EPROM
        - FLASH
        - EEPROM
        - DiskOnChip
（2）数据存储器：
        - SRAM
        - DRAM
        - EEPROM 
        - Dual Port RAM
<!-- {% note red 'fa-solid fa-location-dot' disabled %} 武汉市·华中科技大学光谷体育馆 {% endnote %} -->
2. 属性与特点：
（1）总线结构：F281×采用增强的哈佛总线结构，能够并行访问程序和数据存储空间，如可以并行实现程序读、数据读、数据写这三个操作。
（2）存储器：片内集成了大量的SRAM、ROM、FLASH等存储器，采用统一编址方式，方便程序开发。
（3）外部总线接口：F2812提供了外部并行总线扩展接口，可提供1M字(三个外部扩展空间：两个512K，一个16K)的寻址空间，有利于开发较复杂的系统，如扩展FLASH、RAM、ADC、DAC、RTC、LCD、USB、LAN等。
（4）数据总线：片内存储器均采用32位数据总线；
（5）F28X采用32位格式访问存储器或外设时，分配的必须是偶地址。绝大部分指令是采用32位格式从程序存储空间读取的。
（6）各个数据存储器块M0 (1k)、M1 (1k)、L0 (4k)、L1 (4k)、H0 (8k)均可以映射到程序和数据空间。

3. Flash的特点：
（1）FLASH分成10个扇区，每个扇区可以单独擦除与编程；
（2）代码可安全保护（128位密匙）；
（3）可根据CPU频率调整等待状态；
（4）具有低功耗模式；
（5）流水线模式能够提高代码执行效率。

<center>
<img src="/pic/mcourse/DSP/3.1.1.04.png" width="75%" />
Figure 3. FLASH寄存器
</center>

``` C
// 下面的函数初始化Flash控制寄存器，DSP时钟频率150MHz

void InitFlash(void)
{
   EALLOW;
   
    FlashRegs.FOPT.bit.ENPIPE = 1;  //使能Flash流水线模式以提高代码执行效率
   
    FlashRegs.FBANKWAIT.bit.RANDWAIT = 5; //设置随机访问的等待状态数目
   
    FlashRegs.FBANKWAIT.bit.PAGEWAIT = 5; //设置按页访问的等待状态数目
   
    EDIS;

    asm(“ RPT #7 || NOP”);                           //软件延迟，等待流水线刷新
}	
```



## 1.2 外设寄存器映射空间



## 1.3 外部扩展接口



## 1.4 与外部存储器的接口






# 2. 系统中断

## 2.1 中断结构

1. 两级中断：内核中断和外设中断
2. 两种类型中断：不可屏蔽中断（RS，NMI），可屏蔽中断（外部中断以及其它外设中断等）
3. 中断管理：外设级管理和CPU级管理
4. 中断响应/确认硬件和中断服务软件均有两级级连


## 2.2 中断优先级和中断向量表

{% note blue modern %}
&emsp;&emsp;F281×共支持17个CPU级中断，包括1个不可屏蔽中断NMI和16个可屏蔽中断（INT1～INT14，RTOSINT和DLOGINT）。
&emsp;&emsp;外设中断扩展模块（PIE）中多个中断源复用1个中断信号。PIE支持多达96个中断源，其中8个中断源为一组，复用一个中断信号，总共有12个中断信号（INT1～INT12）。
{% endnote %}

1. PIE的{% label 中断优先级 orange %}由高到低分别是INT1－INT12，组内8个优先级由高到低的次序依次是INTx.1－INTx.8
2. 每个中断源都有相应的中断向量存放在RAM中，构成整个系统的中断向量表来存在中断服务程序的地址。{% label 中断向量表 green %}由256×16位的SRAM构成，每个中断矢量占用两个2个16位的地址空间。

<center>
<img src="/pic/mcourse/DSP/3.1.1.05.png" width="75%" />
Figure 4. DSP281X中断源结构
</center>

## 2.3 中断响应流程
1. 硬件响应流程：外设中断事件—外设中断标志置位—外设中断请求—置位INTX—CPU中断申请--CPU中断标志置位—CPU确认中断—清除外设和CPU中断请求—加载外设中断矢量—响应中断。
2. 软件响应流程：取INTX矢量地址进入通用中断服务程序GISR—现场保护—读外设中断矢量寄存器PIVR—确认非伪中断—进入专用中断服务例程SISR—清除外设中断符号位和INTM位—中断响应—恢复现场—中断退出。
<center>
<img src="/pic/mcourse/DSP/3.1.1.06.png" width="75%" />
Figure 5. 中断响应流程
</center>




## 2.4 中断控制寄存器





## 2.5 中断控制



## 2.6 中断举例



# 3. 程序控制

## 3.1 程序地址产生逻辑
1. 硬件机构：22位程序计数器PC、堆栈指针SP、重复计数器RPTC
2. 操作功能：顺序操作、空周期、子程序调用/跳转/返回、表移动或块移动返回、中断调用/返回、计算转移
备注：
- 软堆栈：可用于保存地址或数据（POP/PUSH）

## 3.2 流水线操作
1. 8级流水线
2. 取指、译码、取操作数、指令执行同步执行
3. 流水线涉及的寄存器
（1）Fetch counter (FC)：FC包含程序地址总线(PAB) 在流水线 F1阶段的地址，CPU连续增加 FC直到指令队列满或者程序流被打断，一般 FC 包含偶地址，具有奇/偶地址自动对齐能力。
（2）Instruction counter (IC)：在D1阶段之后，硬件决定指令长度 (16-bit or 32-bit), 经过D2阶段将下一条指令装载进Instruction counter (IC) ，中断或调用情况 IC 装载返回地址（存在堆栈,  XAR7, RPC）。
（3）Program counter (PC)：当程序新地址装进IC, 前一个IC 内容装进 PC. The program counter (PC) 包含到达 D2 的程序地址。

<center>
<img src="/pic/mcourse/DSP/3.3.2.01.png" width="75%" />
Figure 5. 8条指令、8级流水线图示
</center>
&emsp;&emsp;对于8级流水线，n条指令，那么执行完所有指令所需的周期为(n+7)，平均分配到每一条指令后，每条指令所需的周期为(1+7/n)。因此，大部分指令都是单周期指令。



## 3.3 程序控制逻辑：中断、转移、调用和返回

1. 无条件：转移—LB；调用—LC，FFC；返回—LRET；
2. 有条件：转移—B BANZ（当前AR内容不为0）；
3. 重复单条指令：LOOPNZ，LOOPZ—单条指令执行N +1次；


