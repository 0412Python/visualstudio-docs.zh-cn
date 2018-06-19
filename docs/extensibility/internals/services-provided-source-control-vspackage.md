---
title: 提供的服务 (源控件 VSPackage) |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a52ffa7067a91582d8bfe31e09d6b03be54c4ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129597"
---
# <a name="services-provided-source-control-vspackage"></a>提供的服务 (源控件 VSPackage)
服务是通过其在 Vspackage 和 Visual Studio 集成的开发环境 (IDE) 和其安装的 Vspackage 之间共享功能的主要机制。 有关服务和它们的重要性在 Visual Studio IDE 中详细说明，请参阅[使用和提供服务](../../extensibility/using-and-providing-services.md)。  
  
## <a name="the-source-control-service"></a>源控件服务  
 Visual Studio 提供两个图层的服务、 IDE 级服务和包级别服务。 Visual Studio IDE 以本机方式提供 IDE 级别服务。 源代码管理包使用这些服务的一些。 源代码管理包作为 VSPackage 通过提供自己的私有源控件服务共享其源代码管理功能。 源代码管理包封装了通过它可由 Visual Studio IDE 的协定的形式实现的源控件相关接口的一组。  
  
## <a name="see-also"></a>另请参阅  
 [设计元素](../../extensibility/internals/source-control-vspackage-design-elements.md)