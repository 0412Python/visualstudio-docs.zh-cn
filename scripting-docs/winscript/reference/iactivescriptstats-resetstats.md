---
title: IActiveScriptStats::ResetStats |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStats.ResetStats
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::ResetStats
ms.assetid: d98276fc-ad47-4e7b-aae4-254d63aece77
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b56ca147c4484b00bfac5d1876ac58361901a7e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24724857"
---
# <a name="iactivescriptstatsresetstats"></a>IActiveScriptStats::ResetStats
重置此脚本的统计信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ResetStats();  
```  
  
#### <a name="parameters"></a>参数  
 此方法采用任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法将重置此脚本的统计信息。  
  
## <a name="see-also"></a>另请参阅  
 [IActiveScriptStats 接口](../../winscript/reference/iactivescriptstats-interface.md)