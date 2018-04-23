---
title: .NET compiler Platform (&quot;Roslyn&quot;) 扩展性 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 564201b3-1e18-4b88-b615-42c2f57f3fe8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09287c48285bfcdc32b1a7d558d44f9d212f1b41
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="net-compiler-platform-quotroslynquot-extensibility"></a>.NET compiler Platform (&quot;Roslyn&quot;) 扩展性
.NET Compiler Platform ("Roslyn") 的核心任务是打开的 C# 和 Visual Basic 编译器，允许工具和开发人员共享的丰富信息编译器中有程序的相关。 代码分析工具可提高代码质量和代码生成器帮助在应用程序构造。 随着越来越灵活工具，他们需要访问为越来越多的仅编译器具有深层代码知识。 而不是不透明转换器 （中的源代码和扩展对象代码），Roslyn 编译器提供可用于与代码相关工具和应用程序中的任务的 Api。  
  
 最棒的是 Roslyn 编译器、 其 Api、 示例和演练中和这些 Api 为基础构建的实际工具是在所有完全打开源[github.com/dotnet/roslyn](https://github.com/dotnet/Roslyn)。 请转到 OSS 站点，以了解详细信息和开始使用 Roslyn。 你将找到链接以获取最新的 C# 和 VB 功能，可以使用作为最终用户，以及指向作为工具生成器利用 Roslyn Api 开始的链接。  
  
## <a name="see-also"></a>另请参阅  
 [Roslyn 分析器入门](../extensibility/getting-started-with-roslyn-analyzers.md)