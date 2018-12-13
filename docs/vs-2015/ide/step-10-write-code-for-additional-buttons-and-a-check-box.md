---
title: 步骤 10：编写其他按钮和复选框的代码 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 51063d0c0ae7dc47653786107e691bed74fed699
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49228041"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>步骤 10：编写其他按钮和复选框的代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

现在，您可以完成其他四个方法了。 虽然您可以复制并粘贴此代码，但是若想从此教程中学些到最多的内容，那么请键入代码并使用 IntelliSense。  
  
 此代码将为您之前添加的按钮添加功能。 如果不使用此代码，这些按钮将不执行任何操作。 当您激活控件时，这些按钮将使用其 `Click` 事件（复选框使用 `CheckChanged` 事件）来执行不同的操作。 例如，`clearButton_Click` 事件（当选择“清除图片”按钮时激活），在将其 `Image` 属性设置为 `null`（或 `nothing`）后，可擦除当前的图像。 代码中的每个事件都包括一些注释，用于解释代码所执行的操作。  
  
 ![视频链接](../data-tools/media/playvideo.gif "PlayVideo")有关本主题的视频版本，请观看[Tutorial 1: Create a Picture Viewer in Visual Basic - Video 5](http://go.microsoft.com/fwlink/?LinkId=205216)（教程 1：用 Visual Basic 创建图片查看器 - 视频 5）或 [Tutorial 1: Create a Picture Viewer in C# - Video 5](http://go.microsoft.com/fwlink/?LinkId=205206)（教程 1：用 C# 创建图片查看器 - 视频 5）。 这些视频使用 Visual Studio 的早期版本，因此在一些菜单命令和其他用户界面元素上略有差异。 但是，概念和过程与当前版本的 Visual Studio 大同小异。  
  
> [!NOTE]
>  最佳做法是始终对您的代码进行注释。 注释是供用户阅读的信息，花些时间使您的代码易于理解是值得的。 程序会忽略注释行上的所有内容。 在 Visual C# 中，通过在开头键入两个正斜杠 (//) 来注释一行；在 Visual Basic 中，通过以单引号 (') 开头来注释一行。  
  
### <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>为其他按钮和复选框编码代码  
  
-   将以下代码添加到你的 Form1 代码文件（Form1.cs 或 Form1.vb）。 选择“VB”选项卡以查看 Visual Basic 代码。  
  
     [!code-csharp[VbExpressTutorial1Step9_10#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial1Step9_10#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/vb/form1.vb#2)]  
  
### <a name="to-continue-or-review"></a>继续或查看  
  
-   若要转到下一个教程，请参阅[步骤 11：运行程序和尝试其他功能](../ide/step-11-run-your-program-and-try-other-features.md)。  
  
-   若要返回上一个教程，请参阅[步骤 9：评审代码、为代码添加注释和测试代码](../ide/step-9-review-comment-and-test-your-code.md)。



