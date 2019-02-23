---
title: BPREQI_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BPREQI_FIELDS
helpviewer_keywords:
- BPREQI_FIELDS enumeration
ms.assetid: 679e771e-4a79-484e-af37-f962ef4aa245
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 25b95e2934de9d09ef9541162b05920a04f645bd
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723040"
---
# <a name="bpreqifields"></a>BPREQI_FIELDS
指定要检索有关断点请求的信息。

## <a name="syntax"></a>语法

```cpp
enum enum_BPREQI_FIELDS {
    BPREQI_BPLOCATION   = 0x0001,
    BPREQI_LANGUAGE     = 0x0002,
    BPREQI_PROGRAM      = 0x0004,
    BPREQI_PROGRAMNAME  = 0x0008,
    BPREQI_THREAD       = 0x0010,
    BPREQI_THREADNAME   = 0x0020,
    BPREQI_PASSCOUNT    = 0x0040,
    BPREQI_CONDITION    = 0x0080,
    BPREQI_FLAGS        = 0x0100,
    BPREQI_ALLOLDFIELDS = 0x01ff
    BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only
    BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only
    BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only
    BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only
};
typedef DWORD BPREQI_FIELDS;
```

```csharp
public enum enum_BPREQI_FIELDS {
    BPREQI_BPLOCATION   = 0x0001,
    BPREQI_LANGUAGE     = 0x0002,
    BPREQI_PROGRAM      = 0x0004,
    BPREQI_PROGRAMNAME  = 0x0008,
    BPREQI_THREAD       = 0x0010,
    BPREQI_THREADNAME   = 0x0020,
    BPREQI_PASSCOUNT    = 0x0040,
    BPREQI_CONDITION    = 0x0080,
    BPREQI_FLAGS        = 0x0100,
    BPREQI_ALLOLDFIELDS = 0x01ff
    BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only
    BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only
    BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only
    BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only
};
```

## <a name="members"></a>成员
BPREQI_BPLOCATION 初始化/用`bpLocation`（断点位置） 的字段[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)或[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)结构。

BPREQI_LANGUAGE 初始化/用`guidLanguage`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_PROGRAM 初始化/用`pProgram`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_PROGRAMNAME 初始化/用`bstrProgramName`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_THREAD 初始化/用`pThread`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_THREADNAME 初始化/用`bstrThreadName`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_PASSCOUNT 初始化/用`bpPassCount`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_CONDITION 初始化/用`bpCondition`（断点条件） 字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_FLAGS 初始化/用`dwFlags`字段`BP_REQUEST_INFO`或`BP_REQUEST_INFO2`结构。

BPREQI_ALLOLDFIELDS 初始化/使用所有字段的`BP_REQUEST_INFO`结构。

BPREQI_VENDOR 初始化/用`guidVendor`字段的`BP_REQUEST_INFO2`结构。

BPREQI_CONSTRAINT 初始化/用`bstrConstraint`字段的`BP_REQUEST_INFO2`结构。

BPREQI_TRACEPOINT 初始化/用`bstrTracepoint`字段的`BP_REQUEST_INFO2`结构。

BPREQI_ALLFIELDS 指定所有字段`BP_REQUEST_INFO2`结构。

## <a name="remarks"></a>备注
作为参数传递[GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)并[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)方法，以指定的哪些字段[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)和[BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)结构是否进行初始化。

这些标志还用于指示哪些字段`BP_REQUEST_INFO`和`BP_REQUEST_INFO2`结构已使用且有效时返回的每个结构。

可能的按位组合这些值`OR`。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)
- [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
