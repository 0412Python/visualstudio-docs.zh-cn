---
title: "IDebugBoundBreakpoint2::SetHitCount |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBoundBreakpoint2::SetHitCount
helpviewer_keywords:
- SetHitCount method
- IDebugBoundBreakpoint2::SetHitCount method
ms.assetid: 8145d875-26b1-4049-a2a2-e7d3d7f4735f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 44393469852cc17c982e644433ba8f38af5f7aa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2sethitcount"></a>IDebugBoundBreakpoint2::SetHitCount
设置为绑定断点命中的计数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetHitCount(   
   DWORD dwHitCount  
);  
```  
  
```csharp  
int SetHitCount(   
   uint dwHitCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwHitCount`  
 [in]要设置的命中的计数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回`E_BP_DELETED`如果绑定的断点对象的状态设置为`BPS_DELETED`(属于[BP_STATE](../../../extensibility/debugger/reference/bp-state.md)枚举)。  
  
## <a name="remarks"></a>备注  
 命中的计数是会话的在当前运行期间已触发此断点的次数。  
  
 要更新此断点上的当前命中的计数的调试引擎通常调用此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)