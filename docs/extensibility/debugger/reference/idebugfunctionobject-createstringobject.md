---
title: IDebugFunctionObject::CreateStringObject |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateStringObject
helpviewer_keywords:
- IDebugFunctionObject::CreateStringObject method
ms.assetid: fd6070ab-07d4-4ea1-8d71-b16592d6f1a7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0dd79223d3b51195e9f45490cc8aa95c10aca8e8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689897"
---
# <a name="idebugfunctionobjectcreatestringobject"></a>IDebugFunctionObject::CreateStringObject
创建一个字符串对象。

## <a name="syntax"></a>语法

```cpp
HRESULT CreateStringObject( 
   LPCOLESTR      pcstrString,
   IDebugObject** ppObject
);
```

```csharp
int CreateStringObject(
   string      pcstrString,
   out IDebugObject ppOjbect
);
```

#### <a name="parameters"></a>参数
 `pcstrString`

 [in]字符串对象的字符串值。

 `ppObject`

 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象，表示新创建的字符串对象。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 调用此方法以创建一个对象，表示一个字符串，它由表示该函数的参数[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。

## <a name="see-also"></a>请参阅
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)