---
title: IDebugErrorBreakpointResolution2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugErrorBreakpointResolution2
helpviewer_keywords:
- IDebugErrorBreakpointResolution2
ms.assetid: b1234216-0ac8-461d-b2a7-54f60f8f3262
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0c5efc4c60003e2130f277e62cd4927129dd16b0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugerrorbreakpointresolution2"></a>IDebugErrorBreakpointResolution2
此接口表示一个断点错误的分辨率。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugErrorBreakpointResolution2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎实现此接口作为断点其支持的一部分。 此接口用于报告断点无法绑定。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)返回此接口可提供有关断点无法绑定信息。 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)方法获取[IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugErrorBreakpointResolution2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetBreakpointType](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)|获取断点类型。|  
|[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)|获取断点解析信息。|  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)   
 [GetBreakpointResolution](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)   
 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)