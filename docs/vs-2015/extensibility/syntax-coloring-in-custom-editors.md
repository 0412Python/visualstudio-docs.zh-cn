---
title: 自定义编辑器中的语法着色 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - syntax coloring
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d690afae8d546b4597159bfd094a7a21d2528780
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58937156"
---
# <a name="syntax-coloring-in-custom-editors"></a>自定义编辑器中的语法着色
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 环境 SDK 编辑器，包括核心编辑器中，使用语言服务来标识特定的语法项并将其与给定的文档视图的指定颜色显示。  
  
## <a name="colorization-requirements"></a>着色要求  
 必须实现语言服务的着色器的所有编辑器：  
  
1.  使用一个对象，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>来管理要进行着色的文本和一个对象，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>提供文本的文档视图。  
  
2.  通过查询使用的语言服务的标识 GUID 的 VSPackage 的服务提供商来获取特定的语言服务的接口。  
  
3.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A>对象实现的方法<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>。 此方法将关联的语言服务<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>实现的 VSPackage 使用来管理以进行着色的文本。  
  
## <a name="core-editor-usage-of-a-language-services-colorizer"></a>核心编辑器使用的语言服务的着色器  
 当具有着色器的语言服务通过核心编辑器、 分析和呈现的文本的语言服务的着色器的实例会自动进行而不需要您采取任何进一步的干预。  
  
 IDE 以透明方式：  
  
-   调用着色器根据需要解析和分析文本，如添加或修改的实现中<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>。  
  
-   确保提供的提供的文档视图显示<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>实现更新和重新绘制使用着色器返回的信息。  
  
## <a name="non-core-editor-usage-of-a-language-services-colorizer"></a>语言服务的着色器的非核心编辑器使用情况  
 非核心编辑器实例还可以使用语言服务的语法颜色设置服务，但它们必须显式检索和应用服务的着色器并重新绘制其文档视图本身。  
  
 若要执行此操作，需要对非核心编辑器：  
  
1.  获取语言服务的着色器对象 (它实现`T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer`和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2>)。 你的 VSPackage 将这是通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A>语言服务接口上的方法。  
  
2.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法来请求特定范围的文本进行着色。  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法返回值的数组，一个用于在文本中的每个字母 s p a n 着色。 它还标识为特定类型的可着色项，例如注释、 关键字或数据类型的文本跨距。  
  
3.  使用返回的着色信息<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>重绘和显示其文本。  
  
> [!NOTE]
>  除了使用语言服务的着色器，VSPackage 可以选择使用常规用途的 Visual Studio 环境 SDK 文本着色机制。 此机制的详细信息，请参阅[使用字体和颜色](../extensibility/using-fonts-and-colors.md)。  
  
## <a name="see-also"></a>请参阅  
 [旧版语言服务中的语法着色](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [实现语法着色](../extensibility/internals/implementing-syntax-coloring.md)   
 [如何：使用内置的可着色项](../extensibility/internals/how-to-use-built-in-colorable-items.md)   
 [自定义可着色项](../extensibility/internals/custom-colorable-items.md)
