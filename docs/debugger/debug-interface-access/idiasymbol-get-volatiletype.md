---
title: IDiaSymbol::get_volatileType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_volatileType method
ms.assetid: 19782a4d-40a8-467b-ab7d-58bc4d812309
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c6ccafc8a0d30558f61bc869d8cfc8280c04723e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616308"
---
# <a name="idiasymbolgetvolatiletype"></a>IDiaSymbol::get_volatileType
检索指定用户定义数据类型 (UDT) 是易失性的标志。

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
>  返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
 在 c + +，UDT 可标记为`volatile`关键字，指示其内容不能假定存在一个访问从到下一步。

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)