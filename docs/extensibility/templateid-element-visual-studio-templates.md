---
title: TemplateID 元素 （Visual Studio 模板） |Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateID
helpviewer_keywords:
- <TemplateID> element [Visual Studio Templates]
- TemplateID element [Visual Studio Templates]
ms.assetid: 6ca24b4e-0325-4a9e-855e-0cbbe7361d8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bcd8f318c66766e016aa146cc5be22ca3c57bb62
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54959903"
---
# <a name="templateid-element-visual-studio-templates"></a>TemplateID 元素（Visual Studio 模板）
指定到项模板由一组分类的项模板的标识符[TemplateGroupID](../extensibility/templategroupid-element-visual-studio-templates.md)元素。  
  
 \<VSTemplate>  
 \<TemplateData>  
 \<TemplateID>  
  
## <a name="syntax"></a>语法  
  
```  
<TemplateID> ... </TemplateID>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 将此模板分类并定义此模板在 **“新建项目”** 或 **“添加新项”** 对话框中的显示方式。|  
  
## <a name="text-value"></a>文本值  
 一个`string`，表示到项模板由一组分类的项模板的标识符`TemplateGroupID`元素。  
  
## <a name="remarks"></a>备注  
 `TemplateID` 是可选元素。  
  
 如果.vstemplate 文件中省略`TemplateID`元素，则[名称](../extensibility/name-element-visual-studio-templates.md)元素用作模板标识符。  
  
 值`TemplateID`元素使用与项目系统注册 (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Projects\\) 中显示的筛选器模板**添加新项**对话框。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)