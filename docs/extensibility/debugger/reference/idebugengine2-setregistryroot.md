---
title: "IDebugEngine2::SetRegistryRoot |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::SetRegistryRoot
helpviewer_keywords: IDebugEngine2::SetRegistryRoot
ms.assetid: d0d81202-8a4a-4bc3-b297-30a047c5ec60
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3a514dfb0d248ec38d130b70db432352b5c09411
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine2setregistryroot"></a>IDebugEngine2::SetRegistryRoot
设置用于调试引擎 (DE) 的注册表根。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetRegistryRoot(   
   LPCOLESTR pszRegistryRoot  
);  
```  
  
```csharp  
int SetRegistryRoot(   
   string pszRegistryRoot  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszRegistryRoot`  
 [in]要使用的注册表根。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法允许[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]指定备用注册表根目录，DE 应使用来获取注册表设置; 例如，"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp"。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)