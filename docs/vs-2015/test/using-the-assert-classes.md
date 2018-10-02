---
title: 使用 Assert 类 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.assetid: da1b7a0d-4f1d-4d50-a07e-7b3ff60053f9
caps.latest.revision: 29
ms.author: gewarren
manager: douge
ms.openlocfilehash: 14bdea144a28e971d99ea8528b66e0bce1164035
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478788"
---
# <a name="using-the-assert-classes"></a>使用 Assert 类
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[使用 Assert 类](https://docs.microsoft.com/visualstudio/test/using-the-assert-classes)。  
  
使用 UnitTestingFramework 命名空间的 Assert 类来验证特定功能。 单元测试方法会执行开发代码中的方法代码，但只有包含 Assert 语句时，它才会报告代码行为的正确性。  
  
## <a name="kinds-of-asserts"></a>Assert 的类型  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting> 命名空间提供多种类型的 Assert 类：  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>  
  
 在测试方法中，可以调用任意数量的 Assert 类的方法，例如 Assert.AreEqual()。 Assert 类有许多方法可供选择，并且其中有很多方法具有若干重载。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>  
  
 使用 CollectionAssert 类比较对象的集合，并验证一个或多个集合的状态。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>  
  
 使用 StringAssert 类比较字符串。 此类包含大量有用的方法，如 StringAssert.Contains、StringAssert.Matches 和 StringAssert.StartsWith。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>  
  
 测试失败时，将引发 AssertFailedException 异常。 如果测试超时，引发意外的异常，或者包含生成失败结果的 Assert 语句，测试则将失败。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>  
  
 测试生成无结论的结果时，将引发 AssertInconclusiveException。 通常，将 Assert.Inconclusive 语句添加到仍在进行的测试中以指示它尚未准备好运行。  
  
> [!NOTE]
>  替代策略将使用 Ignore 属性标记尚未准备好运行的测试。 但是，这样做的弊端是你无法轻松地对尚待执行的测试的数量生成报表。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>  
  
 如果编写新的 Assert 异常类，让该类从基类 UnitTestAssertException 继承使其可更轻松地将异常识别为断言失败，而不是从测试或生产代码引发的意外异常。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>  
  
 如果想要让测试方法验证期望由开发代码中的方法引发的异常确实是在该方法中引发的，请使用 ExpectedExceptionAttribute 属性修饰测试方法。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>   
 [为现有代码创建和运行单元测试](http://msdn.microsoft.com/en-us/e8370b93-085b-41c9-8dec-655bd886f173)


