---
title: MemoryTypeEnum |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 92eaaa63f276d9107dfa3155eb85d52884d3157c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
指定要访问的内存的类型。  
  
## <a name="syntax"></a>语法  
  
```C++  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>参数  
 `MemTypeCode`  
 访问仅代码内存。  
  
 `MemTypeData`  
 访问数据或堆栈内存。  
  
 `MemTypeStack`  
 访问仅堆栈内存。  
  
 `MemTypeAny`  
 访问任何类型的内存。  
  
## <a name="remarks"></a>备注  
 此枚举中的值传递给[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)方法，以限制对不同类型的内存访问。  
  
## <a name="requirements"></a>要求  
 标头： cvconst.h  
  
## <a name="see-also"></a>另请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)