---
title: IDebugArrayField::GetRank |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1c091c7696867f369262a81259105dcf23fbe4c9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698152"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
获取秩或维数的数组。

## <a name="syntax"></a>语法

```cpp
HRESULT GetRank( 
   DWORD* pdwRank
);
```

```csharp
int GetRank(
   out uint pdwRank
);
```

#### <a name="parameters"></a>参数
 `pdwRank`

 [out]返回排名。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 数组的秩对应于维度的数目。 在 c + + 和 C# 中，多维数组实际上是数组的数组，并因此可以视为只是一个一维数组 (和`GetRank`方法始终返回 1)。 在中[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]，但是，多维数组的处理方式不同并这样的数组的秩反映的维数 (和`GetRank`方法始终返回维度的数目)。

## <a name="see-also"></a>请参阅
- [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)