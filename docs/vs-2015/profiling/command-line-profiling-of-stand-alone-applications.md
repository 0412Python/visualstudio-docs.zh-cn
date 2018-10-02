---
title: 从命令行分析独立应用程序 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3b261ab2da3ee405db46d8c18e3d41771f1ae5e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472179"
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>从命令行分析独立应用程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[独立应用程序的命令行分析](https://docs.microsoft.com/visualstudio/profiling/command-line-profiling-of-stand-alone-applications)。  
  
本部分介绍从命令行使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具收集独立（客户端）应用程序的性能数据的步骤和选项。  
  
## <a name="common-tasks"></a>常规任务  
  
|任务|相关的内容|  
|----------|---------------------|  
|**收集应用程序统计信息：** 使用采样法收集性能统计信息。 对于分析 CPU 使用率问题以及了解应用程序的常规性能特征，采样数据十分有用。|-   [使用采样法收集应用程序统计信息](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**收集详细计时数据：** 使用检测方法收集详细计时信息。 检测数据可用于分析 I/O 问题和精细分析应用程序方案。|-   [使用检测收集详细计时数据](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**收集 .NET 内存数据：** 使用采样法或检测法收集显示分配对象的大小和数量的 .NET 内存分配数据。 还可以收集对象生存期数据，此数据显示在每次垃圾回收生成中回收的对象的大小和数量。|-   [收集 .NET Framework 内存数据](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**收集并发数据：** 使用并发方法收集资源争用数据和线程活动数据，后者可显示 CPU 使用率、线程争用、线程迁移、同步延迟、重叠 I/O 的区域和其他系统事件。|-   [收集并发数据](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**添加层交互数据：** 可以添加有关应用程序对 Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 数据库进行的同步 ADO.NET 调用的性能数据。 若要将层交互数据添加到分析运行，需要使用命令行分析工具执行特定的步骤。|-   [收集层交互数据](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**尝试一下：** 使用分布过程以通过采样或检测方法分析示例客户端应用程序。|-   [演练：使用采样进行命令行分析](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [演练：使用检测进行命令行分析](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>相关任务  
  
|任务|相关内容|  
|----------|---------------------|  
|**分析 ASP.NET 应用程序**|-   [分析 ASP.NET Web 应用程序](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**分析服务**|-   [分析服务](../profiling/command-line-profiling-of-services.md)|


