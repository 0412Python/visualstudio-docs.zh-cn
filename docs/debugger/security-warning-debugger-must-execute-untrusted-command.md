---
title: 安全警告： 调试器必须执行不受信任的命令 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.securityalert
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77554795772a5a9e2ce5d9bbe9f620923bc20184
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479924"
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Security Warning: Debugger Must Execute Untrusted Command
使用源服务器时，将出现此警告对话框。 它指示调试器需要执行以获取源代码的命令不在 srcsvr.ini 文件所包含的源服务器的受信任命令列表中。 如果这是一个有效命令，则可将其添加到 srcsvr.ini 文件中。 否则，不应运行该命令。 有关详细信息，请参阅[指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)。  
  
## <a name="message-text"></a>消息正文  
 **调试器必须执行以下不受信任的命令，以从源服务器获取源代码。**  
  
 **如果调试符号文件 (\*.pdb) 是不是来自已知且受信任的来源，此命令可能无效或不安全运行。**  
  
 **是否要运行此命令？**  
  
## <a name="uielement-list"></a>UIElement 列表  
 文本框  
 来自 .pdb 文件的要运行的命令。  
  
 运行  
 允许该命令运行。  
  
 不运行  
 停止执行命令并停止从源服务器下载此文件。  
  
## <a name="see-also"></a>请参阅  
 [指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [调试器安全](../debugger/debugger-security.md)   
 [源服务器](http://msdn.microsoft.com/library/windows/desktop/ms680641\(v=vs.85\).aspx)