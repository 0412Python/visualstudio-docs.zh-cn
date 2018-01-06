---
title: "实现抽象类的代码生成 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 663a5ed393502d24c8b677dd2776a87b9855540e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="implement-an-abstract-class-in-visual-basic"></a>在 Visual Basic 中实现抽象类
**新增功能：**便会立即生成所需实现抽象类的代码。 

**何时：**你想要从抽象类继承。  

**原因：**但此功能会自动生成所有方法签名，可以手动实现所有抽象成员一个由一。 

**如何：**

1. 将光标放在行上： 有红色的波浪线，该值指示已从抽象类继承，但未实现了所有必需的成员。

   ![突出显示的代码](media/abstract_highlight.png)

1. 接下来，请执行以下任一操作：
   * **键盘**
     * 按**Ctrl +。** 向触发器**快速操作和重构**菜单，然后选择**实现抽象类**从预览窗口弹出窗口。
   * **鼠标**
     * 右键单击并选择**快速操作和重构**菜单，然后选择**实现抽象类**从预览窗口弹出窗口。
     * 将鼠标悬停在红色波形曲线和单击 ![灯泡](media/bulb.png) 显示的图标。
     * 单击 ![灯泡](media/bulb.png) 如果文本光标已在行中使用红色波形曲线的左边距中显示的图标。

   ![实现类预览](media/abstract_preview.png)

   >[!TIP]
   >使用[**预览更改**](../../ide/preview-changes.md)底部的预览窗口来查看所有将在你的选择之前所做的更改的链接。
   >
   >此外，你可以使用**文档**，**项目**，和**解决方案**跨多个创建正确的方法签名的预览窗口底部的链接从抽象类继承的类。

1. 抽象方法签名将自动创建，并且可以实现。

   ![实现类结果](media/abstract_result.png)

## <a name="see-also"></a>请参阅  
[代码生成 (Visual Basic)](../code-generation-vb.md)  
[预览更改](../../ide/preview-changes.md)