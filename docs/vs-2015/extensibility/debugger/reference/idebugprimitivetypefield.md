---
title: IDebugPrimitiveTypeField | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugPrimitiveTypeField interface
ms.assetid: 73a428fd-797e-4ceb-8392-ba16f1c5226b
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ad9ff38ae4533f7999b9966c1de32ac77105fcc0
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934008"
---
# <a name="idebugprimitivetypefield"></a>IDebugPrimitiveTypeField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

表示基元类型枚举值从[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPrimitiveTypeField : IDebugField  
```  
  
## <a name="methods"></a>方法  
 除了上的方法[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口，此接口实现了以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetPrimitiveType](../../../extensibility/debugger/reference/idebugprimitivetypefield-getprimitivetype.md)|检索与此字段关联的基元类型。|  
  
## <a name="requirements"></a>要求  
 标头：Sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll
