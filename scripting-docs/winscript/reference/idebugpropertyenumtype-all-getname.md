---
title: IDebugPropertyEnumType_All::GetName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugPropertyEnumType_All.GetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugPropertyEnumType_All::GetName
ms.assetid: 24bbe4d5-4263-48d0-8e8d-bff957ffcad2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1c4f416e7cf525d28ad544c361168f55b964f353
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58146638"
---
# <a name="idebugpropertyenumtypeallgetname"></a>IDebugPropertyEnumType_All::GetName
返回包含名称的 BSTR `EnumType`。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetName(  
   BSTR*  pname  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pname`  
 [out]包含名称的 BSTR `EnumType`。  
  
## <a name="return-value"></a>返回值  
 返回一个有效`HRESULT`，通常`S_OK`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPropertyEnumType_All 接口](../../winscript/reference/idebugpropertyenumtype-all-interface.md)