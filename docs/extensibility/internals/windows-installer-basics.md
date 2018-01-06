---
title: "Windows 安装程序基础知识 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1a9f895db0d202dd573e7c665b1185f6e3f4b751
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="windows-installer-basics"></a>Windows 安装程序基础知识
Windows Installer 安装和卸载应用程序或用户的计算机上的软件产品在名为 Windows 安装程序组件 （有时称为 WICs 或只是组件） 的单元中执行这些任务。 一个 GUID 标识每个 WIC，这是安装和引用计数设置使用 Windows 安装程序的基本单位。  
  
 Windows installer 的全面文档，请参阅平台 SDK 主题[Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx)。  
  
## <a name="authoring-a-vspackage"></a>创作 VSPackage  
 Windows 安装程序使用安装包，其中包含 Windows 安装程序需要安装、 卸载或修复产品并运行安装程序用户界面 (UI) 的信息。 每个安装包包括一个.msi 文件，其中包含安装数据库、 摘要信息和中的流的安装的各个部分的数据流。 若要使用安装程序，您必须创作安装。 安装程序将组织安装组件的设计思路，并将安装的相关信息存储在关系数据库，因为广泛创作安装包的过程需要执行以下步骤：  
  
1.  规划你创作以支持版本控制和并排显示策略的设置。  
  
2.  确定要呈现给用户的功能。  
  
3.  将 VSPackage 和依赖项组织到组件。  
  
4.  安装使用填充数据库信息。  
  
5.  验证安装包。  
  
 本文档主要关心过程的第一个和第三个步骤。 这些步骤期间你将组织你的 VSPackage 的功能到 WICs 以便你的版本控制和服务策略来应对的后续版本可以帧[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。 剩余的三个步骤中将平台 SDK 中的 Windows Installer 文档中详细介绍。  
  
## <a name="key-terms"></a>关键术语  
 以下是 Windows Installer 技术与相关的关键术语的定义。  
  
 资源  
 文件、 注册表项、 快捷方式，或，依此类推，可能会安装到计算机。 这些资源进行逻辑分组到 Windows 安装程序组件中。  
  
 Windows Installer 组件 (WIC)  
 表示已安装并卸载作为一个单元的相关资源的逻辑分组的安装基本单位。 Windows 安装程序组件由唯一组件 ID 或 GUID 标识。 此外，Windows Installer 维护其引用计数在 WIC 级别。 最大版本控制的灵活性，对于包含在中给定 WIC 不得超过一个主资源，如 DLL。 请注意，标识和填充 WIC，使其使用的 GUID，并将其部署后，你无法更改其构成。 有关详细信息，请参阅[组织为组件的应用程序](http://msdn.microsoft.com/library/aa370561.aspx)。  
  
 包 （Redist 包）  
 此文件可能指向的.msi 文件和外部源文件组成的部署单元。 包包含 Windows 安装程序需要运行 UI 和安装或卸载应用程序的所有信息。  
  
 .msi 文件  
 包含的说明和安装应用程序所需的数据的 COM 结构化存储文件。 每个包包含至少一个.msi 文件。 .Msi 文件包含安装程序数据库、 摘要信息流和可能是一个或多个转换和内部的源文件。 要安装的文件可以将其压缩为 cab 文件和存储在.msi 文件的流或存储，压缩，或未压缩，外部源的介质上的.msi 文件。 有关详细信息，请参阅[Windows 安装程序文件扩展名](http://msdn.microsoft.com/library/aa372842\(VS.85\).aspx)。  
  
## <a name="windows-installer-rules-enforcement"></a>Windows Installer 规则强制  
 两组规则确定通过安装程序的组件的资源的部署。 虽然应实施第二组安装的作者，将由 Windows 安装程序本身，维护一个规则集。  
  
> [!NOTE]
>  仅当你运行.msi 文件的验证，则会发生的 Windows Installer 规则的实施。 尽管如此，警告将这些规则视为最佳做法。 有关详细信息，请参阅[验证安装数据库](http://msdn.microsoft.com/library/aa372477\(VS.85\).aspx)和[包验证](http://msdn.microsoft.com/library/aa370569\(VS.85\).aspx)。  
  
#### <a name="installer-enforced-rules"></a>安装程序强制实施的规则  
  
-   给定的组件中的所有文件必须都安装到相同的目录。 相反，文件安装到单独的文件夹必须属于单独的组件。  
  
-   可以有每个组件只有一个注册表项路径。 密钥路径是只是文件或注册表项表示整个组件。  
  
#### <a name="component-provider-responsibilities"></a>组件提供程序的职责  
  
-   在后续版本中可能会单独提供任何两个资源应存在于不同的组件。 仅当你确信永远不会将单独提供这些资源时，应将资源分组为同一组件。 事实上，建议所有主要资源 (例如 Dll) 中单独 WICs 始终存在。 有关详细信息，请参阅[定义安装程序组件](http://msdn.microsoft.com/library/aa368269\(VS.85\).aspx)。  
  
-   无版本控制的资源不断应在多个 WIC 装运。  
  
## <a name="see-also"></a>请参阅  
 [如果组件规则被中断，会发生什么情况？](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)