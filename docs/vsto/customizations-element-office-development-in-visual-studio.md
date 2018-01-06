---
title: "&lt;自定义项&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档"
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
- <customizations> element
- customizations element
- application manifests [Office development in Visual Studio], <customizations> element
ms.assetid: fe1133ef-5fdf-4945-a67b-55a66a4e2109
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6d26ede37f64a95e62ff15152ff69be22ccb1ce4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomizationsgt-element-office-development-in-visual-studio"></a>&lt;自定义项&gt;元素 （Visual Studio 中的 Office 开发）
  `customizations` 命名空间的 `vstov4` 元素包括有关安装和加载各个 Office 解决方案的所有信息。  
  
## <a name="syntax-for-document-level-customizations"></a>文档级自定义项的语法  
  
```  
<customizations>  
  <customization  
    id  
    <document  
      solutionId  
    />  
  </customization>  
</customizations>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>VSTO 外接程序的语法  
  
```  
<customizations>  
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
</customizations>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `customizations` 元素包括有关各个 Office 解决方案的特定信息。 此元素必须在以下命名空间中： `vstov4=urn:schemas-microsoft-com:vsto.v4`。 程序集的子元素也必须在此命名空间中。  
  
 `customizations` 元素没有属性。  
  
 `customizations` 元素具有以下子元素。  
  
### <a name="customization"></a>自定义  
 必须的。 `customization`中的元素`vstov4`中定义命名空间[&#60; 自定义 &#62;元素 &#40; Visual Studio &#41; 中的 Office 开发](../vsto/customization-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>文档级自定义项示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示了文档级自定义项的 `customizations` 元素。  
  
> [!NOTE]  
>  此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
  <vstov4:customization>  
    <vstov4:document   
      solutionId="73e" />  
  </vstov4:customization>  
</vstov4:customizations>  
```  
  
## <a name="example-of-an-vsto-add-in"></a>VSTO 外接程序示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示了 VSTO 外接程序的 `customizations` 元素。 这是一个包含窗体区域的 Outlook VSTO 外接程序。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
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
</vstov4:customizations>  
```  
  
## <a name="see-also"></a>请参阅  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  