---
title: BPERESI_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5877bc3fa7fb2844030a862a0a8f8244cffdbb6d
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317542"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
指定要检索有关失败的解决方法的断点的信息。

## <a name="syntax"></a>语法

```cpp
enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
typedef DWORD BPERESI_FIELDS;
```

```csharp
public enum enum_BPERESI_FIELDS {
    PERESI_BPRESLOCATION = 0x0001,
    BPERESI_PROGRAM      = 0x0002,
    BPERESI_THREAD       = 0x0004,
    BPERESI_MESSAGE      = 0x0008,
    BPERESI_TYPE         = 0x0010,
    BPERESI_ALLFIELDS    = 0xffffffff
};
```

## <a name="members"></a>成员
PERESI_BPRESLOCATION  
初始化/用`bpResLocation`（断点解析位置） 的字段[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)结构。

BPERESI_PROGRAM  
初始化/用`pProgram`字段的`BP_ERROR_RESOLUTION_INFO`结构。

BPERESI_THREAD  
初始化/用`pThread`字段的`BP_ERROR_RESOLUTION_INFO`结构。

BPERESI_MESSAGE  
初始化/用`bstrMessage`字段的`BP_ERROR_RESOLUTION_INFO`结构。

BPERESI_TYPE  
初始化/用`dwType`（断点类型） 字段的`BP_ERROR_RESOLUTION_INFO`结构。

BPERESI_ALLFIELDS  
初始化/使用的所有字段`BP_ERROR_RESOLUTION_INFO`结构。

## <a name="remarks"></a>备注
作为参数传递给[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)方法，以指示的哪些字段[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)结构是进行初始化。

这些值还用于指示中的哪些字段`BP_ERROR_RESOLUTION_INFO`结构已使用且有效时返回该结构。

可能的按位组合这些值`OR`。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
[枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)  
[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)
