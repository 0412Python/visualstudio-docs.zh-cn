---
title: IDebugArrayObject |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject
helpviewer_keywords:
- IDebugArrayObject method
ms.assetid: a1c8e77e-dee1-4748-a516-6ab032a8f54f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8cac7730296d2a4f95563c3d6ff4c60fdd294dc6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugarrayobject"></a>IDebugArrayObject
> [!IMPORTANT]
>  在 Visual Studio 2015 中，已弃用这种方式实施表达式计算器。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)和[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 此接口表示一个数组对象。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugArrayObject : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 表达式计算器实现此接口来表示数组。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)接口可以通过使用来获取此接口[QueryInterface](/cpp/atl/queryinterface)如果表示的对象的数组。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 除了上的方法`IDebugObject`接口，将以下方法实现上`IDebugArrayObject`接口。  
  
|方法|描述|  
|------------|-----------------|  
|[GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)|获取数组中元素的计数。|  
|[GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)|获取数组的元素。|  
|[GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)|获取数组的所有元素。|  
|[GetRank](../../../extensibility/debugger/reference/idebugarrayobject-getrank.md)|获取数组的秩。|  
|[GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md)|获取数组的维数。|  
  
## <a name="remarks"></a>备注  
 表达式计算器使用此接口来表示分析树中的数组。  
  
## <a name="requirements"></a>要求  
 标头： ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)