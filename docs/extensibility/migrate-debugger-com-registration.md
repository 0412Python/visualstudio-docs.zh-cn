---
title: "迁移 64 位调试器 COM 类注册 |Microsoft 文档"
ms.custom: 
ms.date: 11/10/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
caps.latest.revision: "1"
author: gregg-miskelly
ms.author: greggm
manager: ghogen
ms.workload: greggm
ms.openlocfilehash: 737c970555fce8f3cdac118421eddb09f52d7c53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>迁移 64 位调试器 COM 类注册

调试器在注册表中的 COM 类注册 （通过使用 regasm，regsvr32，或直接向注册表写入） 并加载到 msvsmon.exe （远程调试器） 的扩展，它现在是可以无需提供此注册到 msvsmon要写入到注册表。 这会影响旧.NET 调试器表达式计算器或配置为在 msvsmon.exe 进程中加载的调试引擎。

## <a name="msvsmon-comclass-def"></a>msvsmon comclass def

若要使用此方法，请添加 msvsmon (InstallDir:\Common7\IDE\Remote Debugger\x64) 旁边的 *.msvsmon comclass def.json 文件。

下面是一个管理，注册一个示例 msvsmon comclass def 文件和一个本机类：

文件名： MyCompany.MyExample.msvsmon comclass def.json

```json
{
  "managedCOMClasses": [
    {
      "clsid": "{C9F48B25-36ED-4B22-8210-98BC5BE4D1E7}",
      "assemblyName": "MyCompany.MyAssembly",
      "className": "MyCompany.MyNamespace.MyClass"
    }
  ],
  "nativeCOMClasses": [
    {
      "clsid": "{42A476E9-8FA7-44D5-ADFE-216AD371EEC9}",
      "dllPath": "MyExample.dll"
    }
  ]
}
```
