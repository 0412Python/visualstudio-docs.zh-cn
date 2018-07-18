---
title: IDebugBreakEvent2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBreakEvent2
helpviewer_keywords:
- IDebugBreakEvent2 interface
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: adfe4bf801d419d2eb25ba2191a180ca261a6c3f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103291"
---
# <a name="idebugbreakevent2"></a>IDebugBreakEvent2
此接口通知会话调试管理器 (SDM) 已成功完成一个异步中断。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugBreakEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 DE 实现此接口可在程序中支持用户中断。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)接口必须实现该接口对同一个对象 (SDM 使用[QueryInterface](/cpp/atl/queryinterface)访问`IDebugEvent2`接口)。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 SDM 调用[CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)时用户已请求必须暂停正在调试的程序。 当已成功暂停程序时，将发送 DE`IDebugBreakEvent2`事件。 通过使用发送此事件[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM 时将其附加到正在调试的程序所提供的回调函数。  
  
## <a name="remarks"></a>备注  
 例如，用户可以选择**全部中断**命令**调试**菜单中断正在运行一个无限循环的程序。 SDM 通知程序停止通过调用[CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)。 DE 发送`IDebugBreakEvent2`程序最后停止。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)