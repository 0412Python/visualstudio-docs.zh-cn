---
title: 步骤 11：运行程序并尝试其他功能 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 38d83c46ecf910a4df5050c6e73de58a1a0963b1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480131"
---
# <a name="step-11-run-your-program-and-try-other-features"></a>步骤 11：运行程序并尝试其他功能
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[步骤 11： 运行程序并尝试其他功能](https://docs.microsoft.com/visualstudio/ide/step-11-run-your-program-and-try-other-features)。  
  
您的程序已完成并已做好运行准备。 您可以运行程序并设置 PictureBox 的背景色。 若要了解更多信息，请尝试通过以下操作来改进程序：更改窗体的颜色、自定义按钮和复选框以及更改窗体的属性。  
  
 若要下载完整的示例版本，请参阅 [Complete Picture Viewer tutorial sample](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8)（图片查看器教程的完整示例）。  
  
 ![视频链接](../data-tools/media/playvideo.gif "PlayVideo")有关本主题的视频版本，请观看[Tutorial 1: Create a Picture Viewer in Visual Basic - Video 5](http://go.microsoft.com/fwlink/?LinkId=205216)（教程 1：用 Visual Basic 创建图片查看器 - 视频 5）或 [Tutorial 1: Create a Picture Viewer in C# - Video 5](http://go.microsoft.com/fwlink/?LinkId=205206)（教程 1：用 C# 创建图片查看器 - 视频 5）。 这些视频使用 Visual Studio 的早期版本，因此在一些菜单命令和其他用户界面元素上略有差异。 但是，概念和过程与当前版本的 Visual Studio 大同小异。  
  
### <a name="to-run-your-program-and-set-the-background-color"></a>运行程序并设置背景色  
  
1.  选择 F5，或者在菜单栏上依次选择“调试”、“启动调试”。  
  
2.  在打开图片之前，请选择“设置背景色”按钮。 随即打开“颜色”对话框。  
  
     ![“颜色”对话框](../ide/media/express-colordialog.png "Express_ColorDialog")  
“颜色”对话框  
  
3.  选择一种要设置为 PictureBox 背景色的颜色。 仔细查看 `backgroundButton_Click()` 方法以了解其工作原理。  
  
    > [!NOTE]
    >  通过将某个图片的 URL 粘贴到“打开文件”对话框中，可以从 Internet 加载该图片。 尝试找到一个带透明背景的图像，以便显示您的背景色。  
  
4.  选择“清除图片”按钮以确保清除图片。 然后，选择“关闭”按钮退出程序。  
  
### <a name="to-try-other-features"></a>尝试其他功能  
  
-   使用“BackColor”属性更改窗体和按钮的颜色。  
  
-   使用“Font”和“ForeColor”属性自定义按钮和复选框。  
  
-   更改窗体的“FormBorderStyle”和“ControlBox”属性。  
  
-   使用窗体的“AcceptButton”和“CancelButton”属性可使得在用户选择 Enter 或 Esc 键时自动选择这些按钮。 使程序在用户选择 Enter 时打开“打开文件”对话框，并在用户选择 ESC 时关闭此对话框。  
  
### <a name="to-continue-or-review"></a>继续或查看  
  
-   若要了解有关 Visual Studio 编程的详细信息，请参阅 [Programming Concepts](http://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6)（编程概念）。  
  
-   若要了解有关 Visual Basic 的详细信息，请参阅[使用 Visual Basic 开发应用程序](http://msdn.microsoft.com/library/1e1c0c81-6d95-4167-a98b-44b1efb6d25f)。  
  
-   若要了解有关 Visual C# 的详细信息，请参阅 [C# 语言和 .NET Framework 介绍](http://msdn.microsoft.com/library/0a2dff4e-cd84-42ff-8141-e89889b24081)。  
  
-   若要转到下一教程，请参阅[教程 2：创建计时数学测验](../ide/tutorial-2-create-a-timed-math-quiz.md)。  
  
-   若要返回到上一个教程，请参阅[步骤 10：编写其他按钮和复选框的代码](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)。



