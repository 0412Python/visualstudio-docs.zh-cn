---
title: CA1506： 避免过度类耦合 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 018abf05181be812bcf01fc9cb910745dc085bcf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506：避免过度类耦合
|||  
|-|-|  
|TypeName|AvoidExcessiveClassCoupling|  
|CheckId|CA1506|  
|类别|Microsoft.Maintainability|  
|是否重大更改|重大|  
  
## <a name="cause"></a>原因  
 与许多其他类型结合使用的类型或方法。  
  
## <a name="rule-description"></a>规则说明  
 此规则通过计算类型或方法包含的唯一类型引用的个数来衡量类耦合。  
  
 类型和具有类耦合度很高的方法可能很难维护。 它是一个好办法具有类型和低耦合、 内聚高的方法。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要解决此冲突，请尝试重新设计的类型或方法，以减少之耦合的类型的数量。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 在类型或方法仍被视为可维护尽管其大量的其他类型的依赖关系时，请排除此警告。  
  
## <a name="see-also"></a>另请参阅  
 [可维护性警告](../code-quality/maintainability-warnings.md)   
 [测量托管代码的复杂性和可维护性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)