---
title: IDebugEngineLaunch2::CanTerminateProcess | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngineLaunch2::CanTerminateProcess
helpviewer_keywords:
- IDebugEngineLaunch2::CanTerminateProcess
ms.assetid: 7973454d-c957-4123-a0ee-80ebcdbbd2d1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6b4468af7b2b0cfd08e551839a9ab9c606c25df2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678081"
---
# <a name="idebugenginelaunch2canterminateprocess"></a>IDebugEngineLaunch2::CanTerminateProcess
确定是否可以终止进程。

## <a name="syntax"></a>语法

```cpp
HRESULT CanTerminateProcess ( 
   IDebugProcess2* pProcess
);
```

```csharp
int CanTerminateProcess ( 
   IDebugProcess2 pProcess
);
```

#### <a name="parameters"></a>参数
 `pProcess`

 [in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)对象，表示将终止进程。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则返回错误代码。 返回`S_FALSE`如果引擎无法终止进程，例如，由于访问被拒绝。

## <a name="remarks"></a>备注
 如果此方法返回`S_OK`，然后对其进行[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)可以调用方法来实际终止进程。

## <a name="see-also"></a>请参阅
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)