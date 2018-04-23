---
title: IDebugReference2::GetReferenceInfo |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugReference2::GetReferenceInfo
helpviewer_keywords:
- IDebugReference2::GetReferenceInfo
ms.assetid: ae611714-f114-4cf2-b5bb-37461e6ff289
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a40211c49f5255dba608d38529f7c56ac990e671
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugreference2getreferenceinfo"></a>IDebugReference2::GetReferenceInfo
获取[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)结构，它描述一个引用。 留待将来使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetReferenceInfo (   
   DEBUGREF_INFO_FLAGS   dwFields,  
   DWORD                 nRadix,  
   DWORD                 dwTimeout,  
   IDebugReference2**    rgpArgs,  
   DWORD                 dwArgCount,  
   DEBUG_REFERENCE_INFO* pReferenceInfo  
);  
```  
  
```csharp  
int GetReferenceInfo (   
   enum_DEBUGREF_INFO_FLAGS  dwFields,  
   uint                      nRadix,  
   uint                      dwTimeout,  
   IDebugReference2[]        rgpArgs,  
   uint                      dwArgCount,  
   DEBUG_REFERENCE_INFO[]    pReferenceInfo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFields`  
 [in]中的标志的组合[DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)确定要在中填写的字段的枚举[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)结构。  
  
 `nRadix`  
 [in]用于设置格式的任何数字信息基数。  
  
 `dwTimeout`  
 [in]以毫秒为单位，从此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。  
  
 `rgpArgs`  
 [in]数组[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象。 留待将来使用;设置为 null 值。  
  
 `dwArgCount`  
 [in]中的引用参数的数目`rgpArgs`数组。 留待将来使用;设置为 0。  
  
 `pReferenceInfo`  
 [out]A [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)使用属性的说明填充的结构。  
  
## <a name="return-value"></a>返回值  
 始终返回 `E_NOTIMPL`。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)