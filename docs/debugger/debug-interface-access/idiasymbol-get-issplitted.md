---
title: 'Idiasymbol:: Get_issplitted |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isSplitted method
ms.assetid: ff160cf6-003b-4ef5-a406-20a7b287b2bf
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a3cf8eb994a33ab3bbcce6bce38bf02677197780
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644641"
---
# <a name="idiasymbolgetissplitted"></a>IDiaSymbol::get_isSplitted
检索一个标志，指定是否已被数据符号拆分为聚合或其他符号; 集合编译器将符号视为单独的实体，即使它们实际上是更大的符号的一部分。

## <a name="syntax"></a>语法

```C++
HRESULT get_isSplitted(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>参数
 `pFlag`

[out]返回`TRUE`如果该符号已被拆分为聚合的符号; 否则，返回`FALSE`。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
 [Idiasymbol:: Get_isaggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)方法将返回`TRUE`属于拆分符号的所有符号。

## <a name="requirements"></a>要求

|需求|说明|
|-----------------|-----------------|
|标头：|dia2.h|
|版本：|DIA SDK v8.0|

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_isAggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)