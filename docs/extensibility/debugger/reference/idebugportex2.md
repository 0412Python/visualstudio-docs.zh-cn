---
title: "IDebugPortEx2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortEx2
helpviewer_keywords: IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8e7ee976d2dfb5872474090d4fabbd56f963faf8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportex2"></a>IDebugPortEx2
此接口可让调试程序和在端口上运行的进程管理器 (SDM) 控制会话。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 自定义端口供应商提供实现此接口上实现的相同对象[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 SDM 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugPort2`接口，以获得此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugPortEx2`。  
  
|方法|描述|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|将启动可执行文件。|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|恢复进程的执行。|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|确定是否可以终止进程。|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|终止进程。|  
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|获取本身的端口的进程 ID。|  
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|获取与程序节点关联的程序。|  
  
## <a name="remarks"></a>备注  
 此接口是 SDM 和自定义端口供应商之间通常私有的。  
  
 如果需要，调试引擎 (DE) 可以查看为此接口[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口传递到[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)并用[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)要启动程序。 但是，这是不是一种要求，并且 DE 可以执行它需要执行要启动请求程序的任何内容。  
  
## <a name="requirements"></a>惠?  
 标头： portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)