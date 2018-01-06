---
title: "错误： 网站辅助进程已被 IIS 终止 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.web_server_process_terminated
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fb7a0220cf6650aeeb12ec6549d112a39918de3f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="error-web-site-worker-process-has-been-terminated-by-iis"></a>错误：网站辅助进程已被 IIS 终止
调试器已停止对网站执行代码。 这导致 Internet Information Services (IIS) 认为辅助进程已停止响应。 因此，IIS 终止了辅助进程。  
  
 若要继续调试，必须配置 IIS 以使辅助进程继续运行。 在低于 IIS 7 的 IIS 版本中，不会显示此错误消息。  
  
### <a name="to-configure-iis-7-to-allow-the-worker-process-to-continue"></a>配置 IIS 7 以使辅助进程继续运行  
  
1.  打开**管理工具**窗口。  
  
    1.  单击**启动**，然后选择**控制面板**。  
  
    2.  在**控制面板**，选择**切换到经典视图**，如有必要，然后双击**管理工具**。  
  
2.  在**管理工具**窗口中，双击**Internet Information Services (IIS) Manager**。  
  
     IIS 管理器随即打开。  
  
3.  在**连接**窗格中，展开\<计算机名称 > 节点，如有必要。  
  
4.  下\<计算机名称 > 节点，单击**应用程序池**。  
  
5.  在**应用程序池**列表，右键单击你的应用程序运行在中，池的名称，然后单击**高级设置**。  
  
6.  在**高级设置**对话框中，找到**进程模型**部分，然后执行以下操作之一：  
  
    -   设置**启用 Ping**到**False**。  
  
    -   设置**Ping 最大响应时间**为大于 90 秒的值。  
  
     设置**启用 Ping**到**False** IIS 停止检查辅助进程是否仍在运行，并使工作进程保持活动状态，直到您停止被调试的进程。 设置**Ping 最大响应时间**为较大值可使 IIS 继续监视辅助进程。  
  
7.  单击**确定**关闭**高级设置**对话框。  
  
8.  关闭 IIS 管理器和**管理工具**窗口。  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和疑难解答](../debugger/remote-debugging-errors-and-troubleshooting.md)