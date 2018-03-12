---
title: "Idiasession:: Findchildren |Microsoft 文档"
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
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0cae2dd492fd11ff4a5d707ba95c571711358358
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
检索指定的父标识符的所有匹配的名称和符号类型的子级。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `parent`  
 [in][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)表示父对象。 如果此父符号是函数、 模块或块，则在返回其子词法`ppResult`。 如果父符号是一种类型，则返回其子类。 如果此参数为`NULL`，然后`symtag`必须设置为`SymTagExe`或`SymTagNull`，这将返回全局作用域 （.exe 文件）。  
  
 `symtag`  
 [in]指定要检索的子级的符号标记。 值，将从[SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)枚举。 设置为`SymTagNull`检索所有子级。  
  
 `name`  
 [in]指定要检索的子级的名称。 设置为`NULL`为要检索的所有子级。  
  
 `compareFlags`  
 [in]指定应用于名称匹配的比较选项。 中的值[NameSearchOptions 枚举](../../debugger/debug-interface-access/namesearchoptions.md)枚举可以单独或组合使用。  
  
 `ppResult`  
 [out]返回[IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)检索包含子符号列表中的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
 下面的示例演示如何查找函数的局部变量`pFunc`该匹配项名称`szVarName`。  
  
```C++  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>请参阅  
 [概述](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 枚举](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)