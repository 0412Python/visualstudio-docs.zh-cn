---
title: IDebugEngine2::CreatePendingBreakpoint |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngine2::CreatePendingBreakpoint
helpviewer_keywords:
- IDebugEngine2::CreatePendingBreakpoint
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 28123ed555cc54d8ca307cca020fe7b101f73087
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51777222"
---
# <a name="idebugengine2creatependingbreakpoint"></a>IDebugEngine2::CreatePendingBreakpoint
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

在调试引擎 (DE) 中创建挂起断点。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT CreatePendingBreakpoint(   
   IDebugBreakpointRequest2*  pBPRequest,  
   IDebugPendingBreakpoint2** ppPendingBP  
);  
```  
  
```csharp  
int CreatePendingBreakpoint(   
   IDebugBreakpointRequest2     pBPRequest,  
   out IDebugPendingBreakpoint2 ppPendingBP  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pBPRequest`  
 [in][IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)描述挂起断点，以创建对象。  
  
 `ppPendingBP`  
 [out]返回[IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)表示挂起断点的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 通常会返回`E_FAIL`如果`pBPRequest`参数不匹配支持的 if DE 的任何语言`pBPRequest`参数是无效或不完整。  
  
## <a name="remarks"></a>备注  
 挂起断点是实质上是将断点绑定到代码所需的所有信息的集合。 此方法返回挂起断点未绑定到之前的代码[绑定](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)调用方法。  
  
 每个挂起断点的用户集，会话调试管理器 (SDM) 调用此方法在每个附加 DE。 负责 DE 以验证该断点适用于该 DE 中运行的程序。  
  
 当用户的代码行上设置断点时，DE 可以自由地将断点绑定到对应于此代码在文档中的最近的一行。 这使得用户可以在多行语句的第一行上设置断点，但将其绑定上的最后一行 （其中的所有代码具有的都特性中的调试信息）。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于简单`CProgram`对象。 DE 实现`IDebugEngine2::CreatePendingBreakpoint`可能然后转发到每个程序中方法的此实现的所有调用。  
  
```  
HRESULT CProgram::CreatePendingBreakpoint(IDebugBreakpointRequest2* pBPRequest, IDebugPendingBreakpoint2** ppPendingBP)     
{    
  
   // Create and initialize the CPendingBreakpoint object.  
   CComObject<CPendingBreakpoint> *pPending;    
   CComObject<CPendingBreakpoint>::CreateInstance(&pPending);    
   pPending->Initialize(pBPRequest, m_pInterp, m_pCallback, m_pEngine);    
   return pPending->QueryInterface(ppPendingBP);    
}    
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [将绑定](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)

