---
title: SccGetExtendedCapabilities 函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 46ae3e051028e8239be5949500ebb710d67eee17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137211"
---
# <a name="sccgetextendedcapabilities-function"></a>SccGetExtendedCapabilities 函数
此函数可返回受源代码管理插件的其他功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccGetExtendedCapabilities(  
   LPVOID pContext,  
   LONG lSccExCaps,  
   LPBOOL pbSupported  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件的上下文指针。  
  
 lSccExCaps  
 [in]一个标志，指定要测试的扩展的功能 (请参阅中的扩展功能代码表[功能标志](../extensibility/capability-flags.md)可能标志)。  
  
 pbSupported  
 [out]返回非零 (`TRUE`) 如果支持指定的功能进行; 否则，返回零 (`FALSE`)。  
  
## <a name="return-value"></a>返回值  
 此函数的源代码控制插件实现应返回以下值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|Get 功能操作成功完成。|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|出现未知或未指定错误。|  
  
## <a name="remarks"></a>备注  
 按需; 调用此方法也就是说，如果一项功能需要先进行测试，调用此方法以确定是否支持功能。 指定一次只有一个标志。  
  
## <a name="see-also"></a>另请参阅  
 [源控件插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [错误代码](../extensibility/error-codes.md)   
 [功能标志](../extensibility/capability-flags.md)