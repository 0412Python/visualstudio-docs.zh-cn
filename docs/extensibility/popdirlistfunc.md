---
title: POPDIRLISTFUNC |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 44a11e6edc9666fcd7614d467a2c9ffaa86b4365
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
这是提供给一个回调函数[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)函数以更新目录和 （可选） 若要了解它们在源代码管理下的文件名称的集合。  
  
 `POPDIRLISTFUNC`回调应调用仅对这些目录和文件名称 (在列表中提供给`SccPopulateDirList`函数)，其实是在源代码管理下。  
  
## <a name="signature"></a>签名  
  
```cpp  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>参数  
 pvCallerData  
 [in]用户值提供给[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)。  
  
 bFolder  
 [in]`TRUE`如果中的名称`lpDirectoryOrFileName`是一个目录中; 否则名称是一个文件名。  
  
 lpDirectoryOrFileName  
 [in]到源代码管理下的目录或文件名称的完整的本地路径。  
  
## <a name="return-value"></a>返回值  
 IDE 返回相应的错误代码：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|继续进行处理。|  
|SCC_I_OPERATIONCANCELED|停止处理。|  
|SCC_E_xxx|任何合适的源控制错误应停止处理。|  
  
## <a name="remarks"></a>备注  
 如果`fOptions`参数`SccPopulateDirList`函数包含`SCC_PDL_INCLUDEFILES`标志，则列表将可能包含文件的名称，以及目录名称。  
  
## <a name="see-also"></a>另请参阅  
 [由 IDE 实现的回调函数](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [错误代码](../extensibility/error-codes.md)