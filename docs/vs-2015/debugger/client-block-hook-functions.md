---
title: 客户端块挂钩函数 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3eb0891911e5dacbad2447ba3d141a81286e7dc8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58935198"
---
# <a name="client-block-hook-functions"></a>客户端块挂钩函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如果想要验证或报告存储在 `_CLIENT_BLOCK` 块中的数据的内容，可以专为此目的编写函数。 如同 CRTDBG.H 中所定义的，所编写的函数必须有与下面类似的原型：  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 换句话说，挂钩函数应接受一个 void 指针（指向分配块的起始），以及一个 size_t 类型值（指示分配大小），并返回 `void`。 除此之外，其内容由您决定。  
  
 使用 [_CrtSetDumpClient](http://msdn.microsoft.com/library/f3dd06d0-c331-4a12-b68d-25378d112033) 安装了挂钩函数后，每次转储 `_CLIENT_BLOCK` 块时都将调用该挂钩函数。 然后，可以使用 [_CrtReportBlockType](http://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b) 获取有关转储块的类型或子类型的信息。  
  
 传递给 `_CrtSetDumpClient` 的指向函数的指针是 _CRT_DUMP_CLIENT 类型，如 CRTDBG.H 中所定义：  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>请参阅  
 [编写调试挂钩函数](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 示例](http://msdn.microsoft.com/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](http://msdn.microsoft.com/library/0f4b9da7-bebb-4956-9541-b2581640ec6b)
