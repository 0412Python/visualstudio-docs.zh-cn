---
title: "生成的构造函数的代码生成 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53b1ab5cb202995cb6a5e9eeef76ee4cf38b4ea9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-constructor-in-visual-basic"></a>在 Visual Basic 中生成一个构造函数
**新增功能：**便会立即生成新的构造函数的类上的代码。 

**何时：**引入新的构造函数，并且想要正确地将其，自动声明。  

**原因：**你无法再使用它，声明构造函数，但此功能将它，并用正确的参数，自动生成。 

**如何：**

1. 将光标置于该行上红色的波浪线，该值指示你已使用尚不存在的构造函数的情况。

   ![突出显示的代码](media/constructor_highlight.png)

1. 接下来，请执行以下任一操作：
   * **键盘**
     * 按**Ctrl +。** 向触发器**快速操作和重构**菜单，然后选择**生成构造函数中的*TypeName** * 从预览窗口弹出窗口。
   * **鼠标**
     * 右键单击并选择**快速操作和重构**菜单，然后选择**生成构造函数中的*TypeName** * 从预览窗口弹出窗口。
     * 将鼠标悬停在红色波形曲线和单击 ![灯泡](media/bulb.png) 显示的图标。
     * 单击 ![灯泡](media/bulb.png) 如果文本光标已在行中使用红色波形曲线的左边距中显示的图标。

   ![生成构造函数预览](media/constructor_preview.png)

   >[!TIP]
   >使用[**预览更改**](../../ide/preview-changes.md)底部的预览窗口来查看所有将在你的选择之前所做的更改的链接。

1. 构造函数将自动创建包含根据其使用情况推断出任何参数。

   ![生成构造函数结果](media/constructor_result.png)
  
## <a name="see-also"></a>请参阅  
[代码生成 (Visual Basic)](../code-generation-vb.md)  
[预览更改](../../ide/preview-changes.md)