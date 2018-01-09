---
title: "管理项目和解决方案属性 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5315dd07ab0c791cc9a349c08431ceb4a9b5c797
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="managing-project-and-solution-properties"></a>管理项目和解决方案属性

项目具有一些控制编译、调试、测试和部署的很多方面的属性。 有些属性在所有项目类型中是通用的，而有些则只用于特定语言或平台。 右键单击解决方案资源管理器中的项目节点并选择“属性”，或者在菜单栏上的“快速启动”搜索框中键入“属性”，即可访问项目属性。

![项目上下文菜单](../ide/media/vs2015_proj_prop_menu.gif "vs2015_proj_prop_menu")

在项目树本身，.NET 项目也可能具有一个属性节点。

![解决方案资源管理器树中的属性节点](../ide/media/vs2015_props_se.png "VS2015_Props_SE")

## <a name="project-properties"></a>项目属性

项目属性分到各个组且每组具有自己的属性页。 这些页面可能因语言和项目类型不同而有所不同。

### <a name="c-visual-basic-and-f-projects"></a>C#、Visual Basic 和 F# 项目

在 C#、Visual Basic 和 F# 项目中，属性在“项目设计器”中公开。 下图显示了 C# 中的 WPF 项目的生成属性页：

![Visual Studio 项目设计器](../ide/media/vs2015_proppage_build.png "VS2015_PropPage_Build")

有关“项目设计器”中每个属性页的信息，请参阅[项目属性引用](../ide/reference/project-properties-reference.md)。

> [!TIP]
> 解决方案和项目项都具有一些属性；这些属性可在[属性窗口](../ide/reference/properties-window.md)中访问，而不是在**项目设计器**中访问。

### <a name="c-and-javascript-projects"></a>C++ 和 JavaScript 项目

C++ 和 JavaScript 项目对于管理项目属性有不同的用户界面。 此图显示了 C++ 项目属性页（JavaScript 页面与此类似）：

![Visual C++ 项目属性](../ide/media/vs2015_projprops_cpp.png "VS2015_ProjProps_cpp")

有关 C++ 项目属性的信息，请参阅[使用项目属性 (C++)](/cpp/ide/working-with-project-properties)。 有关 JavaScript 属性的详细信息，请参阅[属性页，JavaScript](../ide/reference/property-pages-javascript.md)。

## <a name="solution-properties"></a>解决方案属性

若要访问解决方案上的属性，请右键单击“解决方案资源管理器”中的解决方案节点，然后选择“属性”。 在对话框中，可以设置用于“调试”或“发布”版本的项目配置，选择按下 F5 时应启动的项目，然后设置代码分析选项。

## <a name="see-also"></a>请参阅

[Visual Studio 中的解决方案和项目](../ide/solutions-and-projects-in-visual-studio.md)
