---
title: 开发 Office 解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, about developing solutions
- solutions [Office development in Visual Studio], developing
- Office solutions [Office development in Visual Studio], developing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b84334ac4454760c7457f131a9cd438f715a78ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="developing-office-solutions"></a>开发 Office 解决方案
  使用 Visual Studio 中的 Office 开发人员工具设计项目并设置项目文件后，便可以开始集中精力实现代码和自定义用户界面 (UI)。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有内存占用较小与 VSTO 外接程序和解决方案，相比，并且你可以通过使用几乎任何 web 编程技术，例如 HTML5、 JavaScript、 CSS3 和 XML 生成它们。  
  
## <a name="office-solutions-programming-model"></a>Office 解决方案编程模型  
 Office 对象模型公开各种可以编程的对象。 每当使用托管代码进行 Office 解决方案编程，都将编写使用 Office 主互操作程序集中的类型的代码。 在使用 Visual Studio 中的 Office 项目模板创建的解决方案中，还编写直接针对项目中生成的类的代码。 有关更多信息，请参见 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)。  
  
## <a name="programming-different-types-of-office-solutions"></a>编程不同类型的 Office 解决方案  
 你正在创建的解决方案的类型确定你可以在项目中使用的功能。 例如，在设计时通过从 Visual Studio 中的 *“工具箱”*拖放项，可以向文档级自定义项添加 Windows 窗体控件和扩展的 Office 控件（名为 **主机控件** ）。 但是，如果你正在开发一个 VSTO 外接程序，通过编写代码，可以在运行时仅将这些种类的控件添加到文档。  
  
 有关特定于不同类型解决方案的功能的详细信息，请参阅以下主题：  
  
-   [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)。  
  
-   [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)。  
  
-   [Office UI 自定义项](../vsto/office-ui-customization.md)。  
  
 有关可有助于规划你的 Office 解决方案和程序以帮助创建项目的背景信息，请参阅 [Designing and Creating Office Solutions](../vsto/designing-and-creating-office-solutions.md)。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)|描述在 Office 解决方案中编写代码的各个方面。|  
|[Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)|提供对 VSTO 外接程序的编程模型和相关编程任务的概述。|  
|[Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)|提供对文档级自定义项的编程模型和相关编程任务的概述。|  
|[Office UI 自定义](../vsto/office-ui-customization.md)|介绍可通过使用 VSTO 外接程序和文档级自定义项来自定义 Office 应用程序 UI 的不同方式。|  
|[Office 解决方案中的数据](../vsto/data-in-office-solutions.md)|介绍可以使用 Office 解决方案中的数据的不同方法，例如将数据绑定到控件和缓存文档级自定义项中的数据。|  
|[自动保存如何影响 Office 解决方案](./how-autosave-impacts-office-solutions.md)|描述你可能需要时启用了自动保存对 Office 解决方案进行的调整。|
|[Office 解决方案疑难解答](../vsto/troubleshooting-office-solutions.md)|提供用于解决在创建 Office 解决方案时可能遇到的常见问题的提示。|  
|[Office 中的线程支持](../vsto/threading-support-in-office.md)|提供在 Office 解决方案中使用多个线程的概述。|  
|[Office 项目中的辅助功能](../vsto/accessibility-in-office-projects.md)|描述 Office 解决方案中可用的辅助功能。|  
  
## <a name="see-also"></a>请参阅  
 [如何： 创建和修改自定义文档属性](../vsto/how-to-create-and-modify-custom-document-properties.md)   
 [如何： 读取和写入向文档属性](../vsto/how-to-read-from-and-write-to-document-properties.md)   
 [如何： 面向 Office 多语言用户界面](../vsto/how-to-target-the-office-multilingual-user-interface.md)   
 [演练：创建你的第一个 Excel VSTO 外接程序](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)   
 [演练： 创建你的第一个文档级自定义 excel](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [演练： 创建第一个 VSTO 外接程序的 Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)   
 [演练： 创建第一个 VSTO 外接程序 powerpoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [演练： 创建第一个 VSTO 外接程序项目](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [演练： 创建第一个 VSTO 外接程序 word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)   
 [演练：创建你的第一个 Word 文档级自定义项](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)  
  
  