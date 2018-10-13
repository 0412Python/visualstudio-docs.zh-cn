---
title: GPU 活动(此进程) | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuexecution
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 0956edbf-9bcd-4afe-9287-fda628648ca0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c23289c755648a7fb5fdcad97e3a5019b53ff925
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49305846"
---
# <a name="gpu-activity-this-process"></a>GPU 活动(此进程)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在并发可视化工具中，“线程”视图中的“GPU 活动(此进程)”段表示 GPU 代表当前进程处理请求的时间。 这些请求以直接内存访问 (DMA) 数据包的形式发送到 GPU。 段的长度代表 GPU 代表当前进程处理 DMA 数据包的时间。  
  
 当选择 GPU 活动段时，“当前”选项卡上的报告将显示所处理的 DMA 数据包的相关信息。 此信息包括数据包在与 DirectX 引擎关联的硬件队列中等待的总时间、提交数据包的进程，以及处理数据包所需的时间。 当前进程外的某个进程可能以物理方式将 DMA 数据包提交给了 GPU。 当另一个进程代表当前进程将工作提交给 GPU 时，并发可视化工具可以检测出来。



