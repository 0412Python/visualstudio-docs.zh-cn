---
title: IDebugDefaultPort2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2
helpviewer_keywords:
- IDebugDefaultPort2 interface
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c6d131ab24cc57af1846f89b61afa2d89ae2cacb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdefaultport2"></a>IDebugDefaultPort2
此接口提供几种方法访问端口的服务器和通知功能。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDefaultPort2 : IDebugPort2  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 Visual Studio 实现此接口来表示用于访问程序的调试端口。 如果它处理远程调试，自定义端口供应商还可以实现此接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 上的方法的自变量[IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)接口提供此接口。 调用[QueryInterface](/cpp/atl/queryinterface)上[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口还可以获取此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 除了中定义的方法[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|获取此端口从端口通知接口。|  
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|获取承载此端口的服务器接口。|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|确定此端口是否正在运行在本地计算机上。|  
  
## <a name="remarks"></a>备注  
 名称"`IDebugDefaultPort2`"就会执行不当，因为它不表示默认端口。 它无法调用"IDebugPort3。"  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)