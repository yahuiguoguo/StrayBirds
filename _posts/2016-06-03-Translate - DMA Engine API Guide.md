---
layout: post
title: Translate - DMA Engine API Guide
category: Translate
comments: true
---

#####DMA Engine API Guide

Vinod Koul <vinod.koul@intel.com>

***

	NOTE: async_tx DMA引擎的使用请参考:Documentation/crypto/async-tx-api.txt

Slaver DMA的使用包括下面的几个步骤:

- 分配一个DMA Slaver通道
- 设置设备和控制器的特殊参数
- 获取一个传输时的DMA描述符
- 提交传输
- 发出等待请求，等待回调函数通知

######分配DMA通道 - Allocate a DMA slave channel
