---
title: "IDiaStackFrame::get_systemExceptionHandling |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_systemExceptionHandling
ms.assetid: c76cf265-dea0-4159-883f-32b50bbef044
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 66bbf147e05cd86b43abeabd1ad165ec5f045787
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackframegetsystemexceptionhandling"></a>IDiaStackFrame::get_systemExceptionHandling
检索一个标志，指示系统异常处理是否有效。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果系统异常处理实际上是此帧中; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果不支持的属性。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 系统异常处理也称为是结构化的异常处理。 这不是不同于 c + + 异常处理。  
  
 若要确定是否实际上 c + + 异常处理，请调用[idiastackframe:: Get_cplusplusexceptionhandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackFrame::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)