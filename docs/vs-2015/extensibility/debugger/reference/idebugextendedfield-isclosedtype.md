---
title: IDebugExtendedField::IsClosedType |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a566f5dc7d498a9b07d132abe35b279cbc83155d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470993"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugExtendedField::IsClosedType](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugextendedfield-isclosedtype)。  
  
确定是否该字段表示封闭的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>返回值  
 如果此字段为关闭的类型，则返回`S_OK`; 否则为返回`S_FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)
