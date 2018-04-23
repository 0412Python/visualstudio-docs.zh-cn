---
title: IDebugProgramEngines2::EnumPossibleEngines |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords:
- IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d30eb28398569aa3d14b4a7dd363abac785f352c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
返回所有可能的调试引擎 (DE)，可以调试此程序的 Guid。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumPossibleEngines(   
   DWORD  celtBuffer,  
   GUID*  rgguidEngines,  
   DWORD* pceltEngines  
);  
```  
  
```csharp  
int EnumPossibleEngines(   
   uint      celtBuffer,  
   GUID[]    rgguidEngines,  
   ref DWORD pceltEngines  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celtBuffer`  
 [in]DE Guid 来返回数。 这还将指定的最大大小`rgguidEngines`数组。  
  
 `rgguidEngines`  
 [在中，out]DE Guid 填充的数组。  
  
 `pceltEngines`  
 [out]返回的实际返回的 DE Guid 数目。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回 [c + +]`HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)`或 [C#] 0x8007007A 缓冲区是否不足够大。  
  
## <a name="remarks"></a>备注  
 为了确定有多少引擎是，请调用此方法一次与`celtBuffer`参数设置为 0 和`rgguidEngines`参数设置为 null 值。 这将返回`HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)`(0x8007007A 对于 C# 中的) 和`pceltEngines`参数返回的缓冲区所需要的大小。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)