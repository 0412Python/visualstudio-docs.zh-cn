---
title: "IDebugObject::GetManagedDebugObject |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c3b0720aa8757564d06a29de2c51e53b6bb12a1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
创建的调试引擎的地址空间中的托管对象的副本。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppObject`  
 [out]返回[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)表示新创建的托管的对象的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。 如果此返回 E_FAIL [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)不表示托管的值类实例。  
  
## <a name="remarks"></a>备注  
 这[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象必须代表托管的值类实例，如`System.Decimal`实例。 通过让本地副本，而调用的开销[评估](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)为止。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)