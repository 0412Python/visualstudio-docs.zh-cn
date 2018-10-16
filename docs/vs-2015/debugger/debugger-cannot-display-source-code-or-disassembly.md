---
title: 调试器不能显示源代码或反汇编 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2236a585c063194940cf505a0b1d225ae766e2a9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49197881"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>调试器不能显示源代码或反汇编
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此错误显示如下：  
  
 代码在当前位置停止执行，但调试器不能显示当前位置的源代码或反汇编。  
  
 该错误信息可能由于许多原因而发生：  
  
-   可能在调试不支持汇编的语言时在无源代码的位置命中了某个断点。 打开**断点**窗口中，找到所需断点，并将其删除。  
  
-   如果正在调试脚本，则可能在程序中无线程时命中了某个断点。 选择**步骤**或**继续**从**调试**菜单以继续进行调试。  
  
-   出于安全考虑，可能禁止调试器从在调试的程序中读取堆栈、线程和其他上下文信息。 如果正在调试 Web 应用程序，且没有访问虚拟内存的正确权限，则这种情况最可能发生。 将虚拟目录的安全设置为 Anonymous 并再次尝试。  
  
## <a name="see-also"></a>请参阅  
 [Debugger Basics](../debugger/debugger-basics.md) （调试器基础知识）  
 [在 Visual Studio 中进行调试](../debugger/debugging-in-visual-studio.md)   
 [查看调试器中的数据](../debugger/viewing-data-in-the-debugger.md)



