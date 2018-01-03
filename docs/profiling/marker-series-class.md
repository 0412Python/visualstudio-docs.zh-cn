---
title: "marker_series 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords: Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9bb2cbe0a87e61a50f3f2b071aef9ef9e12663a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="markerseries-class"></a>marker_series 类
表示由单个提供程序生成的一系列事件通道。  
  
## <a name="syntax"></a>语法  
  
```  
class marker_series;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[marker_series::marker_series 构造函数](../profiling/marker-series-marker-series-constructor.md)|初始化 `marker_series` 类的新实例。|  
|[marker_series::~marker_series 析构函数](../profiling/marker-series-tilde-marker-series-destructor.md)|销毁 marker_series 对象并释放所有已分配的资源。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[marker_series::is_enabled 方法](../profiling/marker-series-is-enabled-method.md)|确定是否有任何会话启用了该提供程序。|  
|[marker_series::write_alert 方法](../profiling/marker-series-write-alert-method.md)|向并发可视化工具跟踪文件写入一个警报。|  
|[marker_series::write_flag 方法](../profiling/marker-series-write-flag-method.md)|向并发可视化工具跟踪文件写入一个标志。|  
|[marker_series::write_message 方法](../profiling/marker-series-write-message-method.md)|向并发可视化工具跟踪文件写入一条消息。|  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `marker_series`  
  
## <a name="requirements"></a>惠?  
 **标头：**cvmarkersobj.h  
  
 **命名空间：**Concurrency::diagnostic  
  
## <a name="see-also"></a>请参阅  
 [diagnostic 命名空间](../profiling/diagnostic-namespace.md)