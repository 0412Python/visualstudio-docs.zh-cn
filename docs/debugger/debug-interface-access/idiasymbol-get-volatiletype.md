---
title: "Idiasymbol:: Get_volatiletype |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_volatileType method
ms.assetid: 19782a4d-40a8-467b-ab7d-58bc4d812309
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5fbcdd8e78867eec2184f0df72e7a90f033e6f30
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetvolatiletype"></a>IDiaSymbol::get_volatileType
检索用于指定用户定义数据类型 (UDT) 是易失性的标志。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_volatileType (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果用户定义的类型是易失性; 否则为返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值`S_FALSE`意味着属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 在 c + +，UDT 可以标记与`volatile`关键字，指示其内容不能假定存在一个访问从到下一步。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)