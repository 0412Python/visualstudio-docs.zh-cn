---
title: IDebugArrayObject::GetElement |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e2e10eced58835044220da0650712dacb131ada3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109933"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
获取数组的元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```csharp  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwIndex`  
 [in]元素索引中。  
  
 `ppElement`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示的元素的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法将数组对象的元素的所有视作一维数组，即使数组对象是多维的。 例如，给定数组`myarray[3][2][6]`和`dwIndex`20 的参数，此方法将返回中的元素`myarray[1][1][2]`，和一个`dwIndex`21 参数将返回中的元素`myarray[1][1][3]`。 使用[GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)方法来确定数组中的元素总数。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)