---
title: Visual Studio Tools for Office runtime 中的程序集
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio Tools for Office runtime, assemblies
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8ff32d472d0e2005b22acb8d751e03c6aa3f61ef
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="assemblies-in-the-visual-studio-tools-for-office-runtime"></a>Visual Studio Tools for Office runtime 中的程序集
  在创建新的 Office 项目时，Visual Studio 会自动添加对项目类型和项目的目标 .NET Framework 使用的 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 程序集的引用。 在 .NET Framework 3.5、 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]和 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]的 Office 扩展中存在不同的程序集。 有关这些 Office 扩展的详细信息，请参阅[Visual Studio Tools for Office runtime 概述](../vsto/visual-studio-tools-for-office-runtime-overview.md)。  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-4-and-the-includenetv45vstoincludesnet-v45-mdmd"></a>.NET Framework 4 的 Office 扩展中的程序集和 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 下表列出了包含在 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 和 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]的 Office 扩展中的程序集。 有关文档的命名空间和这些程序集中的类型，请参阅[的托管引用&#40;Visual Studio 中的 Office 开发&#41;](../vsto/managed-reference-office-development-in-visual-studio.md)。  
  
|程序集名称|描述|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.dll|提供以下类型：<br /><br /> -用于创建功能区自定义和智能标记的类型。 **注意：** 中已弃用智能标记[!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]和[!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]。<br />-用于在文档级自定义和自定义任务窗格在 VSTO 外接程序中创建操作窗格的类型。|  
|Microsoft.Office.Tools.Excel.dll|提供表示 Excel 项目的主机项和主机控件以及支持类型的接口。 有关详细信息，请参阅[通过使用扩展的对象自动化 Excel](../vsto/automating-excel-by-using-extended-objects.md)。|  
|Microsoft.Office.Tools.Outlook.dll|提供可用于在 Outlook VSTO 外接程序中创建自定义窗体区域的类型。|  
|Microsoft.Office.Tools.Word.dll|提供表示 Word 项目的主机项和主机控件及支持类型的接口。 有关详细信息，请参阅[自动执行使用扩展的对象实现 Word](../vsto/automating-word-by-using-extended-objects.md)。|  
|Microsoft.Office.Tools.v4.0.Framework.dll|提供以下类型：<br /><br /> -可由 Visual Studio Tools for Office runtime 引发的异常。<br />的在创建 Outlook 时可以使用的属性窗体区域。|  
|Microsoft.Office.Tools.dll|提供作为 Visual Studio Tools for Office Runtime 基础结构一部分，并且不应在代码中直接使用的类型。|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|提供以下类型：<br /><br /> -<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>属性和<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>接口，可以用于在文档级自定义项中缓存数据对象。 有关详细信息，请参阅[缓存数据](../vsto/caching-data.md)。<br />-<xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction>接口，可实现来运行其他安装步骤作为 Office 解决方案的 ClickOnce 安装的最后一步。 有关详细信息，请参阅[使用 ClickOnce 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)。<br />-可由 Visual Studio Tools for Office runtime 引发的异常。<br />-其他类型，属于 Visual Studio Tools for Office runtime 基础结构，并且不应在代码中直接使用。|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|提供以下类型：<br /><br /> -<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>类，可以使用将自定义程序集附加到文档并访问文档中缓存的数据。 有关详细信息，请参阅[使用 ServerDocument 类管理服务器上的文档](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)。<br />-多个类表示的层次结构缓存中的文档级自定义项的数据。 有关详细信息，请参阅[访问服务器上的文档中的数据](../vsto/accessing-data-in-documents-on-the-server.md)。|  
  
 以 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 为目标的项目还引用以下程序集。 这些程序集不属于 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 可再发行组件。 相反，它们是必须与解决方案一起部署的依赖程序集。 默认情况下，它们复制到项目的生成输出文件夹（这些程序集的 **“本地属性”** 属性设置为 **“True”**）。 如果使用 ClickOnce 部署项目，这些程序集包含在生成的包中。  
  
|程序集名称|描述|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|提供 VSTO 外接程序项目中生成的 `ThisAddIn` 类和所有项目中生成的功能区类的基类。|  
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|提供以下类型：<br /><br /> -基类生成`ThisWorkbook`和`Sheet`类在文档级项目 for Excel。<br />你可以使用在 Excel 项目中的工作表的 Windows 窗体控件。|  
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|提供 Outlook 项目中生成的 `ThisAddIn` 和窗体区域类的基类。|  
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|提供以下类型：<br /><br /> -基类生成`ThisDocument`Word 的文档级项目中的类。<br />可以使用的文档在 Word 项目中的 Windows 窗体控件。|  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-35"></a>.NET Framework 3.5 的 Office 扩展中的程序集  
 下表列出了包含在 .NET Framework 3.5 的 Office 扩展中的程序集。 有关命名空间和这些程序集中的类的文档，请参阅 Visual Studio 2008 文档中的以下参考部分： [ http://go.microsoft.com/fwlink/?LinkId=160658 ](http://go.microsoft.com/fwlink/?LinkId=160658)。  
  
|程序集名称|描述|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v9.0.dll|提供以下类型：<br /><br /> 有关 VSTO 外接程序-Microsoft.Office.Tools.AddIn 基本类。<br />-用于创建功能区自定义和智能标记的类。 **注意：** 中已弃用智能标记[!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]和[!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]。<br />-用于在文档级自定义和自定义任务窗格在 VSTO 外接程序中创建操作窗格的类。|  
|Microsoft.Office.Tools.Excel.v9.0.dll|提供 Excel 解决方案的主机项和主机控件。 有关详细信息，请参阅[通过使用扩展的对象自动化 Excel](../vsto/automating-excel-by-using-extended-objects.md)。|  
|Microsoft.Office.Tools.Outlook.v9.0.dll|提供可用于在 Outlook VSTO 外接程序中创建自定义窗体区域的类。|  
|Microsoft.Office.Tools.Word.v9.0.dll|提供 Word 解决方案的主机项和主机控件。 有关详细信息，请参阅[自动执行使用扩展的对象实现 Word](../vsto/automating-word-by-using-extended-objects.md)。|  
|Microsoft.Office.Tools.v9.0.dll|提供以下类型：<br /><br /> - [RemoteBindableComponent](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb546360(v=vs.90))类，该类提供的数据绑定功能有关主机控件在文档级自定义项。<br />-其他类型，属于 Visual Studio Tools for Office runtime 基础结构，并且不应在代码中直接使用。|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|提供以下类型：<br /><br /> -<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>属性和<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>接口，可以用于在文档级自定义项中缓存数据对象。 有关详细信息，请参阅[缓存数据](../vsto/caching-data.md)。<br />-可由 Visual Studio Tools for Office runtime 引发的异常。<br />-其他类型，属于 Visual Studio Tools for Office runtime 基础结构，并且不应在代码中直接使用。|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|提供 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> 接口，可实现该接口以将其他安装步骤作为 Office 解决方案的 ClickOnce 安装程序的最后一步进行运行。 有关详细信息，请参阅[高级 Office 解决方案部署](http://msdn.microsoft.com/en-us/9147b6f6-849f-4cb1-b2c5-e22658d74b02)。|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|提供以下类型：<br /><br /> -<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>类，可以使用以编程方式将自定义程序集附加到文档并访问文档中缓存的数据。 有关详细信息，请参阅[使用 ServerDocument 类管理服务器上的文档](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)。<br />-多个类表示的层次结构缓存中的文档级自定义项的数据。 有关详细信息，请参阅[访问服务器上的文档中的数据](../vsto/accessing-data-in-documents-on-the-server.md)。|  
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|提供以下类型：<br /><br /> -Microsoft.VisualStudio.Tools.Office.Runtime.Security.AddInSecurityEntry 和 Microsoft.VisualStudio.Tools.Office.Runtime.Security.UserInclusionList 类，该类可用于创建用户包含列表条目，以向 Office 授予信任面向.NET Framework 3.5 的解决方案。<br />-其他类型，属于 Visual Studio Tools for Office runtime 基础结构，并且不应在代码中直接使用。|  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio Tools for Office runtime 概述](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Visual Studio Tools for Office runtime 安装方案](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)  
  
  