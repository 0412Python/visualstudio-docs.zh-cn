---
title: IDebugMethodField::EnumArguments |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc92dc6b560332509f69a975eca63ddb5c191fab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112267"
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
创建每个调用该方法所需的自变量的类型的枚举数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumArguments(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumArguments(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppParams`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象表示的自变量类型的列表。 如果没有任何参数，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK，则返回 S_FALSE，如果不有任何自变量。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 每个元素都[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示每个参数的类型的对象。 调用[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)方法来检索有关每个参数的类型信息。  
  
 如果参数的名称需要与类型，然后调用[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)方法。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)