---
title: "如何： 以编程方式创建新的工作簿 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], creating workbooks
- workbooks, creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 1a1ed1679b5a50616219ef7f398261c72053c9a0
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-create-new-workbooks"></a>如何：以编程方式新建工作簿
  以编程方式创建工作簿时，它是一个本机 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象，而不是 <xref:Microsoft.Office.Tools.Excel.Workbook> 主机项。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 你可以在 VSTO 外接程序项目中为 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象生成一个 <xref:Microsoft.Office.Tools.Excel.Workbook> 主机项。 有关更多信息，请参见 [在运行时在 VSTO 外接程序中扩展 Word 文档和 Excel 工作簿](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)。  
  
### <a name="to-create-a-new-workbook"></a>创建新的工作簿  
  
1.  使用 <xref:Microsoft.Office.Interop.Excel.Workbooks> 集合的 <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> 方法。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#1)]  
  
    > [!NOTE]  
    >  通过将想要用作参数的模板传递给 <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> 方法，可以基于该模板而不是默认模板创建工作簿。  
  
## <a name="see-also"></a>请参阅  
 [在运行时扩展 Word 文档和 Excel 工作簿在 VSTO 外接程序](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [在运行时向 Office 文档添加控件](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [如何： 以编程方式打开工作簿](../vsto/how-to-programmatically-open-workbooks.md)   
 [如何： 以编程方式保存工作簿](../vsto/how-to-programmatically-save-workbooks.md)   
 [如何： 以编程方式关闭工作簿](../vsto/how-to-programmatically-close-workbooks.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)   
 [主机项和主机控件概述](../vsto/host-items-and-host-controls-overview.md)  
  
  