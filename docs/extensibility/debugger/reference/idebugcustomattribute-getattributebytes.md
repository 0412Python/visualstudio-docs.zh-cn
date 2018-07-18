---
title: IDebugCustomAttribute::GetAttributeBytes |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute::GetAttributeBytes
helpviewer_keywords:
- IDebugCustomAttribute::GetAttributeBytes
ms.assetid: cf34583b-6530-4dcc-89f8-eb27e4e8d594
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 949bc7b8722e11be0a69800f890b509399169688
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107002"
---
# <a name="idebugcustomattributegetattributebytes"></a>IDebugCustomAttribute::GetAttributeBytes
获取作为字节的 blob 的属性信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAttributeBytes(   
   BYTE*  ppBlob,  
   DWORD* pdwLen  
);  
```  
  
```csharp  
int GetAttributeBytes(  
   ref byte[] ppBlob,   
   ref uint   pdwLen  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppBlob`  
 [在中，out]使用属性字节填充数组。  
  
 `pdwLen`  
 [在中，out]指定的最大返回中的字节数`ppBlob`数组并返回实际写入到该数组的字节数。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 设置`ppBlob`为 null 值，以返回数量的参数属性可用字节数。 分配一个数组，然后将为该数组中的传递`ppBlob`参数。  
  
 属性字节表示的自定义属性的原始数据。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)