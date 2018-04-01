---
title: IDebugGenericFieldInstance |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugGenericFieldInstance interface
ms.assetid: f68b4761-be8b-4801-9d4b-cde90e01d95e
caps.latest.revision: 7
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 3d5ee0d66f1248ec3770dd9402baaa1dc8066e96
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericfieldinstance"></a>IDebugGenericFieldInstance
表示托管的代码的泛型类型的字段的实例。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugGenericFieldInstance : IUnknown  
```  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetTypeArguments](../../../extensibility/debugger/reference/idebuggenericfieldinstance-gettypearguments.md)|检索此实例的类型参数自变量。|  
|[TypeArgumentCount](../../../extensibility/debugger/reference/idebuggenericfieldinstance-typeargumentcount.md)|返回此实例的参数自变量类型的数目。|  
  
## <a name="requirements"></a>惠?  
 标头： Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll