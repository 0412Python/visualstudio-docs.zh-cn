---
title: SetNotificationForWaitCompletion 方法 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
caps.latest.revision: 5
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f5e35933e59fb4d8ff9f13db4bef8c23891bac2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion 方法
设置或清除 TASK_STATE_WAIT_COMPLETION_NOTIFICATION 状态位。  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
## <a name="syntax"></a>语法  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>参数  
 `enabled`  
  
 `true`若要设置的位;`false`到取消设置位。  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 调试器将设置此位，以帮助单步从异步方法正文。 如果`enabled`是`true`，必须调用此方法仅在尚未完成的任务上。 如果`enabled`是`false`，不能对已完成的任务调用此方法。 在既情况下，它应仅用于承诺样式任务。  
  
## <a name="requirements"></a>惠?  
  
## <a name="see-also"></a>请参阅  
 [任务类](../../extensibility/debugger/task-class-internal-members.md)