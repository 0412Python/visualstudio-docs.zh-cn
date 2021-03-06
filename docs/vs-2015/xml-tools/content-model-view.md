---
title: 内容模型视图 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c0a25766327f2e074c4b7f8adf1ccde5a46895d9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58936136"
---
# <a name="content-model-view"></a>内容模型视图
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
内容模型视图提供局部和全局架构节点及其组件（包括简单类型和复杂类型、元素、模型组、特性及特性组）的图形表示形式。 在内容模型视图中不能查看 XML 注释和处理指令。 内容模型视图包括两个面板：**工作区**面板，其中包含一系列中的节点[XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)，和设计图面，可从中查看架构的内容模型在选择的节点**工作区**面板。 内容模型视图还包括 XML 架构设计器工具栏和痕迹栏。  
  
 在下图中，“工作区”面板包括六个架构节点。 在“工作区”面板中，`purchaseOrder` 节点处于选定状态且该节点显示在设计图面中。  
  
 ![XML 架构设计器的内容模型视图](../xml-tools/media/xsddesigner-contentmodelview.gif "XSDDesigner_ContentModelView")  
  
## <a name="workspace-panel"></a>“工作区”面板  
 将节点添加到工作区后，节点的列表将显示在**工作区**的内容模型视图的面板。 当选择中的节点**工作区**面板，它们显示在内容模型视图的设计图面上。 若要从工作区中删除节点，请使用 XSD 设计器工具栏中，**工作区**面板上下文菜单或 DELETE 键。  
  
 有关将节点添加的信息，请参阅中的"向工作区中添加节点"一节[XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)。  
  
## <a name="design-surface"></a>设计图面  
 在“工作区”面板中选择某节点后，该节点会添加到内容模型视图的设计图面中，可在设计图面中查看该节点的详细信息。  
  
 节点的内容模型由一个可展开的图形树表示，其中元素和特性显示为树节点。 默认情况下，仅一个级别处于展开状态。 其他信息（如排序器、类型名称、组和其他容器）与其包含的元素和特性一起放置在垂直条（当展开时）中。 双击垂直条时，该垂直条会变为水平且树会折叠。 双击水平条时，该水平条会变为垂直且树会展开。 选择垂直条将会选定容器中的所有节点。 如果元素是可展开或可折叠的，则节点的右侧会显示 Expander。  
  
 如果设计图面为空，则会显示 XML 编辑器、XML 架构资源管理器和水印。 *水印*是指向所有 XSD 设计器视图的列表。 如果架构集有错误，在列表末尾显示以下文本："使用错误列表以查看并集中解决错误。"  
  
## <a name="breadcrumb-bar"></a>痕迹栏  
 内容模型视图底部的痕迹栏显示所选节点在架构集中所处的位置。  
  
## <a name="context-menus"></a>上下文菜单  
 在设计图面或“工作区”面板上右键单击某一项时，会出现一个上下文菜单。 下表介绍了可用于内容模型视图的设计图面的选项。  
  
|Option|描述|  
|------------|-----------------|  
|**在 XML 架构资源管理器中显示**|将焦点置于架构资源管理器上，并突出显示架构集节点。|  
|**在关系图视图中显示**|切换到图形视图。|  
|**生成示例 XML**|仅可用于全局元素。 生成全局元素的示例 XML 文件。|  
|**显示文档**|显示或隐藏批注/文档节点内容。|  
|**将关系图导出为图像...**|将设计图面保存到 XPS 文件。|  
|**查看代码**|在 XML 编辑器中打开包含所选节点的文件。 在 XML 架构资源管理器中选定的项也会在 XML 编辑器中选定。|  
|**“属性”窗口**|此时将打开**属性**窗口 （如果尚未打开）。 此窗口显示有关节点的信息。|  
  
 下表介绍了可用于“工作区”面板的选项。  
  
|Option|描述|  
|------------|-----------------|  
|**在 XML 架构资源管理器中显示**|将焦点置于架构资源管理器上，并突出显示架构集节点。|  
|**在关系图视图中显示**|切换到图形视图。|  
|**清空工作区**|清空工作区和设计图面。|  
|**从工作区中删除**|从工作区和设计图面中删除所选节点。|  
|**移除所选内容从工作区**|从工作区和设计图面中删除未选择的节点。|  
|**生成示例 XML**|仅可用于全局元素。 生成全局元素的示例 XML 文件。|  
|**选择所有**|选择“工作区”面板中的所有节点。|  
|**查看代码**|在 XML 编辑器中打开包含所选节点的文件。 在 XML 架构资源管理器中选定的项也会在 XML 编辑器中选定。|  
|**“属性”窗口**|此时将打开**属性**窗口 （如果尚未打开）。 此窗口显示有关节点的信息。|  
  
## <a name="properties-window"></a>属性窗口  
 使用上下文菜单可初始打开**属性**窗口。 默认情况下**属性**窗口显示在 Visual Studio 的右下角中。 当您单击的内容模型视图中呈现的节点时，该节点的属性将显示在**属性**窗口。  
  
## <a name="xsd-designer-toolbar"></a>XSD 设计器工具栏  
 当内容模型视图处于活动状态时，会启用以下 XSD 设计器工具栏按钮。  
  
 ![XML 架构设计器工具栏](../xml-tools/media/xsdcontentmodelviewtoolbar.gif "XSDContentModelViewToolbar")  
  
|Option|描述|  
|------------|-----------------|  
|**显示起始视图**|切换到[启动视图](../xml-tools/start-view.md)。 可以使用键盘快捷方式访问此视图：**CTRL + 1**。|  
|**显示内容模型视图**|切换到[内容模型视图](../xml-tools/content-model-view.md)。 可以使用键盘快捷方式访问此视图：**CTRL + 2**。|  
|**显示图形视图**|切换到[图形视图](../xml-tools/graph-view.md)。 可以使用键盘快捷方式访问此视图：**CTRL + 3**。|  
|**清空工作区**|清空工作区和设计图面。|  
|**从工作区中删除**|从工作区和设计图面中删除所选节点。|  
|**移除所选内容从工作区**|从工作区和设计图面中删除未选择的节点。|  
|**显示文档**|显示或隐藏批注/文档节点内容。|  
  
## <a name="panscroll"></a>平移/滚动  
 可通过以下方法平移设计图面：使用滚动条，或在按住 Ctrl 键的同时单击并拖动鼠标。 如果使用单击并拖动鼠标的方法平移设计图面，光标将更改为指向四个方向的十字箭头。  
  
## <a name="undoredo"></a>撤消/重做  
 在内容模型视图中，为以下操作启用了撤消/重做功能：  
  
-   通过拖放操作添加单个节点。  
  
-   从架构资源管理器的搜索结果窗口中添加多个节点。  
  
-   从起始视图添加节点。  
  
-   删除单个或多个节点。  
  
## <a name="zoom"></a>缩放  
 内容模型视图的右下角提供了缩放功能。  
  
 可通过以下方法控制缩放功能：  
  
- 当鼠标悬停在内容模型视图的图面上时，按住 Ctrl 键的同时滚动鼠标滚轮。  
  
- 使用滑块控件。 滑块显示当前缩放级别。  
  
  当选择缩放滑块、将鼠标悬停在其上或将 Ctrl 与鼠标滚轮结合使用进行缩放时，缩放滑块是不透明的；在其他任何情况下，它均是透明的。  
  
## <a name="xml-editor-integration"></a>XML 编辑器集成  
 可使用上下文菜单在 XSD 设计器和 XML 编辑器之间来回切换。  
  
 如果在 XML 编辑器中对架构集进行更改，则相应的更改会在内容模型视图中同步。 有关详细信息，请参阅[使用 XML 编辑器集成](../xml-tools/integration-with-xml-editor.md)。  
  
## <a name="see-also"></a>请参阅  
 [XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)
