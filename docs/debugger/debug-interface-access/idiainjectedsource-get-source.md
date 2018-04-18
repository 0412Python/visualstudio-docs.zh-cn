---
title: 'Idiainjectedsource:: Get_source |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_source method
ms.assetid: 3c0b5386-321f-4f8f-85cc-e2ee7b4cc3d2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a9d3019d7a2a36f032f4c1e68fa1e60adbe2fede
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiainjectedsourcegetsource"></a>IDiaInjectedSource::get_source
检索源代码字节。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_source (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbData`  
 [in]表示数据缓冲区的大小的字节数。  
  
 `pcbData`  
 [out]返回表示字节的字节数返回。 如果`data`是`NULL`，然后`pcbData`是可用的数据的字节总数。  
  
 `data[]`  
 [out]若要使用的源字节填充缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果不支持此属性。 否则，返回错误代码。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)