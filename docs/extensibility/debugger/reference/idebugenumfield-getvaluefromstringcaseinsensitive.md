---
title: IDebugEnumField::GetValueFromStringCaseInsensitive |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive
helpviewer_keywords:
- IDebugEnumField::GetValueFromStringCaseInsensitive method
ms.assetid: ef95b38e-d9b2-4fb5-a166-7c2e14641dc7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 05d838bc91949ea5023fe61c6eb0c1b5c5220e68
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116524"
---
# <a name="idebugenumfieldgetvaluefromstringcaseinsensitive"></a>IDebugEnumField::GetValueFromStringCaseInsensitive
此方法使用不区分大小写的搜索返回的枚举常数的名称与关联的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetValueFromStringCaseInsensitive(  
   LPCOLESTR  pszValue,  
   ULONGLONG* pvalue  
);  
```  
  
```csharp  
int GetValueFromStringCaseInsensitive(  
   string    pszValue,   
   out ulong pValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszValue`  
 [in]指定要为其获取值的名称的字符串。 请注意，对于 c + +，这是宽字符字符串。  
  
 `pValue`  
 [out]返回关联的数字值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`，如果名称不是枚举，则返回错误代码的一部分。  
  
## <a name="remarks"></a>备注  
 此方法是不区分大小写。 如果需要区分大小写的搜索时 （例如，在其中名称区分大小写的 c + + 等语言），使用[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)