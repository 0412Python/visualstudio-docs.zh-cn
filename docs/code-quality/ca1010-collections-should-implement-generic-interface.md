---
title: CA1010：集合应实现泛型接口
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f79a0e4fcb9cf4f82b85e9d62ffa51ef969293c7
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550994"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010：集合应实现泛型接口
|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 外部可见的类型实现<xref:System.Collections.IEnumerable?displayProperty=fullName>接口，但不实现<xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>接口，并且包含程序集针对[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]。 此规则会忽略类型实现的<xref:System.Collections.IDictionary?displayProperty=fullName>。

## <a name="rule-description"></a>规则说明
 若要扩大集合的用途，应实现某个泛型集合接口。 然后可以使用集合来填充泛型集合类型，如下所示：

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>

- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>

- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，实现以下泛型集合接口之一：

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>

- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>

- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示此规则; 的警告但是，该集合将具有更多限制的使用。

## <a name="example-violation"></a>冲突的示例

### <a name="description"></a>描述
 下面的示例演示派生自非泛型类 （引用类型）`CollectionBase`类，与此规则冲突。

### <a name="code"></a>代码
 [!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

### <a name="comments"></a>注释
 若要解决此冲突的冲突，应实现泛型接口，或将基类更改为已实现了这两个泛型和非泛型接口，如类型`Collection<T>`类。

## <a name="fix-by-base-class-change"></a>通过基类更改进行修复

### <a name="description"></a>描述
 下面的示例通过从非泛型更改集合的基类中修复了冲突`CollectionBase`泛型类`Collection<T>`(`Collection(Of T)`中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 类。

### <a name="code"></a>代码
 [!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

### <a name="comments"></a>注释
 更改已发布的类的基类被视为对现有使用者的重大更改。

## <a name="fix-by-interface-implementation"></a>通过接口实现进行修复

### <a name="description"></a>描述
 下面的示例通过实现这些泛型接口中修复了冲突： `IEnumerable<T>`， `ICollection<T>`，并`IList<T>`(`IEnumerable(Of T)`， `ICollection(Of T)`，并且`IList(Of T)`中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])。

### <a name="code"></a>代码
 [!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1005：避免泛型类型的参数过多](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1000：不要在泛型类型中声明静态成员](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002：不要公开泛型列表](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006：不要将泛型类型嵌套在成员签名中](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004：泛型方法应提供类型形参](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003：使用泛型事件处理程序实例](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007：在适用处使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>请参阅
 [泛型](/dotnet/csharp/programming-guide/generics/index)