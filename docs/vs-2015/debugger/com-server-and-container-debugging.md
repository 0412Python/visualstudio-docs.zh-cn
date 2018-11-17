---
title: 调试 COM 服务器和容器 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.com
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- COM servers, debugging
- ActiveX controls, debugging
- COM [Visual Studio], debugging
ms.assetid: b7ce8696-ebb8-4354-a767-f76b8ada4ac1
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a495b90f68d0a12d9fb34babf28aca073580f2aa
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51787999"
---
# <a name="com-server-and-container-debugging"></a>调试 COM 服务器和容器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

COM 应用程序执行若干不直接受程序员控制的任务。 DLL 间的通信、对象的使用计数和剪贴板操作只是可能遇到意外行为的少数几个情况。 发生这种情况时，第一步是抓住问题的根源。  
  
 Visual Studio 调试器支持单步通过和单步执行容器和服务器。 这包括单步执行远程过程调用 (RPC) 的能力。  
  
##  <a name="BKMK_COMServerandContainerintheSameSolution"></a> 调试 COM 服务器和在同一解决方案中的容器  
 可以使用同一解决方案中的两个项目来调试 COM 服务器和容器。 在每个项目和调试中设置适当的断点。 当容器对服务器进行调用而遇到断点时，容器将一直等到服务器代码返回（即等到完成调试）。  
  
 调试 COM 容器类似于调试标准程序。 一个不同的情况是当调试生成回调的事件时（如在容器应用程序上拖动数据）。 这种情况下，必须在回调函数中设置断点。  
  
##  <a name="BKMK_ServerApplicationWithoutContainerInformation"></a> 调试没有容器信息的服务器应用程序  
 如果不必或不想容器应用程序使用调试信息，那么开始调试服务器应用程序可分三步进行：  
  
1.  像对待普通的应用程序一样开始调试服务器。  
  
2.  按需要设置断点。  
  
3.  启动容器应用程序。  
  
##  <a name="BKMK_DebuggingaServerandDomainIsolationSDIApplication"></a> 调试服务器和域隔离 (SDI) 应用程序  
 如果正在调试 SDI 服务器应用程序，则必须指定`/Embedding`或`/Automation`中**命令行参数**中的属性*项目*C/c + +，C# 中，属性页对话框或Visual Basic 项目。  
  
 使用这些命令行自变量，调试器可以像从容器中启动服务器应用程序一样启动它。 从程序管理器或文件管理器启动容器将导致容器使用在调试器中启动的服务器实例。  
  
 访问*项目*属性页对话框中，右键单击解决方案资源管理器中的项目，然后从快捷菜单中选择属性。 若要找到“命令行自变量”属性，请展开“配置属性”类别并单击“调试”页。  
  
## <a name="see-also"></a>请参阅  
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)



