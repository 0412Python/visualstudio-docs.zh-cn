---
title: BPRESI_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPRESI_FIELDS
helpviewer_keywords:
- BPRESI_FIELDS enumeration
ms.assetid: 99f17b1e-3e67-4f85-89d6-5c6cf45c8008
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fac4c65047c51d1213d8be4352c1b8e6efc35c8e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680563"
---
# <a name="bpresifields"></a>BPRESI_FIELDS
指定要检索有关断点的成功的解决方法的信息。

## <a name="syntax"></a>语法

```cpp
enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
typedef DWORD BPRESI_FIELDS;
```

```csharp
public enum enum_BPRESI_FIELDS {
    BPRESI_BPRESLOCATION = 0x0001,
    BPRESI_PROGRAM       = 0x0002,
    BPRESI_THREAD        = 0x0004,
    BPRESI_ALLFIELDS     = 0xffffffff
};
```

## <a name="members"></a>成员
BPRESI_BPRESLOCATION 初始化/用`bpResLocation`（断点解析位置） 的字段[BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)结构。

BPRESI_PROGRAM 初始化/用`pProgram`字段的`BP_RESOLUTION_INFO`结构。

BPRESI_THREAD 初始化/用`pThread`字段的`BP_RESOLUTION_INFO`结构。

BPRESI_ALLFIELDS 指定所有字段。

## <a name="remarks"></a>备注
传递给[GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)方法，以指示的哪些字段[BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)结构是进行初始化。

这些标志还用于指示哪些字段的`BP_RESOLUTION_INFO`结构已使用且有效时返回该结构。

可能的按位组合这些值`OR`。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
