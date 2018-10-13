---
title: ClickOnce 部署清单 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce, deployment manifests
- deployment manifests [ClickOnce]
ms.assetid: 8457e615-e3b6-4990-8dcf-11bc590e4e9b
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 96ce7d873c20b8c29e5586a54c577a5d744b0caa
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49306782"
---
# <a name="clickonce-deployment-manifest"></a>ClickOnce 部署清单
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

部署清单是一个 XML 文件，用于描述 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 部署，包括要部署的当前 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 应用程序版本的标识。  
  
 部署清单具有下列元素和特性。  
  
|元素|描述|特性|  
|-------------|-----------------|----------------|  
|[\<程序集 > 元素](../deployment/assembly-element-clickonce-deployment.md)|必须的。 顶级元素。|`manifestVersion`|  
|[\<assemblyIdentity > 元素](../deployment/assemblyidentity-element-clickonce-deployment.md)|必须的。 标识 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 应用程序的应用程序清单。|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `culture`|  
|[\<说明 > 元素](../deployment/description-element-clickonce-deployment.md)|必须的。 标识应用程序信息用于创建 shell 表示和**添加或删除程序**控制面板中的项。|`publisher`<br /><br /> `product`<br /><br /> `supportUrl`|  
|[\<部署 > 元素](../deployment/deployment-element-clickonce-deployment.md)|可选。 标识用于部署更新并向系统公开的特性。|`install`<br /><br /> `minimumRequiredVersion`<br /><br /> `mapFileExtensions`<br /><br /> `disallowUrlActivation`<br /><br /> `trustUrlParameters`|  
|[\<compatibleFrameworks > 元素](../deployment/compatibleframeworks-element-clickonce-deployment.md)|必须的。 标识此应用程序可在其上安装和运行的 .NET Framework 版本。|`SupportUrl`|  
|[\<依赖项 > 元素](../deployment/dependency-element-clickonce-deployment.md)|必须的。 标识要为部署而安装的应用程序版本以及应用程序清单的位置。|`preRequisite`<br /><br /> `visible`<br /><br /> `dependencyType`<br /><br /> `codebase`<br /><br /> `size`|  
|[\<publisherIdentity > 元素](../deployment/publisheridentity-element-clickonce-deployment.md)|对于已签名清单是必需的。 包含有关为此部署清单签名的发布者的信息。|`Name`<br /><br /> `issuerKeyHash`|  
|[\<签名 > 元素](../deployment/signature-element-clickonce-deployment.md)|可选。 包含对此部署清单进行数字签名所需的信息。|无|  
|[\<customErrorReporting > 元素](../deployment/customerrorreporting-element-clickonce-deployment.md)|可选。 指定发生错误时所显示的 URI。|URI|  
  
## <a name="remarks"></a>备注  
 部署清单文件标识 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 应用程序部署，包括当前版本和其他部署设置。 该文件引用应用程序清单，该清单描述了应用程序的当前版本以及部署中包含的所有文件。  
  
 有关详细信息，请参阅 [ClickOnce Security and Deployment](../deployment/clickonce-security-and-deployment.md)。  
  
## <a name="file-location"></a>文件位置  
 部署清单文件引用当前版本应用程序的正确应用程序清单。 如果要使应用程序部署的新版本可用，必须更新部署清单，使其引用新的应用程序清单。  
  
 该部署清单文件必须使用强名称，并且还可以包含用于验证发布者的证书。  
  
## <a name="file-name-syntax"></a>文件名语法  
 部署清单文件的名称必须以 .application 扩展名结尾。  
  
## <a name="examples"></a>示例  
 下面的代码示例阐释了部署清单。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"  
  manifestVersion="1.0"  
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <assemblyIdentity   
    name="My Application Deployment.app"  
    version="1.0.0.0"  
    publicKeyToken="43cb1e8e7a352766"  
    language="neutral"  
    processorArchitecture="x86"  
    xmlns="urn:schemas-microsoft-com:asm.v1" />  
  <description  
    asmv2:publisher="My Company Name"  
    asmv2:product="My Application"  
    xmlns="urn:schemas-microsoft-com:asm.v1" />  
  <deployment install="true">  
    <subscription>  
      <update>  
        <expiration maximumAge="0" unit="days" />  
      </update>  
    </subscription>  
    <deploymentProvider codebase="\\myServer\sampleDeployment\MyApplicationDeployment.application" />  
  </deployment>  
  <compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
    <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.20506" />  
    <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.20506" />  
  </compatibleFrameworks>  
  <dependency>  
    <dependentAssembly  
      dependencyType="install"  
      codebase="1.0.0.0\My Application Deployment.exe.manifest"  
      size="6756">  
      <assemblyIdentity  
        name="My Application Deployment.exe"  
        version="1.0.0.0"  
        publicKeyToken="43cb1e8e7a352766"  
        language="neutral"  
        processorArchitecture="x86"  
        type="win32" />  
      <hash>  
        <dsig:Transforms>  
          <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
        </dsig:Transforms>  
        <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
        <dsig:DigestValue>E506x9FwNauks7UjQywmzgtd3FE=</dsig:DigestValue>  
      </hash>  
    </dependentAssembly>  
  </dependency>  
<publisherIdentity name="CN=DOMAIN\MyUsername" issuerKeyHash="18312a18a21b215ecf4cdb20f5a0e0b0dd263c08" /><Signature Id="StrongNameSignature" xmlns="http://www.w3.org/2000/09/xmldsig#">  
…  
</Signature></asmv1:assembly>  
```  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)



