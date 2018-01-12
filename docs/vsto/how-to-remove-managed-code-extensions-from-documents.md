---
title: "如何： 从文档中删除托管的代码扩展 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], removing
- documents [Office development in Visual Studio], managed code extensions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c83f9794cdce71db9f51a6adca69fbeabc8c7a8e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-remove-managed-code-extensions-from-documents"></a>如何：移除文档中的托管代码扩展
  从文档或工作簿的 Microsoft Office Word 或 Microsoft Office Excel 的文档级自定义项的一部分，可以以编程方式删除自定义程序集。 然后，用户可以打开的文档并查看内容，但你将添加到文档中的任何自定义用户界面 (UI) 将不会出现，并将不运行代码。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 你可以使用提供的 RemoveCustomization 方法之一来删除自定义程序集[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。 你使用哪种方法取决于是否想要删除在运行时自定义项 （即，通过运行时 Word 自定义项中的代码文档或 Excel 工作簿处于打开状态），或如果你想要从已关闭的文档或文档中删除自定义该 i没有安装 Microsoft Office 的服务器上的 s。  
  
 ![视频链接](../vsto/media/playvideo.gif "视频链接")相关的视频演示，请参阅[i： 不要如何附加或分离 VSTO 程序集从 Word 文档？](http://go.microsoft.com/fwlink/?LinkId=136782)。  
  
### <a name="to-remove-the-customization-assembly-at-run-time"></a>若要删除在运行时的自定义项程序集  
  
1.  在自定义代码中，调用<xref:Microsoft.Office.Tools.Word.Document.RemoveCustomization%2A>方法 （对于 Word) 或<xref:Microsoft.Office.Tools.Excel.Workbook.RemoveCustomization%2A>（针对 Excel) 的方法。 只有在不再需要自定义后，应调用此方法。  
  
     你的代码中调用此方法的位置取决于如何使用自定义项。 例如，如果客户使用你的自定义功能，直到他们就可以将文档发送给其他客户端只需要到此文档本身 （不自定义项），你可以提供一些 UI，以调用 RemoveCustomization，当客户单击它。 或者，如果首次打开它，但自定义项不提供任何其他功能，通过客户的直接访问时，你的自定义将填充具有数据的文档，然后你可以调用 RemoveCustomization 尽快自定义项正在初始化文档的完成。  
  
### <a name="to-remove-the-customization-assembly-from-a-closed-document-or-a-document-on-a-server"></a>从已关闭的文档或服务器上的文档中删除自定义程序集  
  
1.  在不需要 Microsoft Office，如控制台应用程序的项目或 Windows 窗体项目中，添加 Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll 程序集的引用。  
  
2.  添加以下**导入**或**使用**到你的代码文件顶部的语句。  
  
     [!code-csharp[Trin_VstcoreDeployment#1](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#1)]
     [!code-vb[Trin_VstcoreDeployment#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#1)]  
  
3.  调用静态<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A>方法<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>类，并指定参数的解决方案文档路径。  
  
     下面的代码示例假定，你要从名为的文档中删除自定义项**WordDocument1.docx**即在桌面上。  
  
     [!code-csharp[Trin_VstcoreDeployment#2](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#2)]
     [!code-vb[Trin_VstcoreDeployment#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#2)]  
  
4.  生成项目并想要删除自定义项的计算机上运行应用程序。 计算机必须具有 Visual Studio 2010 Tools for Office Runtime 安装。  
  
## <a name="see-also"></a>请参阅  
 [使用 ServerDocument 类管理服务器上的文档](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [如何：将托管代码扩展附加到文档](../vsto/how-to-attach-managed-code-extensions-to-documents.md)  
  
  