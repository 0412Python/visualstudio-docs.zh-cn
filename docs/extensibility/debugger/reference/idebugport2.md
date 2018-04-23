---
title: IDebugPort2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPort2
helpviewer_keywords:
- IDebugPort2 interface
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d1811ad7e46865d00eed2066d061daec78d7ab2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugport2"></a>IDebugPort2
此接口表示计算机上的调试端口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 自定义端口供应商提供实现此接口来表示计算机上的调试端口。  
  
 如果端口支持发送端口事件，它还必须实现<xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer>接口以支持<xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint>反过来提供接口[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)或[添加](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)返回此接口，表示请求的端口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugPort2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|返回的端口名称。|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|返回端口标识符。|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|返回用于创建一个端口 （如果可用） 的请求。|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|返回为此端口端口供应商。|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|返回一个指向接口给定进程的标识符的过程。|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|枚举所有的端口上运行的进程。|  
  
## <a name="remarks"></a>备注  
 本地端口提供访问所有进程和在本地计算机上运行的程序。 其他端口可能表示的串行电缆连接到基于 Windows CE 的设备时或与非 DCOM 计算机的网络连接。 `IDebugPort2`接口用于查找的名称和端口、 标识符枚举的端口上运行的所有进程并为启动和终止进程的端口上提供功能。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)