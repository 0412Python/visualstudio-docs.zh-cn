---
title: "IRemoteDebugApplication110 接口 |Microsoft 文档"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110 Interface
ms.assetid: 785ab46a-8827-41cb-806a-132e6b2c8f47
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d384cea22b79b2a7ca9af3424d053fb3062d79a3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="iremotedebugapplication110-interface"></a>IRemoteDebugApplication110 接口
用于提供可由脚本调试器和过程的调用方的新功能。  
  
> [!IMPORTANT]
>  此接口由 PDM v11.0 和更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="methods"></a>方法  
 `IRemoteDebugApplication110` 接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IRemoteDebugApplication110::SetDebuggerOptions](../../winscript/reference/iremotedebugapplication110-setdebuggeroptions.md)|调用以更新调试器选项。 为 0 (SDO_NONE) 选项默认值。|  
|[IRemoteDebugApplication110::GetCurrentDebuggerOptions](../../winscript/reference/iremotedebugapplication110-getcurrentdebuggeroptions.md)|返回当前组的已启用的选项。|  
|[IRemoteDebugApplication110::GetMainThread](../../winscript/reference/iremotedebugapplication110-getmainthread.md)|返回主线程调用 SetSite 的主机。|