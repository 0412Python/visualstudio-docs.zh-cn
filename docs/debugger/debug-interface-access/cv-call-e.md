---
title: CV_call_e |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ccdc9df86180883a5a3891563b22625fab4a2ad2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466378"
---
# <a name="cvcalle"></a>CV_call_e
指定的函数的调用约定。  
  
> [!NOTE]
>  此处记录了只有最常见的枚举值。 Cvconst.h 标头文件中提供了完整枚举。  
  
## <a name="syntax"></a>语法  
  
```C++  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## <a name="elements"></a>元素  
 CV_CALL_NEAR_C  
 指定使用 near 右到左推送的函数调用约定。 调用的函数可清除堆栈。  
  
 CV_CALL_NEAR_FAST  
 指定使用寄存器近的从左到右推送的函数调用约定。 调用的函数使用参数字节之的和清除堆栈。  
  
 CV_CALL_NEAR_STD  
 指定使用 near 标准调用 （从右到左推送） 的函数调用约定。  
  
 CV_CALL_NEAR_SYS  
 指定使用 near 系统调用的函数调用约定。  
  
 CV_CALL_THISCALL  
 指定函数调用约定使用`this`调用 (`this`指针寄存器中传递)。  
  
 CV_CALL_CLRCALL  
 指定使用由公共语言运行时 (CLR) （也称为托管代码调用约定） 的函数调用约定。  
  
## <a name="remarks"></a>备注  
 此枚举中的值返回通过调用[idiasymbol:: Get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： cvconst.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)