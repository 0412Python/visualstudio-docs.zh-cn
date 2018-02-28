---
title: "JsSetRuntimeMemoryAllocationCallback 函数 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 755ab36c8edb8c0350eb2b245e060344c8825dee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jssetruntimememoryallocationcallback-function"></a>JsSetRuntimeMemoryAllocationCallback 函数
为指定的运行时设置内存分配回调  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <a name="parameters"></a>参数  
 `runtime`  
 为其注册分配回调的运行时。  
  
 `callbackState`  
 将传回到回调的用户提供状态。  
  
 `allocationCallback`  
 要为内存分配事件调用的内存分配回调。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 注册内存分配回调将导致运行时回调到主机（每当它从操作系统获取内存或释放内存到操作系统时）。 在运行时内存管理器分配内存块之前调用回调例程。 如果回调返回 false，则将拒绝分配。 释放内存块及分配失败之后，运行时内存管理器也会调用回调例程。  
  
 在当前运行时执行线程上调用回调，因此在回调完成前将阻止执行。  
  
 不存储回调的返回值；以前被拒绝的分配不会再阻止运行时稍后为新的内存分配调用回调。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)