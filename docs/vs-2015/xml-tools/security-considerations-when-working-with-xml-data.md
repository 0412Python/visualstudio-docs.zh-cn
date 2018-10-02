---
title: 使用 XML 数据时的安全注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce2b708-1aef-454f-be59-52b76f359351
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9acd701c4e279d02cae874768b18a3d89b58203d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477185"
---
# <a name="security-considerations-when-working-with-xml-data"></a>使用 XML 数据时的安全注意事项
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[时使用的 XML 数据的安全注意事项](https://docs.microsoft.com/visualstudio/xml-tools/security-considerations-when-working-with-xml-data)。  
  
  
本主题讨论在使用“XML 编辑器”或 XSLT 调试程序时需要了解的安全问题。  
  
## <a name="xml-editor"></a>XML 编辑器  
 “XML 编辑器”基于 Visual Studio 文本编辑器。 它依靠 <xref:System.Xml> 和 <xref:System.Xml.Xsl> 类处理许多 XML 进程。  
  
-   XSLT 转换在新的应用程序域中执行。 XSLT 转换为*沙盒*; 也就是说，您的计算机的代码访问安全策略用于确定受限的权限根据 XSLT 样式表所在的位置。 例如，来自 Internet 位置的样式表的权限最受限制，而复制到硬盘驱动器上的样式表则以“完全信任”权限运行。  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 类用于将 XSLT 编译为 Microsoft 中间语言，以便提高执行时的性能。  
  
-   编录文件中指向外部位置的架构将在“XML 编辑器”初次加载时自动下载。 <xref:System.Xml.Schema.XmlSchemaSet> 类用于编译架构。 随“XML 编辑器”提供的编录文件没有与任何外部架构的链接。 用户必须显式添加对外部架构的引用，“XML 编辑器”才能下载该架构文件。 可以通过禁用 HTTP 下载**杂项工具选项**页 XML 编辑器。  
  
-   “XML 编辑器”使用 <xref:System.Net> 类下载架构。  
  
## <a name="xslt-debugger"></a>XSLT 调试程序  
 XSLT 调试程序利用由 Visual Studio 管理的调试引擎以及 <xref:System.Xml> 和 <xref:System.Xml.Xsl> 命名空间中的类。  
  
-   XSLT 调试程序在沙盒型应用程序域中运行每个 XSLT 转换。 计算机的代码访问安全策略用于根据 XSLT 样式表所处的位置确定受限的权限。 例如，来自 Internet 位置的样式表的权限最受限制，而复制到硬盘驱动器上的样式表则以“完全信任”权限运行。  
  
-   XSLT 样式表使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类进行编译。  
  
-   XSLT 表达式计算器通过托管调试引擎加载。 托管调试引擎假定所有代码均从用户的本地计算机上运行。 <xref:System.Xml.Xsl.XslCompiledTransform> 类相应地将 XSLT 文件下载到用户的本地计算机上。 通过在具有受限权限的新应用程序域中执行所有 XSLT 转换，降低了发生执行权限升级的可能性。  
  
## <a name="see-also"></a>请参阅  
 [应用程序域](http://msdn.microsoft.com/en-us/39e57d07-a740-4cd4-ae82-e119ea3856c1)


