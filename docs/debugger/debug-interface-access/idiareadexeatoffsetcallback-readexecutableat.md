---
title: "Idiareadexeatoffsetcallback:: Readexecutableat |Microsoft 文档"
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
- IDiaReadExeAtOffsetCallback::ReadExecutableAt method
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1250bef977c887be9d4d98fb4372a597c4e22072
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiareadexeatoffsetcallbackreadexecutableat"></a>IDiaReadExeAtOffsetCallback::ReadExecutableAt
读取指定的可执行文件从指定的偏移量处开始的字节数。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT ReadExecutableAt (   
   DWORDLONG fileOffset,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 fileOffset  
 [in]中开始读取的可执行文件的偏移量。  
  
 cbData  
 [in]要读取的字节数。  
  
 pcbData  
 [out]返回读取的字节数。  
  
 数据]  
 [在中，out]使用从文件中读取字节填充数组。  
  
## <a name="remarks"></a>备注  
 若要从使用绝对文件偏移量的可执行文件加载数据字节的 DIA 支持代码通过调用此方法。 此方法称为 support 的[idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)