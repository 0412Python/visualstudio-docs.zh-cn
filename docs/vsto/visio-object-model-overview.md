---
title: "Visio 对象模型概述 |Microsoft 文档"
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
- Visio [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Visio
- objects [Office development in Visual Studio], Office object models
- Office object models
- Visio object model
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e829842f4e530b014a19f69c567a91dc49bd78e6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="visio-object-model-overview"></a>Visio 对象模型概述
  要为 Microsoft Office Visio 开发 Office 解决方案，则可以与 Visio 对象模型进行交互。 此对象模型包含的类和 Visio 中，主互操作程序集中提供并在 Microsoft.Office.Interop.Visio 命名空间中定义的接口。  
  
 本主题概要介绍 Visio 对象模型。 有关使用 Visio 对象模型在 Office 项目中执行任务的信息，请参阅以下主题：  
  
-   [使用 Visio 文档](../vsto/working-with-visio-documents.md)  
  
-   [使用 Visio 形状](../vsto/working-with-visio-shapes.md)  
  
## <a name="understanding-the-visio-object-model"></a>了解 Visio 对象模型  
 Visio 提供了许多可与之交互的对象。 这些对象采用严格遵循用户界面的层次结构进行组织。 层次结构的顶部是 [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx) 对象。 此对象表示 Visio 的当前实例。 Microsoft.Office.Interop.Visio.Application 对象包含的 Microsoft.Office.Interop.Visio.Document 和 Microsoft.Office.Interop.Visio.Page 对象以及 Microsoft.Office.Interop.Visio.Documents 和Microsoft.Office.Interop.Visio.Pages 集合。 每个对象和集合都有许多方法和属性，可进行访问以便操作并与其进行交互。  
  
 有关详细信息，请参阅适用于 [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx)、 [Microsoft.Office.Interop.Visio.Document](https://msdn.microsoft.com/library/office/ff765575.aspx)和 [Microsoft.Office.Interop.Visio.Page](https://msdn.microsoft.com/library/office/ff767035.aspx) 对象，以及 [Microsoft.Office.Interop.Visio.Documents](https://msdn.microsoft.com/library/office/ff768812.aspx) 和 [Microsoft.Office.Interop.Visio.Pages](https://msdn.microsoft.com/library/office/ff766165.aspx) 集合的 VBA 的参考文档。  
  
 下列各节简要介绍了顶级对象以及它们彼此交互的方式。 这些对象包括以下对象：  
  
-   应用程序对象  
  
-   文档对象  
  
-   Page 对象  
  
### <a name="application-object"></a>应用程序对象  
 Microsoft.Office.Interop.Visio.Application 对象表示 Visio 应用程序，并且所有其他对象的父级。 其成员通常作为一个整体应用于 Visio。 可以使用的属性和方法的 Microsoft.Office.Interop.Visio.Application 和 Microsoft.Office.Interop.Visio.ApplicationSettings 对象来控制 Visio 环境。  
  
 在 VSTO 外接程序项目中，你可以通过访问 Microsoft.Office.Interop.Visio.Application 对象`Application`字段`ThisAddIn`类。 有关详细信息，请参阅 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)。  
  
### <a name="document-object"></a>文档对象  
 Microsoft.Office.Interop.Visio.Document 对象是 Visio 编程的核心。 它表示绘图、模具或模板文件。 当你打开 Visio 文档或创建新文档时，创建一个新的 Microsoft.Office.Interop.Visio.Document 对象，该添加到 Microsoft.Office.Interop.Visio.Application 对象 Microsoft.Office.Interop.Visio.Documents 集合对象.  
  
 具有焦点的文档被称为活动文档。 它表示由 Microsoft.Office.Interop.Visio.Application 对象的 Microsoft.Office.Interop.Visio.Application.ActiveDocument 属性。  
  
### <a name="page-object"></a>Page 对象  
 Microsoft.Office.Interop.Visio.Page 对象表示前景页或背景页的绘图区域。 Microsoft.Office.Interop.Visio.Page.Background 属性可用于确定某页是前景页或背景页。  
  
 若要创建形状，可以使用包括的 Microsoft.Office.Interop.Visio.Page.DrawSpline 和 Microsoft.Office.Interop.Visio.Page.DrawOval 方法的方法。 此外，可以从模具检索母板，并将形状放置在页面上，通过使用 Microsoft.Office.Interop.Visio.Page.Drop 或 Microsoft.Office.Interop.Visio.Page.DropMany 方法。  
  
## <a name="using-the-visio-object-model-documentation"></a>使用 Visio 对象模型文档  
 有关 Visio 对象模型的完整信息，可以参考 Visio VBA 对象模型引用。 VBA 对象模型引用在 Visio 对象模型被公开到 Visual Basic for Applications (VBA) 代码时记录该对象模型。 有关详细信息，请参阅 [Visio 2010 对象模型引用](http://go.microsoft.com/fwlink/?LinkId=199775)。  
  
 VBA 对象模型引用中的所有对象和成员都对应于 Visio 主互操作程序集 (PIA) 中的类型和成员。 例如，VBA 对象模型引用中的文档对象对应于 Visio PIA 中的 Microsoft.Office.Interop.Visio.Document 类型。 虽然 VBA 对象模型引用提供大多数属性、方法和事件的代码示例，但如果想要将其用于使用 Visual Studio 创建的 Visio VSTO 外接程序项目，则必须将本引用中的 VBA 代码转换成 Visual Basic 或 Visual C#。  
  
> [!NOTE]  
>  此时，没有任何 Visio 主互操作程序集的参考文档。  
  
 有关相关的代码示例和创建 Visio 解决方案的其他工具，请参阅 [Visio 2010 软件开发工具包](http://go.microsoft.com/fwlink/?LinkId=196501)。  
  
### <a name="additional-types-in-primary-interop-assemblies"></a>主互操作程序集中的其他类型  
 可以在主互操作程序集中找到因为实现不同而对 VBA 不可见的类型。 VBA 提供 Visio 对象模型的视图，该视图仅包括可以直接使用的对象和成员。 主互操作程序集公开相同的对象模型，但它们还包括将 COM 对象模型中的对象转换为托管代码的其他接口、类和的成员。 这些附加项不应直接在代码中使用。  
  
 有关更多信息，请参见 [Office 主互操作程序集中的类和接口概述](http://go.microsoft.com/fwlink/?LinkId=189592) 和 [Office Primary Interop Assemblies](../vsto/office-primary-interop-assemblies.md)。  
  
## <a name="see-also"></a>请参阅  
 [Visio 解决方案](../vsto/visio-solutions.md)   
 [使用 Visio 文档](../vsto/working-with-visio-documents.md)   
 [使用 Visio 形状](../vsto/working-with-visio-shapes.md)  
  
  