---
title: VSG_DEFAULT_RUN_FILENAME |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 303bce554ff6345a37719a8d2f529f3c1ffe02e2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="vsgdefaultrunfilename"></a>VSG_DEFAULT_RUN_FILENAME
定义图形日志文件的默认文件名。  
  
## <a name="syntax"></a>语法  
  
```C++  
#define VSG_DEFAULT_FILENAME filename  
```  
  
#### <a name="parameters"></a>参数  
 `filename`  
 以编程方式捕获图形信息时默认为图形日志文件指定的文件名。  
  
## <a name="value"></a>值  
 表示图形日志文件的文件名的字符串。 默认情况下为 L"default.vsglog"。  
  
```C++  
#define VSG_DEFAULT_FILENAME L"default.vsglog"  
```  
  
## <a name="remarks"></a>备注  
 如果定义预处理器符号 `DONT_SAVE_VSGLOG_TO_TEMP`，则文件名与捕获的应用的当前目录相关，或为绝对路径；否则，它与用户的临时文件目录相关，且不能是绝对路径。  
  
 若要更改定义的文件名称，您必须先重新定义它你包括`vsgcapture.h`程序中。  
  
## <a name="example"></a>示例  
 此示例说明如何更改捕获文件的默认文件名：  
  
```C++  
// Redefine the default capture filename before including vsgcapture.h  
#define VSG_DEFAULT_FILENAME L"capture.vsglog"  
  
#include <vsgcapture.h>  
```  
  
## <a name="see-also"></a>请参阅  
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)