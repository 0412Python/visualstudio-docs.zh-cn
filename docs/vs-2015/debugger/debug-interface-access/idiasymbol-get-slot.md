---
title: IDiaSymbol::get_slot | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_slot method
ms.assetid: 97e405b8-483f-4da0-91e7-ca4d88251ecd
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a0699c6e7cb5070095b35ba33f1695f0af747197
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58936622"
---
# <a name="idiasymbolgetslot"></a>IDiaSymbol::get_slot
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索位置的槽数。 何时使用[LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)是`LocIsSlot`。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_slot (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回位置的槽数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)
