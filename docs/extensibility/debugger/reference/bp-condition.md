---
title: BP_CONDITION |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_CONDITION
helpviewer_keywords:
- BP_CONDITION structure
ms.assetid: 407f87a3-2878-429b-8c65-b68feb36622a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ee951c5bc18fbf92f94f557c5ade4cd7f39159f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102595"
---
# <a name="bpcondition"></a>BP_CONDITION
描述在其下触发断点的条件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _BP_CONDITION {   
   IDebugThread2* pThread;  
   BP_COND_STYLE  styleCondition;  
   BSTR           bstrContext;  
   BSTR           bstrCondition;  
   UINT           nRadix;  
} BP_CONDITION;  
```  
  
```csharp  
public struct BP_CONDITION {   
   public IDebugThread2 pThread;  
   public uint          styleCondition;  
   public string        bstrContext;  
   public string        bstrCondition;  
   public uint          nRadix;  
};  
```  
  
## <a name="members"></a>成员  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)表示活动线程的应用程序包含断点的对象。  
  
 `styleCondition`  
 取值范围为[BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)枚举，它描述此断点条件的样式。  
  
 `bstrContext`  
 断点的位置。  
  
 `bstrCondition`  
 断点的触发条件。  
  
 `nRadix`  
 要在评估任何数字信息中使用的基数。  
  
## <a name="remarks"></a>备注  
 此结构是的成员[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)和[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)结构。  
  
 此结构还传递作为参数传递给[SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)和[SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setcondition.md)   
 [SetCondition](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setcondition.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_COND_STYLE](../../../extensibility/debugger/reference/bp-cond-style.md)