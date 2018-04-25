---
title: 安全性和已本地化的附属程序集 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca89e842b6e5229890e93c06b7ca83658f6dbf7c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="security-and-localized-satellite-assemblies"></a>安全性和已本地化的附属程序集

如果主程序集使用强命名，则必须使用与主程序集相同的私钥对附属程序集进行签名。 如果主程序集和附属程序集之间的公钥/私钥对不匹配，则不会加载资源。 有关对程序集签名的详细信息，请参阅[如何：使用强名称为程序集签名](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)。  
  
 通常，可能需要要求你组织的签名组或外部签名组织使用私钥进行签名。 这是因为私钥具有敏感性：访问通常限制为少数几个人。 可以在开发期间使用延迟签名。 有关更多信息，请参见 [延迟为程序集签名](/dotnet/framework/app-domains/delay-sign-assembly)。  
  
## <a name="see-also"></a>请参阅

- [程序集安全注意事项](/dotnet/framework/app-domains/assembly-security-considerations)  - [安全性的基础概念](/dotnet/standard/security/key-security-concepts)   
- [基于 .NET Framework 的国际应用程序简介](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
- [本地化应用程序](../ide/localizing-applications.md)   
- [对应用程序进行全球化和本地化](../ide/globalizing-and-localizing-applications.md)