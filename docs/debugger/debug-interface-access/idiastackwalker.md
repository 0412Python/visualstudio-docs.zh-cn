---
title: IDiaStackWalker |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f0f9c4509e56949d739af3e39e04b89f289edfbe
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="idiastackwalker"></a>IDiaStackWalker
提供方法以执行堆栈遍历的.pdb 文件中使用信息。  
  
## <a name="syntax"></a>语法  
  
```  
IDiaStackWalker: IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDiaStackWalker`。  
  
|方法|描述|  
|------------|-----------------|  
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|检索的堆栈帧枚举器 x86 平台。|  
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|检索特定平台类型的堆栈帧枚举器。|  
  
## <a name="remarks"></a>备注  
 使用此接口来获取已加载模块的堆栈帧的列表。 每个方法传递[IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) （该客户端应用程序实现） 的对象，它提供必要的信息来创建的堆栈帧的列表。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口通过调用获取`CoCreateInstance`方法与类标识符`CLSID_DiaStackWalker`和的接口 ID `IID_IDiaStackWalker`。 该示例演示如何获取此接口。  
  
## <a name="example"></a>示例  
 此示例演示如何获取`IDiaStackWalker`接口。  
  
```C++  
  
      IDiaStackWalker* pStackWalker;  
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaStackWalker,  
                              (void**) &pStackWalker);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>要求  
 标头： Dia2.h  
  
 库： diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>请参阅  
 [接口 （调试接口访问 SDK）](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)