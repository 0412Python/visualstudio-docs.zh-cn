---
title: "如何： 以编程方式打开文本文件作为工作簿 |Microsoft 文档"
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
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 45d2b85ea8c005d56ddc076d0b758a0c9e4a2d67
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>如何：以编程方式及工作簿形式打开文本文件
  为工作簿，可以打开一个文本文件。 必须传递你想要打开的文本文件的名称。 你可以指定多个可选参数，例如到开始分析以及文件中的数据的列格式的行号。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要以下组件：  
  
-   名为的逗号分隔的文本文件`Test.txt`，包含至少三个行的文本。  
  
-   该文本文件`Test.txt`似乎存储在驱动器 c。  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [如何： 以编程方式打开工作簿](../vsto/how-to-programmatically-open-workbooks.md)   
 [如何： 以编程方式创建新的工作簿](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [如何： 以编程方式保存工作簿](../vsto/how-to-programmatically-save-workbooks.md)   
 [如何： 以编程方式关闭工作簿](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  