---
title: IDebugCustomAttributeQuery |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fa9c87065130e0b539e49c314648fa5b3944089b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934049"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

表示对方法或类型的自定义属性的查询。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|检索在给定其名称的自定义属性。|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|确定指定中定义自定义属性。|  
  
## <a name="requirements"></a>要求  
 标头：Sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll
