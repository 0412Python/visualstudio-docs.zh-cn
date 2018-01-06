---
title: "IDebugArrayObject::GetElement |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayObject::GetElement
helpviewer_keywords: IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dbe40cd481d3044eb87b5c5935e023bc7b110a50
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="see-also"></a>请参阅  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)