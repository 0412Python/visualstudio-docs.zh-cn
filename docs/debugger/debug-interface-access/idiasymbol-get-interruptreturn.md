---
title: 'Idiasymbol:: Get_interruptreturn |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_interruptReturn method
ms.assetid: 9665da6c-4cc0-41d7-b2e2-0d9e50174cf8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4256da41a93b32902bccfdf3b9a13ce5d754cbbf
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646546"
---
# <a name="idiasymbolgetinterruptreturn"></a>IDiaSymbol::get_interruptReturn
检索一个标志，指定该函数是否包含从中断指令返回 (例如，X86 程序集代码`iret`)。

## <a name="syntax"></a>语法

```C++
HRESULT get_interruptReturn(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>参数
 `pFlag`

[out]返回`TRUE`如果函数具有的返回从中断指令; 否则，返回`FALSE`。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="requirements"></a>要求

|需求|说明|
|-----------------|-----------------|
|标头：|dia2.h|
|版本：|DIA SDK v8.0|

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)