---
title: IDiaStackWalkHelper::pdataForVA |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42b38aa37260f7ffe7cf0a64ea5199de5253a97f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
返回与虚拟地址相关联的 PDATA 数据块。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>参数  
 `va`  
 [in]指定要获取的数据的虚拟地址。  
  
 `cbData`  
 [in]以字节为单位来获取数据的大小。  
  
 `pcbData`  
 [out]返回以字节为单位获得数据的实际大小。  
  
 `pbData`  
 [在中，out]使用请求的数据填充缓冲区。 不能为 `NULL`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有指定的地址不 PDATA。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 PDATA （名为".pdata"部分） 的编译单位包含有关异常处理函数的信息。  
  
 调用方知道了以便调用方具有无需要求提供了有关数据量的要返回的数据量。 因此，它是可接受的返回错误，如果此方法的实现`pbData`参数是`NULL`。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)