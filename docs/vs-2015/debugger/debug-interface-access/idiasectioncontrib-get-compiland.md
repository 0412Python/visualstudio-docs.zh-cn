---
title: 'Idiasectioncontrib:: Get_compiland |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_compiland method
ms.assetid: c0496f6f-f8f2-435f-8674-6c32db6c5934
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7ed5b181a9e0346cab5225d5f9024f070124186a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934615"
---
# <a name="idiasectioncontribgetcompiland"></a>IDiaSectionContrib::get_compiland
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索提供本部分的编译单位符号的引用。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_compiland (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象，表示提供本部分将编译单位。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
