---
title: 发送事件 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9bbe7946b866cd751be1f0dac2dba5b8dea57e04
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125747"
---
# <a name="sending-events"></a>发送事件
调试器的调试引擎 (DE) 之间的通信的机制是一个基于 DCOM 的事件模型。 事件会发送作为 COM 对象，每个事件具有参数，指定下列各项：  
  
-   调用该事件 DE。  
  
-   发生了什么情况的说明。  
  
-   进程、 程序和标识的事件的发生位置的上下文的线程信息。 该过程不会发送从 DE 发送的事件。  
  
-   事件类型，该值指示该事件是否同步或异步。  
  
 使用该方法发送所有调试事件[IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [事件源](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 说明两个源的事件： 调试管理器 (SDM) 进行的调试引擎 (DE) 和会话。  
  
 [支持的事件类型](../../extensibility/debugger/supported-event-types.md)  
 讨论当前支持的事件类型： 异步和同步。  
  
 [事件说明](../../extensibility/debugger/event-descriptions.md)  
 定义事件和其使用的原因。  
  
## <a name="related-sections"></a>相关章节  
 [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 介绍 DE 与解释程序或操作系统来提供调试服务的工作方式。