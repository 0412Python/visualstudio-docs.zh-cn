---
title: "如何： 指定托管的代码规则集的多个项目在解决方案中 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.solution
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: e0b6a2864340f87702b765f49605ebdb3aaa555c
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2018
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>如何：为解决方案中的多个项目指定托管代码规则集

默认情况下，解决方案中的所有托管的项目分配 Microsoft 最少量建议规则的代码分析*规则集*。 你可以更改分配给该解决方案的属性对话框中的解决方案中的项目的规则集。

> [!NOTE]
> 默认情况下，不会作为的生成步骤运行项目代码分析。 若要启用代码分析作为的生成步骤，请参阅[如何： 为托管代码项目的配置代码分析](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)。

1. 在 Visual Studio 中打开解决方案。

2. 上**分析**菜单上，单击**解决方案的配置代码分析**。

3. 如有必要，展开**通用属性**，然后单击**代码分析设置**。

4. 你可以指定一个或多个项目设置的规则。

    - 若要指定的规则集的单个项目，单击项目名称。

    - 若要指定设置为多个项目的规则，请按住 CTRL 并单击项目名称。

    - 若要在解决方案中指定的所有项目，按住 SHIFT 并单击列表中的项目。

5. 单击**规则集**字段的项目，然后单击你想要应用设置的规则的名称。