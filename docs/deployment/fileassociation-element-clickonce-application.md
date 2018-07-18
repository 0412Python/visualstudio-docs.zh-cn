---
title: '&lt;fileAssociation&gt;元素 （ClickOnce 应用程序） |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f59ef1d00951d4c49c1bcb19c6c9122e281c3ca
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
ms.locfileid: "31561072"
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;fileAssociation&gt;元素 （ClickOnce 应用程序）
标识要与应用程序相关联的文件扩展。  
  
## <a name="syntax"></a>语法  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `fileAssociation` 元素是可选的。 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`extension`|必须的。 要与应用程序相关联的文件扩展名。|  
|`description`|必须的。 使用 shell 的文件类型的说明。|  
|`progid`|必须的。 唯一标识的文件类型的名称。|  
|`defaultIcon`|必须的。 指定要用于此扩展名的文件的图标。 必须使用指定的图标文件[\<文件 > 元素](../deployment/file-element-clickonce-application.md)内[\<程序集 > 元素](../deployment/assembly-element-clickonce-application.md)，其中包含此元素。|  
  
## <a name="remarks"></a>备注  
 此元素必须包括到的 XML 命名空间参考"urn： 架构-microsoft-com:clickonce.v1"。 如果`<fileAssociation>`元素时，它必须后`<application>`其父代中的元素[\<程序集 > 元素](../deployment/assembly-element-clickonce-application.md)。  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 将不会覆盖现有文件关联。 但是，ClickOnce 应用程序可以重写当前用户的文件扩展名。 卸载该 ClickOnce 应用程序后，ClickOnce 删除文件关联的用户，并重新处于活动状态的每台计算机关联。  
  
## <a name="example"></a>示例  
 下面的代码示例阐释了`fileAssociation`应用程序中的元素的文本编辑器应用程序使用部署清单[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]。 此代码示例还包括[\<文件 > 元素](../deployment/file-element-clickonce-application.md)按所需的`defaultIcon`属性。  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>请参阅  
 [ClickOnce 应用程序清单](../deployment/clickonce-application-manifest.md)