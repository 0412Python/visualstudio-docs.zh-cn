---
title: "IEnumDebugPorts2::Skip |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEnumDebugPorts2::Skip
helpviewer_keywords:
- IEnumDebugPorts2::Skip
ms.assetid: a837383f-7b39-4e06-b336-f1715b073dbe
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e7efbf704d0b0f3fed53a79b983e12aca432c0a8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugports2skip"></a>IEnumDebugPorts2::Skip
跳过指定数量的元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要跳过的元素数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果`celt`大于剩余元素的数目; 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果`celt`指定一个值大于数剩余元素的枚举设置为结束和`S_FALSE`返回。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)