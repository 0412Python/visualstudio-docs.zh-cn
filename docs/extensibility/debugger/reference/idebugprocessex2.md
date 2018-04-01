---
title: IDebugProcessEx2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
caps.latest.revision: 21
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 3d23b1b97145b5e0b24ebfe814aeca5168ef6a06
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
此接口允许调试管理器 (SDM) 通知它是附加到或与进程分离的进程，会话。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 自定义端口供应商提供对同一个对象作为实现此接口[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)接口以便为：  
  
-   支持跟踪的会话连接到进程  
  
-   支持自动附加跨多个调试引擎  
  
 自定义端口供应商可以实现此接口，如果它选择。  
  
## <a name="notes-for-callers"></a>调用方的说明  
  
-   SDM 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugProcess2`接口，以获得此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProcessEx2`。  
  
|方法|描述|  
|------------|-----------------|  
|[附加](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|通知会话现在正在调试的进程的进程。|  
|[分离](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|通知会话不再调试进程的进程。|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|添加程序节点有关的调试引擎的列表。|  
  
## <a name="remarks"></a>备注  
 此接口是私有 SDM 和进程之间。  
  
## <a name="requirements"></a>惠?  
 标头： Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)