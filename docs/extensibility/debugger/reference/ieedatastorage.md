---
title: IEEDataStorage |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEEDataStorage
helpviewer_keywords:
- IEEDataStorage interface
ms.assetid: 704e932d-2325-410e-89c4-ce88c6ec19da
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aeb98c4c4d3b544616412b3cf5cf8a162fddbd6b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ieedatastorage"></a>IEEDataStorage
此接口表示一个字节数组。  
  
## <a name="syntax"></a>语法  
  
```  
IEEDataStorage : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 表达式计算器 (EE) 实现此接口可表示的字节数组 (由类型可视化工具，用于检索和更改数据通过[IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)接口)。 EE 通常实现此接口以支持外部类型可视化工具。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 上的方法`IPropertyProxyEESide`接口所有返回此接口。 调用[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)获取[IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)接口。 调用[QueryInterface](/cpp/atl/queryinterface)上[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)接口，以获得[IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 `IEEDataStorage`接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)|检索指定到提供的缓冲区的数据字节数。|  
|[GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)|检索可用的数据字节数。|  
  
## <a name="remarks"></a>备注  
 类型可视化工具使用此接口来访问由特定对象保留的数据。 数据将被视为字节，可让类型可视化工具，以任何方式将需要向用户显示在对其进行操作的数组。  
  
 自定义查看器还可以使用此接口，如果需要，尽管更常见的做法，自定义查看器将使用自定义接口， [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)或[GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md) （适用于面向字符串的数据）。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [类型可视化工具和自定义查看器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)