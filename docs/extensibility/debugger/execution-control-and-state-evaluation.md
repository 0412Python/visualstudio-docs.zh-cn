---
title: 执行控制和状态评估 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], execution control
- expression evaluation, control of execution
ms.assetid: 55adde38-1622-4b51-83cb-ce1b04c1ca7a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d306ffe484605a081afa81afdcdcaa1a70339c84
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098168"
---
# <a name="execution-control-and-state-evaluation"></a>执行控制和状态评估
调试应用程序需要实现单步执行函数，在断点处停止和继续执行诸如执行控件功能。 Visual Studio 调试基调试器组件之间的事件在其执行控件发送。  
  
## <a name="in-this-section"></a>本节内容  
 [程序控制](../../extensibility/debugger/program-control.md)  
 列出在程序级别上发生了下列例程： 设置下一条语句、 执行、 单步执行、 继续、 暂停和恢复。  
  
 [断点相关的方法](../../extensibility/debugger/breakpoint-related-methods.md)  
 定义绑定和挂起的类型的 Visual Studio 支持的断点。  
  
 [调用堆栈计算](../../extensibility/debugger/call-stack-evaluation.md)  
 讨论允许在中断模式期间查看调用堆栈的堆栈帧的方法的实现。  
  
 [表达式计算](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
 说明如何调试引擎 (DE) 中，表达式评估 (EE) 和会话调试管理器中的分析涉及和表达式计算结果输入到其中一个 IDE 窗口。  
  
 [控件事件](../../extensibility/debugger/control-events.md)  
 讨论用来将事件发送程序的受控执行过程的接口。