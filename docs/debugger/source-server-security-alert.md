---
title: 源服务器安全警报 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbb2233ffcc041a9d756ff51ac9fd3f1b9dc669e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="source-server-security-alert"></a>源服务器安全警报
使用源服务器时，只能使用来自已知和受信任位置的符号文件。  
  
 此警告会在你启用源服务器支持时出现。 源服务器命令嵌套在调试符号文件 (***.pdb**文件)。 请确保你知道自己的 PDB 文件来自何处。  
  
> [!IMPORTANT]
>  使用源服务器时必须考虑以下潜在的安全威胁：因为任何命令都可以嵌入到应用程序的 PDB 文件中，所以请确保只将要执行的命令放到 srcsrv.ini 文件中。 任何尝试执行不在 srcsvr.ini 文件中的命令都将导致出现一个确认对话框。 有关更多信息，请参见 [Security Warning: Debugger Must Execute Untrusted Command](../debugger/security-warning-debugger-must-execute-untrusted-command.md)。 未对命令参数执行任何验证，因此请慎用受信任的命令。 例如，如果你信任 cmd.exe，恶意用户则可能会指定使该命令变得危险的参数。  
  
## <a name="see-also"></a>请参阅  
 [指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [调试器安全](../debugger/debugger-security.md)   
 [源服务器](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)
