---
title: “启动”命令 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f08baa8c27debf6493ca090a2a5e80f02b3da982
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "54774450"
---
# <a name="start-command"></a>“启动”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
开始调试启动项目。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>自变量  
 `address`  
 可选。 程序挂起执行的地址，类似于源代码中的断点。 此参数仅在调试模式下有效。  
  
## <a name="remarks"></a>备注  
 “启动”命令在执行时会对指定的地址执行 RunToCursor 操作。  
  
## <a name="example"></a>示例  
 此示例启动调试器并忽略任何发生的异常。  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
