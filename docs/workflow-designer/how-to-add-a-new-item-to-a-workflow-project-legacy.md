---
title: "如何： 将新项添加到工作流项目 （旧版） |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- sequential workflows, adding to workflow projects
- workflows, adding new items
- state machine workflows, adding to workflow projects
- activities, adding to workflow projects
ms.assetid: 130cd83d-942d-437b-bbb5-8088ec0a6d79
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d2b0c644854f8f08ff7aeeb05f92fe3fd359f45e
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-a-new-item-to-a-workflow-project-legacy"></a>如何：向工作流项目添加新项（旧版）
创建使用旧的 Windows 工作流设计器提供的工作流项目之后[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]面向[!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)]或[!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]，你可以添加[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]项和其他熟悉[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]项到你项目。

 下表列出了可添加到工作流项目中的 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 项。

|项|描述|
|----------|-----------------|
|Activity|活动定义在设计器代码文件中而用户代码在另一个代码文件中的活动。|
|Activity (具有单独的代码)|位于不同代码文件中的活动定义（以工作流标记形式表示）和用户代码。|
|顺序工作流 (代码)|工作流定义在设计器代码文件中而用户代码在另一个代码文件中的顺序工作流。|
|顺序工作流 (具有单独的代码)|工作流定义（以工作流标记形式表示）与用户代码位于不同代码文件中的顺序工作流。|
|状态机工作流 (代码)|工作流定义在设计器代码文件中而用户代码在另一个代码文件中的状态机工作流。|
|状态机工作流 (具有单独的代码)|工作流定义（以工作流标记形式表示）与用户代码位于不同代码文件中的状态机工作流。|

### <a name="to-add-a-new-item-to-a-workflow-project"></a>向工作流项目添加新项

1.  上**项目**菜单上，单击**添加新项**。

     **添加新项**对话框随即打开。

2.  选择一个项。

     前面的表列出了可用的 Windows Workflow Foundation 选择。

3.  单击**添加**将该项添加到工作流项目。

## <a name="see-also"></a>请参阅

- [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)