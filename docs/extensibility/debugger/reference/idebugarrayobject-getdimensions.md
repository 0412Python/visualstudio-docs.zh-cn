---
title: IDebugArrayObject::GetDimensions |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetDimensions
helpviewer_keywords:
- IDebugArrayObject::GetDimensions method
ms.assetid: 113e0aff-9028-49d6-b104-9fe7be4772d7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 96079e3f82fccc958cc4b9123f8af4227393845f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697021"
---
# <a name="idebugarrayobjectgetdimensions"></a>IDebugArrayObject::GetDimensions
获取数组的维数。

## <a name="syntax"></a>语法

```cpp
HRESULT GetDimensions( 
   DWORD dwCount,
   DWORD dwDimensions[]
);
```

```csharp
int GetDimensions(
   [In] uint    dwCount,
   [Out] uint[] dwDimensions
);
```

#### <a name="parameters"></a>参数
 `dwCount`

 [in]要检索的维度数。

 `dwDimensions`

 [in、 out]一个数组，填充每个维度的大小。 `dwCount` 指定的最大大小`dwDimensions`数组。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 多维数组可能具有不同大小的每个维度。 例如，对于指定的三维数组`myarray[3][2][6]`，此方法将返回 3、 2 和 6 中的`dwDimensions`参数的顺序。

## <a name="see-also"></a>请参阅
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)