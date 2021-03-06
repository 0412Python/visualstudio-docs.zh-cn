---
title: 项目优先级 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], opening items
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 47c96e9384d561aeda3a966ca8bc5b305a9351e2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628255"
---
# <a name="project-priority"></a>项目优先级
项目项通常是解决方案中只有一个项目的成员。 因此，IDE 可以轻松地确定使用哪个项目打开的项。 但是，如果项是多个项目的成员，IDE 将使用优先级方案来确定打开的项的最佳项目。

 以下列表显示项目优先级方案：

-   IDE 调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A>解决方案来确定文档是否为该项目的成员的每个项目的方法。

-   如果文档是项目的成员，项目将响应优先级 project 为根据其处理该文档。 例如，语言项目会使用其语言源文件的高优先级进行响应，但使用不用作其生成过程的一部分的无法识别的文件类型较低优先级进行响应。

-   为文档提供自定义、 特定于项目的编辑器或设计器的项目还收到了高优先级。

-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>枚举提供文档的优先级值。

-   指定的最高优先级的项目有打开的文档的上下文。 如果两个项目返回相同的优先级值，请将首选活动项目。 如果解决方案中没有项目做出响应，它可以打开的文档，IDE 会将文档放在杂项文件项目中。 有关详细信息，请参阅[杂项文件项目](../../extensibility/internals/miscellaneous-files-project.md)。

## <a name="see-also"></a>请参阅
- [杂项文件项目](../../extensibility/internals/miscellaneous-files-project.md)
- [如何：打开编辑器的打开的文档](../../extensibility/how-to-open-editors-for-open-documents.md)
- [添加项目和项目项模板](../../extensibility/internals/adding-project-and-project-item-templates.md)