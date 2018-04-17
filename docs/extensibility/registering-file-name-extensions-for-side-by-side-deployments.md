---
title: 注册-并排部署的文件扩展名 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae7d7307ef12184dcbfc29254ec5cbae9ff55bb8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="registering-file-name-extensions-for-side-by-side-deployments"></a>注册-并排部署的文件扩展名
为部署在通过并行环境的 Vspackage，你必须注册要将文件的正确版本与关联文件扩展名[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。 除非你使用特定于版本的文件扩展名，注册使用户能够打开你的项目和项目项文件中的适当版本[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
 [关于文件扩展名](../extensibility/about-file-name-extensions.md)  
 讨论如何注册文件扩展名。  
  
 [指定文件扩展名的文件处理程序](../extensibility/specifying-file-handlers-for-file-name-extensions.md)  
 提供有关如何注册应用程序可以打开、 编辑和等等，特定文件扩展名的信息。  
  
 [注册文件扩展名的谓词](../extensibility/registering-verbs-for-file-name-extensions.md)  
 讨论如何注册谓词。  
  
 [管理并行文件关联](../extensibility/managing-side-by-side-file-associations.md)  
 讨论如何处理在其中通过并行安装的特定版本[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]应被调用来打开文件。  
  
## <a name="related-sections"></a>相关章节  
 [支持多个版本的 Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)  
 介绍与多个版本的相关问题[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]和你的 VSPackage 期间开发和部署到最终用户。