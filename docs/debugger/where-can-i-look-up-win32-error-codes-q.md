---
title: 可以在哪里查阅 Win32 错误代码？ | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ebd2b4dd65fbcb957e13207cc5550a10b7870219
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56699231"
---
# <a name="where-can-i-look-up-win32-error-codes"></a>可以在哪里查阅 Win32 错误代码？
默认系统安装的 INCLUDE 目录中的 WINERROR.H 包含 Win32 API 函数的错误代码定义。

 可以通过在“监视”窗口或“快速监视”对话框中键入错误代码来查阅该代码。 例如:

`0x80000004,hr`


## <a name="see-also"></a>请参阅
- [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)
- [调试本机代码](../debugger/debugging-native-code.md)