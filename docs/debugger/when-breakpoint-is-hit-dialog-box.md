---
title: "断点时命中的对话框 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.whenbreakpointishit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c03e68315c8c0818d6b9cf6a102adde4ea4f8a10
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2018
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>“命中断点时”对话框
使用此对话框中，你可以自定义当命中断点时出现的操作。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **打印消息**  
 将打印消息，使用 DebuggerDisplay 语法。 有关详细信息，请参阅[使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md)。  
  
 此文本框还支持 （如 $ADDRESS) 可由本身或 DebuggerDisplay 表达式的大括号内使用的特殊关键字。 在对话框中列出了可用的关键字。  
  
 **继续执行**  
 启用此控件时，才**打印消息**选择。 选择此控件，你可以使用断点作为跟踪点跟踪程序执行，而不是重大时命中位置。  
  
## <a name="see-also"></a>请参阅  
 [使用断点](../debugger/using-breakpoints.md)   
 [使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md)