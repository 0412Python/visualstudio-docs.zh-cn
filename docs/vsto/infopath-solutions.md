---
title: "InfoPath 解决方案 |Microsoft 文档"
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
- solutions [Office development in Visual Studio], InfoPath
- templates [Office development in Visual Studio], InfoPath
- InfoPath [Office development in Visual Studio]
- Office development in Visual Studio, InfoPath solutions
- projects [Office development in Visual Studio], InfoPath
- Office solutions [Office development in Visual Studio], InfoPath
- Office projects [Office development in Visual Studio], InfoPath
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4e59b91ff6159af8f6e5736621c0443d3d96c8b5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="infopath-solutions"></a>InfoPath 解决方案
  Visual Studio 提供了一些项目模板，你可以使用这些模板来创建用于 Microsoft Office InfoPath 2013 和 InfoPath 2010 的 VSTO 外接程序。 InfoPath 在 Office 2016 中不可用。  
  
> [!NOTE]  
>  你可以仍创建 VSTO 外接程序中用于 InfoPath 即使安装了 Office 2016。 只需与 Office 2016 并行安装 InfoPath 2013 或 Office 2013。  
  
 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]  
  
> [!NOTE]  
>  开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有内存占用较小与 VSTO 外接程序和解决方案，相比，并且你可以通过使用几乎任何 web 编程技术，例如 HTML5、 JavaScript、 CSS3 和 XML 生成它们。  
  
 InfoPath 的 VSTO 外接程序类似于其他 Microsoft Office 应用程序的 VSTO 外接程序。 这些类型的解决方案包含由应用程序加载的一个程序集。 不管打开了哪个窗体或窗体模板，最终用户都能访问此程序集的功能。 有关 VSTO 外接程序的详细信息，请参阅 [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md) 和 [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)。  
  
> [!NOTE]  
>  Visual Studio 2015 不包括 Visual Studio 的早期版本中提供的 InfoPath 窗体模板项目。 也无法使用 Visual Studio 2015 打开或编辑用 Visual Studio 的早期版本创建的 InfoPath 窗体模板项目。 但是，可以使用 Visual Studio Tools for Applications 打开和编辑 InfoPath 窗体模板项目。 有关详细信息，请参阅 [在 InfoPath 2010 中使用 VSTO 2008 项目](http://go.microsoft.com/fwlink/?LinkID=218903)。  
  
## <a name="automating-infopath-by-using-an-add-in"></a>使用外接程序实现 InfoPath 自动化  
 若要从使用 Visual Studio 中的 Office 开发工具创建的 Office VSTO 外接程序访问 InfoPath 对象模型，请在项目中使用 `Application` 类的 `ThisAddIn` 字段。 `Application` 字段返回 <xref:Microsoft.Office.Interop.InfoPath.Application> 对象，该对象表示 InfoPath 的当前实例。 有关详细信息，请参阅 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)。  
  
 从 VSTO 外接程序调入 InfoPath 对象模型时，将使用在 InfoPath 的主互操作程序集中提供的类型。 该主互操作程序集将作为 VSTO 外接程序中的托管代码和 InfoPath 中的 COM 对象模型之间的桥梁。 InfoPath 主互操作程序集中的所有类型都是在 <xref:Microsoft.Office.Interop.InfoPath> 命名空间中定义的。 有关 InfoPath 主互操作程序集的详细信息，请参阅 [关于 Microsoft Office InfoPath 主互操作程序集](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)。 有关主互操作程序集的详细信息一般情况下，请参阅[Office 解决方案开发概述 &#40;VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)和[Office 主互操作程序集](../vsto/office-primary-interop-assemblies.md)。  
  
## <a name="customizing-the-user-interface-of-infopath-by-using-an-add-in"></a>使用外接程序自定义 InfoPath 的用户界面  
 为 InfoPath 创建 VSTO 外接程序时，可以使用几个不同的 UI 自定义选项。 下表列出了其中一些选项。  
  
|任务|更多相关信息|  
|----------|--------------------------|  
|创建自定义任务窗格。|[自定义任务窗格](../vsto/custom-task-panes.md)|  
|向 InfoPath 的功能区中添加自定义选项卡。|[自定义 InfoPath 功能区](../vsto/customizing-a-ribbon-for-infopath.md)|  
  
 有关自定义 UI InfoPath 和其他 Microsoft Office 应用程序的详细信息，请参阅[Office UI 自定义项](../vsto/office-ui-customization.md)。  
  
## <a name="see-also"></a>请参阅  
 [关于 Microsoft Office InfoPath 主互操作程序集](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)   
 [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office 解决方案开发概述 &#40;VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO 外接程序的体系结构](../vsto/architecture-of-vsto-add-ins.md)   
 [如何： 在 Visual Studio 中创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [在 Office 解决方案中编写代码](../vsto/writing-code-in-office-solutions.md)   
 [Office 主互操作程序集](../vsto/office-primary-interop-assemblies.md)   
 [Office UI 自定义项](../vsto/office-ui-customization.md)   
 [InfoPath 2010 中的 Office 开发](http://go.microsoft.com/fwlink/?LinkId=199012)  
  
  