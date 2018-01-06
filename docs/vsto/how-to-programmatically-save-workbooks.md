---
title: "如何： 以编程方式保存工作簿 |Microsoft 文档"
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
- workbooks, saving in XML format
- workbooks, saving
- workbooks, saving backup copies
ms.assetid: 991ccf9b-5213-4094-9030-284ec167bdcc
caps.latest.revision: "50"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d0aa6421893c9d930f917e98fb8aa85b6ceb28d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-save-workbooks"></a>如何：以编程方式保存工作簿
  可通过多种方式保存工作簿。 可以保存工作簿而不更改路径。 如果以前没有保存过工作簿，则应该通过指定一个路径来保存工作簿。 如果没有显式路径，Microsoft Office Excel 会使用创建文件时为其指定的名称将文件保存在当前文件夹中。 还可以保存工作簿的副本，而不修改内存中打开的工作簿。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="saving-a-workbook-without-changing-the-path"></a>保存工作簿而不更改路径  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>保存与文档级自定义项关联的工作簿  
  
1.  调用 ThisWorkbook 类的 <xref:Microsoft.Office.Tools.Excel.Workbook.Save%2A> 方法。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#4)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>在 VSTO 外接程序中保存活动工作簿  
  
1.  调用 <xref:Microsoft.Office.Interop.Excel._Workbook.Save%2A> 方法以保存活动工作薄。 若要使用下面的代码示例，请在 Excel 的应用程序级项目内的 `ThisAddIn` 类中运行它。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="saving-a-workbook-with-a-new-path"></a>使用新路径保存工作簿  
 可以将指定的工作簿保存到新位置或以新名称保存，还可以选择指定文件格式、密码和访问模式等。  
  
> [!NOTE]  
>  你可能想要设置<xref:Microsoft.Office.Interop.Excel._Application.DisplayAlerts%2A>属性**False**使用新路径保存工作簿，因为以某些格式保存需要交互之前。 此属性设置为**False**导致 Excel 使用所有默认值。  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>保存与文档级自定义项关联的工作簿  
  
1.  调用 `ThisWorkbook` 类的 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> 方法。 若要使用下面的代码示例，请在 `ThisWorkbook` 类中运行它。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#5)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>在 VSTO 外接程序中保存活动工作簿  
  
1.  调用 <xref:Microsoft.Office.Interop.Excel._Workbook.SaveAs%2A> 方法以将活动工作簿保存到新路径。 若要使用下面的代码示例，请在 Excel 的应用程序级项目内的 `ThisAddIn` 类中运行它。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="saving-a-copy-of-the-workbook"></a>保存工作簿的副本  
 可以将工作簿的副本保存到文件中，而不修改内存中打开的工作簿。 当想要创建备份副本而不修改工作簿的位置时，此方法十分有用。  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>保存与文档级自定义项关联的工作簿  
  
1.  调用 `ThisWorkbook` 类的 <xref:Microsoft.Office.Tools.Excel.Workbook.SaveCopyAs%2A> 方法。 若要使用下面的代码示例，请在 `ThisWorkbook` 类中运行它。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#6)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>在 VSTO 外接程序中保存活动工作簿  
  
1.  调用 <xref:Microsoft.Office.Interop.Excel._Workbook.SaveCopyAs%2A> 方法以保存活动工作簿的副本。 若要使用下面的代码示例，请在 Excel 的应用程序级项目内的 `ThisAddIn` 类中运行它。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="robust-programming"></a>可靠编程  
 以交互方式取消任何保存或复制工作簿的方法将在代码中引发运行时错误。 例如，如果你的过程调用<xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A>方法但不是会从 Excel 中，不禁用提示和用户单击**取消**出现提示时，Excel 将引发运行时错误。  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [工作簿主机项](../vsto/workbook-host-item.md)   
 [如何： 以编程方式关闭工作簿](../vsto/how-to-programmatically-close-workbooks.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)   
 [主机项和主机控件概述](../vsto/host-items-and-host-controls-overview.md)  
  
  