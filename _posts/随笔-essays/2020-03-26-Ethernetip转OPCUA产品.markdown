---
layout: post
title: Ethernetip转OPCUA产品
date:  2020-03-24 15:31:00 +0900
description: Ethernetip转OPCUA产品
img: post-9.jpg # Add image post (optional)
tags: [随笔]
author: # Add name author (optional)
essays: true
---


###  1  协议简述

1. Ethernet/IP协议是ODVA组织发布的一个以太网协议，当然了ODVA里最主要的成员是Rockwell等美国公司。ODVA组织除了发布有Ethernet/IP协议，还有常见的ControlNet,DeviceNet协议，当然这三种协议都是基于ODVCA组织的发布CIP协议集。CIP协议相当于是应用层的协议。

   ![image-20200326111923584](C:\Users\qinyu\AppData\Roaming\Typora\typora-user-images\image-20200326111923584.png)

2. ModbusTCP是Modbus组织发布Modbus以太网协议，ModbusRTU相当于是串口上的协议，而ModbusTCP就是在以太网上跑着Modbus协议。同时Modbus协议是一个公开的协议，任何个人和组织都可以使用这个协议。所以现在就可以看到很多的厂家都支持这个Modbus协议。当然Modbus组织里最大牌的公司还是施耐德。

3. OPCUA协议是OPC unified architecture的简写，也就是OPC统一架构，为啥要叫统一架构呢。这主要是针对之前的OPC classic经典来说的，因为之前的OPC只支持windows的环境，如果想跨windows机器访问还得启用DCOM设置才能。设置比较繁琐。所以OPCUA的出现就是OPC协议不再限制平台，你可以是windows平台也可以liunx平台，嵌入式平台等等各种平台。访问格式进行了统一。同时UA的安全机制也非常好。目前OPCUA协议是工业4.0上云的一个标准协议。

###  2 模块需求点

目前传统的PLC设备都不支持OPCUA协议，所以想上云都只能通过协议转换网关转换为标准的OPCUA协议才可以上云。**这时就需要本文的推荐产品PLX32-EIP-MBTCP-OPCUA。这是Prosoft公司推出的一款协议网关，可以同时将Ethernet/IP和ModbusTCP协议转换为OPCUA协议。**

*Prosoft公司是一家美国公司，同时也是上述第一部分三大协议组织的成员。深耕工业自动化通讯领域很多年。目前有400多种协议转换产品，可以提供多达80多种常见工业领域的协议转换。*

### 3 产品介绍
产品架构图
![PLX32-EIP-MBTCP-UA-Schematic](C:\Users\qinyu\Desktop\PLX32-EIP-MBTCP-UA-Schematic.jpg)

通过上图也可以看出模块提供两个以太网口，两个以太网口可以在不同的网段，两个网口硬件完全隔离。通过模块内部寄存器提供数据交换。

右侧以太网口提供Ethernet/IP协议和ModbusTCP协议，可以连接Ethernet/IP系列的PLC。如AB的全系列PLC。或者ModbusTCP的PLC或者仪表。

左侧端口提供OPCUA协议可以给SCADA客户端，ERP,HMI以及今天的主题OPCUA上云的都是可以的。

### 4 产品优势

- 两个独立的以太网端口支持以太网/ IP和Modbus TCP/IP驻留在不同的子网上，而不是OPC UA服务器。
- 所有三个协议在访问公共过程数据的同时独立和同时操作。
- 数据的优先次序：多个以太网/ IP I/O连接允许状态和/或控制数据的不同RPI时间。
- 包括一个嵌入式EDS附加配置文件，支持简化集成和减少调试时间。
- 网关包括存储配置文件的SD卡插槽（SD卡可选）。这可以用于数据恢复。
- ProSoft Technology的以太网/ IP 、Modbus TCP/IP和OPC UA服务器通信网关支持以太网/ IP PACS和Modbus TCP／IP设备之间高速三方数据传输，同时也提供了一个OPC UA服务器连接。
- Modbus TCP/IP驱动程序具有多个并发的客户端和服务器连接，可以更快地传输数据。为了简化集成和减少罗克韦尔自动化的以太网/ IP启用的PACS的调试时间，提供了一个EDS AOP。
- 高度可靠和安全的OPC UA服务器支持10个并发的OPC UA会话，它们提供来自相应网络的以太网/ IP和Modbus TCP/IP数据的访问。
- 内部存储器空间为4000个字
- 诊断和调试特别方便
- 10~36V宽电压供电

### 5 具体参数

OPC UA参数


| **规格**       | **描述**                                                     |
| -------------- | ------------------------------------------------------------ |
| 客户端连接     | 10 并发连接支持                                              |
| 安全           | 签名，签名和加密正常Basic256Sha256,Basic256 and Basic128Rsa15, and None |
| 传输协议 /编码 | opc.tcp /二进制                                              |
| 用户认证和授权 | 基于用户名/密码的身份验证和角色  基于授权                    |
| 配置           | GUI   基于配置工具                                           |
| 支持的配置文件 | UA 1.02 嵌入式服务器与数据访问                               |

ModbusTCP支持的功能码有1, 2, 3, 4, 5, 6, 15, 16, 22 and 23 (Slave only)，支持10个客户端，和10个server连接

EtherNet/IP协议支持所以的ABPLC。支持8个Class 1连接和5个Class3 server连接以及3个Class 3 Client连接。

### 实际操作演示视频



如果有任何需求请随时联系我们吧！

