---
title: Help Content Manager 重写 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 35c3d8a13ace801a06e7d1c658c9923e1432ef59
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49190250"
---
# <a name="help-content-manager-overrides"></a>Help Content Manager 重写
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以修改注册表以更改 Visual Studio IDE 中的帮助查看器和帮助相关功能的默认行为。  
  
|任务|注册表项|值和定义|  
|----------|------------------|--------------------------|  
|定义唯一的服务终结点|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSWinExpress\14.0\Help|NewContentAndUpdateService--*HTTPValueForTheServiceEndpoint*。|  
|定义联机/脱机默认值|HKEY_LOCAL_MACHINE\Software\Microsoft\VSWinExpress\14.0\help|UseOnlineHelp -- 输入 `0` 可指定本地帮助，输入 `1` 可指定联机帮助。|  
|定义唯一的 F1 终结点|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSWinExpress\14.0\Help|OnlineBaseUrl--*HTTPValueForTheServiceEndpoint*|  
|替代 BITS 作业优先级|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node（64 位计算机上）\Microsoft\Help\v2.2|BITSPriority -- 使用以下值之一：**foreground**、**high**、**normal** 或 **low**。|  
|禁用联机（和 IDE 联机选项）|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node（64 位计算机上）\Microsoft\VisualStudio\14.0\Help|OnlineHelpPreferenceDisabled -- 设置为 1 可禁用联机帮助内容的访问。|  
|禁用“管理内容”|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node（64 位计算机上）\Microsoft\VisualStudio\14.0\Help|ContentManagementDisabled -- 设置为 1 可禁用帮助查看器中的“管理内容”选项卡。|  
|指向网络共享上的本地内容存储区|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.2\Catalogs\VisualStudio11|LocationPath=”*ContentStoreNetworkShare*”|  
|禁用首次启动 Visual Studio 功能时的内容安装。|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node（64 位计算机上）\Microsoft\VisualStudio\14.0\Help|DisableFirstRunHelpSelection -- 设置为 1 可禁用在 Visual Studio 首次启动时配置的帮助功能。|  
  
## <a name="see-also"></a>请参阅  
 [帮助查看器管理员指南](../ide/help-viewer-administrator-guide.md)



