---
title: "&lt;自定义&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档"
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
helpviewer_keywords: application manifests [Office development in Visual Studio], <customization> element
ms.assetid: a3bf7f35-bd98-4530-9226-46489cd37bb1
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 922e68a676f1f8ceac547983436c76ac01facc3b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomizationgt-element-office-development-in-visual-studio"></a>&lt;自定义&gt;元素 （Visual Studio 中的 Office 开发）
  `customization` 命名空间的 `vstov4` 元素描述特定 Office 解决方案。 对于文档级自定义项和 VSTO 外接程序，子元素是不同的。  
  
## <a name="syntax-for-document-level-customizations"></a>文档级自定义项的语法  
  
```  
<customization  
  id  
  <document  
    solutionId  
  />  
</customization>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>VSTO 外接程序的语法  
  
```  
<customization  
  id  
  <appAddin  
    application  
    loadBehavior  
    keyName>  
  <friendlyName></friendlyName>  
  <description></description>  
  <formRegions></formRegions>  
</customization>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `customization` 元素包含特定于自定义项的信息。 此元素必须在以下命名空间中： `vstov4=urn:schemas-microsoft-com:vsto.v4`。 每个 Office 解决方案都有一个 `customization` 元素。 例如，如果你在一个多项目部署中部署三个 Office 解决方案，则应用程序清单中有三个 `customization` 元素。  
  
 程序集的子元素也必须在此命名空间中。  
  
 `customization` 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`id`|对于多项目部署是必需的。 `id` 元素唯一地标识 Office 解决方案。|  
  
### <a name="document-level-customizations"></a>文档级自定义项  
 `customization` 元素具有以下子元素。  
  
#### <a name="document"></a>文档  
 `document`中的元素`vstov4`中定义命名空间[&#60; 文档 &#62;元素 &#40; Visual Studio &#41; 中的 Office 开发](../vsto/document-element-office-development-in-visual-studio.md).  
  
### <a name="vsto-add-ins"></a>VSTO 外接程序  
 `customization` 元素具有以下子元素。  
  
#### <a name="appaddin"></a>appAddin  
 `appAddin`中的元素`vstov4`中定义命名空间[&#60; appAddin &#62;元素 &#40; Visual Studio &#41; 中的 Office 开发](../vsto/appaddin-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>文档级自定义项示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示了文档级自定义项的 `customization` 元素。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstov4:customization>  
  <vstov4:document   
    solutionId="73e" />  
</vstov4:customization>  
```  
  
## <a name="example-of-an-vsto-add-in"></a>VSTO 外接程序示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示了 VSTO 外接程序的 `customization` 元素。 这是一个包含窗体区域的 Outlook VSTO 外接程序。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstov4:customization>  
  <vstov4:appAddIn   
    application="Outlook"   
    loadBehavior="3"   
    keyName="ContosoOutlookAddIn">  
    <vstov4:friendlyName>  
      ContosoOutlookAddIn  
    </vstov4:friendlyName>  
    <vstov4:description>  
      ContosoOutlookAddIn - Outlook VSTO Add-in   
      created with Visual Studio Tools for Office  
    </vstov4:description>  
    <vstov4:formRegions>  
      <vstov4:formRegion  
          name="OutlookAddIn1.FormRegion1">  
        <vstov4:messageClass name="IPM.Note" />  
        <vstov4:messageClass name="IPM.Contact" />  
        <vstov4:messageClass name="IPM.Appointment" />  
      </vstov4:formRegion>  
    </vstov4:formRegions>  
  </vstov4:appAddIn>  
</vstov4:customization>  
```  
  
## <a name="see-also"></a>请参阅  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  