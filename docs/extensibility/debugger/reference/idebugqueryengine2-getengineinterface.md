---
title: "IDebugQueryEngine2::GetEngineInterface |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 65f40bf3e0e110a6d945921d06443f0c8a608d20
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
获取自定义调试引擎 (DE) 接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetEngineInterface(   
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetEngineInterface(   
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppUnk`  
 [out]返回`IUnknown`对象，表示的调试引擎 (DE)，以及其中可以查询 DE 与关联的任何其他有效的接口 (例如[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)或[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md))。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 应慎用生成接口，因为通过此方法从检索到的接口的调用绕过会话调试管理器的处理，并可能导致 SDM 使进入错误状态，或在调试时生成错误。  
  
## <a name="see-also"></a>请参阅  
 [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)