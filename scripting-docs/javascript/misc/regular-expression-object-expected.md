---
title: 缺少正则表达式对象 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: e226096c-c58f-4bcb-a71e-fa32ce474b67
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b27c90a0c2461d500f618fbf7acede4d6942781
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840667"
---
# <a name="regular-expression-object-expected"></a>应为正则表达式对象
你尝试调用**RegExp.prototype.toString**或**RegExp.prototype.valueOf**方法以外的类型的对象上`RegExp`。 调用此类型的对象的类型必须是`RegExp`。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   仅调用**RegExp.prototype.toString**或**RegExp.prototype.valueOf**类型的对象上的方法`RegExp`。  
  
## <a name="see-also"></a>请参阅  
 [正则表达式对象](../../javascript/reference/regular-expression-object-javascript.md)   
 [正则表达式语法 (JavaScript)](https://msdn.microsoft.com/library/1400241x)