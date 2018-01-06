---
title: "IDebugProcess2::GetAttachedSessionName |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::GetAttachedSessionName
helpviewer_keywords: IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8ca045a1fee17891fbe053d1d072a4affa41c787
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
获取的会话中调试此过程的名称。 一个 IDE 可以调试在特定计算机上的特定进程的用户显示此信息。  
  
> [!NOTE]
>  此方法已被弃用，并且应始终返回其实现`E_NOTIMPL`。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrSessionName`  
  
## <a name="return-value"></a>返回值  
 此方法应始终返回`E_NOTIMPL`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)