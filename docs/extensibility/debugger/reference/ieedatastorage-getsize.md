---
title: IEEDataStorage::GetSize |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEEDataStorage::GetSize
helpviewer_keywords:
- IEEDataStorage::GetSize
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ee3e04c16b59ae97b93a3c521aa1a63f57835eb4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ieedatastoragegetsize"></a>IEEDataStorage::GetSize
返回此对象中包含的字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSize(  
   ULONG* size  
);  
```  
  
```csharp  
int GetSize(  
   out uint size  
);  
```  
  
#### <a name="parameters"></a>参数  
 `size`  
 [out]此对象中包含的字节数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 使用[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)方法来检索实际的数据字节的长度。  
  
## <a name="see-also"></a>请参阅  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)