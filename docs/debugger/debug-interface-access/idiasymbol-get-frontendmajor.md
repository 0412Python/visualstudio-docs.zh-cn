---
title: 'Idiasymbol:: Get_frontendmajor |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_frontEndMajor method
ms.assetid: f8a067c5-3306-4fc5-bc20-8910a47ed504
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3bf14958e9e4c95ce5613c92244b757326c9c03e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31468315"
---
# <a name="idiasymbolgetfrontendmajor"></a>IDiaSymbol::get_frontEndMajor
检索前端主版本号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_frontEndMajor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回前端主版本号。 请参阅“备注”。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值`S_FALSE`意味着属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 编译器通常组成两个主要元素： 前端 （分析器），用于处理为中间形式分析的源代码，并将中间形式转换为程序集的后端 （代码生成器）。 它是很常见的前端，具有后端的版本不同。  
  
 前端或后端版本号由三个部分组成：\<主要 >。\<次要 >。\<生成 >，其中\<主要 > 是的主要版本号，\<次要 > 是的次要版本号，和\<生成 > 是的生成号。 例如，13.10.3077。  
  
## <a name="requirements"></a>要求  
  
|需求|描述|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v7.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)