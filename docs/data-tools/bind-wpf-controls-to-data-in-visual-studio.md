---
title: 将 WPF 控件绑定到数据-第 1 部分
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: e05a1e0c-5082-479d-bbc9-d395b0bc6580
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 00cc931a75dee9d3762e94ca522e4d060584840b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939094"
---
# <a name="bind-wpf-controls-to-data-in-visual-studio"></a>在 Visual Studio 中将 WPF 控件绑定到数据

通过将数据绑定到 [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] 控件，可以向应用程序的用户显示数据。 若要创建这些数据绑定控件，可以将项从**数据源**窗口拖到[!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)]Visual Studio 中。 本主题将介绍一些你可用于创建数据绑定 [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] 应用程序的最常见的任务、工具和类。

有关如何在 Visual Studio 中创建数据绑定控件的常规信息，请参阅[将控件绑定到 Visual Studio 中的数据](../data-tools/bind-controls-to-data-in-visual-studio.md)。 有关 [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] 数据绑定的详细信息，请参阅[数据绑定概述](/dotnet/framework/wpf/data/data-binding-overview)。

## <a name="tasks-involved-in-binding-wpf-controls-to-data"></a>将 WPF 控件绑定到数据所涉及的任务

下表列出了可以通过将项从“数据源”窗口拖到 [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)] 来完成的任务。

|任务|详细信息|
|----------| - |
|新建数据绑定控件。<br /><br /> 将现有控件绑定到数据。|[将 WPF 控件绑定到数据集](../data-tools/bind-wpf-controls-to-a-dataset.md)|
|创建按父子关系显示相关数据的控件：当用户选择一个控件中的父数据记录时，另一个控件将显示所选记录的相关子数据。|[在 WPF 应用程序中显示相关数据](../data-tools/display-related-data-in-wpf-applications.md)|
|创建“查找表”，此表根据一个表的外键字段的值显示另一个表中的信息。|[在 WPF 应用程序中创建查找表](../data-tools/create-lookup-tables-in-wpf-applications.md)|
|将控件绑定到数据库中的图像。|[将控件绑定到数据库中的图片](../data-tools/bind-controls-to-pictures-from-a-database.md)|

## <a name="valid-drop-targets"></a>有效放置目标

只能将“数据源”窗口中的项拖动到 [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)] 中的有效放置目标。 有两种主要的有效放置目标：容器和控件。 容器是通常包含控件的用户界面元素。 例如，网格是容器，窗口也是容器。

## <a name="generated-xaml-and-code"></a>生成的 XAML 和代码

当将某项从**数据源**到窗口[!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)]，Visual Studio 生成[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]定义新的数据绑定控件 （或将现有控件绑定到数据源）。 对于某些数据源，Visual Studio 还会生成代码用数据填充数据源的代码隐藏文件中。

下表列出[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]和 Visual Studio 为每种类型的数据源中生成的代码**数据源**窗口。

| 数据源 | 生成将控件绑定到数据源的 XAML | 生成用数据填充数据源的代码 |
| - | - | - |
| 数据集 | 是 | 是 |
| [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] | 是 | 是 |
| 服务 | 是 | No |
| 对象 | 是 | No |

### <a name="datasets"></a>数据集

当将表或列从**数据源**到设计器中，Visual Studio 窗口生成[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]，执行以下操作：

-   将数据集和新的 <xref:System.Windows.Data.CollectionViewSource> 添加到将项拖至的容器的资源中。 <xref:System.Windows.Data.CollectionViewSource> 是可用于导航和显示数据集中的数据的对象。

-   为控件创建数据绑定。 如果将项拖动到设计器中的一个现有控件上，则 XAML 会将该控件绑定到该项。 如果将项拖动到容器时，XAML 创建拖动的项，为选定的控件，并将控件绑定到的项。 将在新的 <xref:System.Windows.Controls.Grid> 内创建该控件。

Visual Studio 还将对代码隐藏文件做出以下更改：

- 为包含该控件的 <xref:System.Windows.FrameworkElement.Loaded> 元素创建 [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] 事件处理程序。 该事件处理程序用数据填充表，从容器的资源中检索 <xref:System.Windows.Data.CollectionViewSource>，然后使第一个数据项成为当前项。 如果<xref:System.Windows.FrameworkElement.Loaded>事件处理程序已存在，Visual Studio 将此代码添加到现有的事件处理程序。

### <a name="entity-data-models"></a>实体数据模型

当您将实体或实体属性从**数据源**到设计器中，Visual Studio 窗口生成[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]，执行以下操作：

- 将新的 <xref:System.Windows.Data.CollectionViewSource> 添加到将项拖至的容器的资源中。 <xref:System.Windows.Data.CollectionViewSource> 是可用于导航和显示实体中的数据的对象。

- 为控件创建数据绑定。 如果将项拖动到设计器中的一个现有控件上，则 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] 会将该控件绑定到该项。 如果将项拖动到容器中，[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]创建控件的选择为拖动的项，并将控件绑定到的项。 将在新的 <xref:System.Windows.Controls.Grid> 内创建该控件。

Visual Studio 还将对代码隐藏文件做出以下更改：

- 添加一种新方法，该方法返回对拖动到设计器中的实体（或包含拖动到设计器中的属性的实体）的查询。 新的方法同名`Get<EntityName>Query`，其中`\<EntityName>`是实体的名称。

- 为包含该控件的 <xref:System.Windows.FrameworkElement.Loaded> 元素创建 [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] 事件处理程序。 事件处理程序调用`Get<EntityName>Query`方法来用数据填充实体检索<xref:System.Windows.Data.CollectionViewSource>从容器的资源，然后使第一个数据项的当前项。 如果<xref:System.Windows.FrameworkElement.Loaded>事件处理程序已存在，Visual Studio 将此代码添加到现有的事件处理程序。

### <a name="services"></a>服务

当将服务对象或属性从**数据源**设计器中，Visual Studio 窗口生成[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]创建数据绑定控件 （或将现有控件绑定到对象或属性）。 但是，Visual Studio 不生成用数据填充代理服务对象的代码。 你必须自己编写此代码。 有关演示如何执行此操作的示例，请参阅[绑定 WPF 控件添加到 WCF 数据服务](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)。

Visual Studio 将生成执行以下操作的 XAML：

- 将新的 <xref:System.Windows.Data.CollectionViewSource> 添加到将项拖至的容器的资源中。 <xref:System.Windows.Data.CollectionViewSource> 是一个对象，它可用于导航和显示服务返回的对象中的数据。

- 为控件创建数据绑定。 如果将项拖动到设计器中的一个现有控件上，则 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] 会将该控件绑定到该项。 如果将项拖动到容器中，[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]创建控件的选择为拖动的项，并将控件绑定到的项。 将在新的 <xref:System.Windows.Controls.Grid> 内创建该控件。

### <a name="objects"></a>对象

当将对象或属性从**数据源**设计器中，Visual Studio 窗口生成[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]创建数据绑定控件 （或将现有控件绑定到对象或属性）。 但是，Visual Studio 不生成代码以用数据填充该对象。 你必须自己编写此代码。

> [!NOTE]
> 自定义类都必须是公共的并在默认情况下，具有无参数构造函数。 它们不能为其语法中具有"dot"的嵌套的类。 有关详细信息，请参阅[XAML 及 WPF 的自定义类](/dotnet/framework/wpf/advanced/xaml-and-custom-classes-for-wpf)。

Visual Studio 生成[!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]，执行以下操作：

-   将新的 <xref:System.Windows.Data.CollectionViewSource> 添加到将项拖至的容器的资源中。 <xref:System.Windows.Data.CollectionViewSource> 是可用于导航和显示对象中的数据的对象。

-   为控件创建数据绑定。 如果将项拖动到设计器中的一个现有控件上，则 XAML 会将该控件绑定到该项。 如果将项拖动到容器时，XAML 创建拖动的项，为选定的控件，并将控件绑定到的项。 将在新的 <xref:System.Windows.Controls.Grid> 内创建该控件。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)